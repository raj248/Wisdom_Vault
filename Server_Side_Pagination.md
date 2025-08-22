
### 🔹 1. Backend (Express + Prisma Example)

```ts
// GET /api/users?page=2&limit=10
app.get("/api/users", async (req, res) => {
  try {
    const page = parseInt(req.query.page as string) || 1;
    const limit = parseInt(req.query.limit as string) || 10;

    const skip = (page - 1) * limit;

    const [users, total] = await Promise.all([
      prisma.user.findMany({
        skip,
        take: limit,
        orderBy: { createdAt: "desc" },
      }),
      prisma.user.count(),
    ]);

    res.json({
      success: true,
      data: users,
      pagination: {
        total,
        page,
        limit,
        totalPages: Math.ceil(total / limit),
      },
    });
  } catch (error) {
    res.status(500).json({ success: false, error: "Something went wrong" });
  }
});
```

✅ This API returns:

```json
{
  "success": true,
  "data": [ ...users ],
  "pagination": {
    "total": 120,
    "page": 2,
    "limit": 10,
    "totalPages": 12
  }
}
```

---

### 🔹 2. Frontend (React Query Example)

```ts
import { useQuery } from "@tanstack/react-query";
import axios from "axios";

const API_URL = import.meta.env.VITE_API_URL;

interface PaginatedResponse<T> {
  success: boolean;
  data: T[];
  pagination: {
    total: number;
    page: number;
    limit: number;
    totalPages: number;
  };
}

export const getUsers = async (page: number, limit: number) => {
  const res = await axios.get<PaginatedResponse<User>>(
    `${API_URL}/user?page=${page}&limit=${limit}`
  );
  return res.data;
};

export const useUsers = (page: number, limit: number) =>
  useQuery({
    queryKey: ["users", page, limit],
    queryFn: () => getUsers(page, limit),
    keepPreviousData: true, // smooth transition
  });
```

---

### 🔹 3. React Component with Pagination Controls

```tsx
import { useState } from "react";
import { useUsers } from "@/api/users";

function UserList() {
  const [page, setPage] = useState(1);
  const limit = 10;

  const { data, isLoading } = useUsers(page, limit);

  if (isLoading) return <p>Loading...</p>;

  return (
    <div>
      <ul>
        {data?.data.map((user) => (
          <li key={user.id}>{user.userId}</li>
        ))}
      </ul>

      <div className="flex gap-2 mt-4">
        <button
          disabled={page === 1}
          onClick={() => setPage((p) => p - 1)}
        >
          Prev
        </button>
        <span>
          Page {data?.pagination.page} of {data?.pagination.totalPages}
        </span>
        <button
          disabled={page === data?.pagination.totalPages}
          onClick={() => setPage((p) => p + 1)}
        >
          Next
        </button>
      </div>
    </div>
  );
}
```

---

🔥 With this setup:

* Backend only sends the **needed records**.
* React Query handles cache + smooth pagination.
* UI shows total pages & enables/disables prev/next.

---

integrate pagination buttons (or ui) with the backend.
