To manage dynamic metadata (like the page title and description) in a React app, the industry standard is to use a library called **React Helmet Async**. 

Since your app is a Single Page Application (SPA), the browser doesn't naturally "see" a new page when the route changes. React Helmet Async injects these tags into the `<head>` of your document dynamically.

### 1. Installation
First, install the library:
```bash
npm install react-helmet-async
```

---

### 2. Setup the Provider
In your `App.tsx`, you need to wrap your entire application in the `HelmetProvider`. This allows all child components to update the head.

```tsx
import { HelmetProvider } from 'react-helmet-async';

const App: React.FC = () => {
  return (
    <BrowserRouter>
      <HelmetProvider> {/* Add this wrapper */}
        <SettingProvider>
           {/* ... rest of your code */}
        </SettingProvider>
      </HelmetProvider>
    </BrowserRouter>
  );
};
```

---

### 3. Usage on Static Pages
For pages like **About** or **Privacy Policy**, you can just drop the `Helmet` component at the top of the file:

**`pages/AboutPage.tsx`**
```tsx
import { Helmet } from 'react-helmet-async';

const AboutPage = () => {
  return (
    <>
      <Helmet>
        <title>About Us | YourStore</title>
        <meta name="description" content="Learn more about our company and values." />
      </Helmet>
      <div>
        {/* Your about page content */}
      </div>
    </>
  );
};
```

---

### 4. Usage on Dynamic Pages (Product Details)
This is where it gets powerful. For your `ProductDetails` page, you can use the data fetched from your backend (like the `product.title` and `product.image`) to set the meta tags. This is crucial for social media sharing (OpenGraph).

**`pages/ProductDetails.tsx`**
```tsx
import { Helmet } from 'react-helmet-async';

const ProductDetails = ({ product }) => {
  return (
    <>
      {product && (
        <Helmet>
          <title>{product.title.en} | YourStore</title>
          <meta name="description" content={product.description.en.substring(0, 160)} />
          
          {/* Social Media (Open Graph) */}
          <meta property="og:title" content={product.title.en} />
          <meta property="og:description" content={product.description.en.substring(0, 160)} />
          <meta property="og:image" content={product.image[0]} />
          <meta property="og:url" content={window.location.href} />
          <meta name="twitter:card" content="summary_large_image" />
        </Helmet>
      )}
      
      <div className="product-details">
        {/* ... */}
      </div>
    </>
  );
};
```

---

### 5. Create a Reusable SEO Component (Recommended)
Instead of repeating the `<Helmet>` block everywhere, create a small component:

**`components/common/SEO.tsx`**
```tsx
import { Helmet } from 'react-helmet-async';

interface SEOProps {
  title?: string;
  description?: string;
  image?: string;
}

const SEO = ({ title, description, image }: SEOProps) => {
  const siteName = "YourStore";
  const fullTitle = title ? `${title} | ${siteName}` : siteName;

  return (
    <Helmet>
      <title>{fullTitle}</title>
      <meta name="description" content={description || "Best e-commerce shop in town!"} />
      {image && <meta property="og:image" content={image} />}
    </Helmet>
  );
};

export default SEO;
```

**Then use it like this in any page:**
`<SEO title="Contact Us" description="Get in touch with us for support." />`

---

### One Critical Note on SEO
Because your app is a **Client-Side Rendered (CSR)** app, Google will eventually see these tags, but bots from **Facebook, WhatsApp, and Twitter** often don't execute JavaScript. 

If social media link previews are very important for your products, you might eventually need to look into **Vite-plugin-ssr** or **Prerendering**. But for standard SEO, React Helmet is the way to go!

**Would you like me to show you how to generate a dynamic `sitemap.xml` for your products so Google can find all your dynamic pages?**
