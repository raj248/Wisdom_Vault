## 🔧 Option 1: Load different files manually

You can tell **dotenv** exactly which file to load:

```ts
import dotenv from "dotenv";

const envFile =
  process.env.NODE_ENV === "production" ? ".env.production" : ".env.development";

dotenv.config({ path: envFile });

console.log(`Loaded from: ${envFile}`);
console.log(`PORT = ${process.env.PORT}`);
```

Then create your files:

```
.env.development
PORT=3000

.env.production
PORT=8080
```

And run:

```bash
NODE_ENV=development npm run dev
NODE_ENV=production npm start
```

---

## 🔧 Option 2: Use [dotenv-flow](https://www.npmjs.com/package/dotenv-flow)

This package extends `dotenv` with first-class support for multiple files:

```bash
npm install dotenv-flow
```

Usage:

```ts
import dotenvFlow from "dotenv-flow";

dotenvFlow.config();

console.log(process.env.PORT);
```

It automatically looks for:

* `.env` (common defaults)
* `.env.development` / `.env.production` / `.env.test` (overrides based on `NODE_ENV`)
* `.env.local` (ignored by git, machine-specific overrides)

So you’d have a structure like:

```
.env             # shared defaults
.env.development # dev overrides
.env.production  # prod overrides
.env.test        # test overrides
.env.local       # personal local overrides (not committed)
```

And just run:

```bash
NODE_ENV=production npm start
NODE_ENV=development npm run dev
```

---

## ⚖️ Which approach to choose?

* **Simple projects** → Option 1 (plain dotenv + `path`) is enough.
* **Bigger apps / teams** → Option 2 (`dotenv-flow`) is nicer because it follows conventions and supports `.env.local` automatically.

