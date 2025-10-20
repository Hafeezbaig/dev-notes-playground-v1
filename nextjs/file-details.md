### 📁 **node_modules/**

Holds all the packages (dependencies) your app uses — installed via `npm install`.

---

### 📁 **public/**

Stores static files (images, icons, etc.) that are served directly — e.g. `/logo.png`.

---

### 📁 **src/**

Main source code folder (contains your `app/` or `pages/` directory, components, etc.).

---

### ⚙️ **.gitignore**

Lists files and folders Git should **ignore** (like `node_modules`).

---

### ⚙️ **eslint.config.mjs**

Configuration for **ESLint**, a tool that checks and fixes coding style issues.

---

### ⚙️ **next-env.d.ts**

TypeScript definitions automatically added by Next.js — don’t edit this file.

---

### ⚙️ **next.config.ts**

Main **Next.js configuration file** — used to customize build, redirects, images, etc.

---

### 📦 **package.json**

Defines your project details, dependencies, and scripts like:

```json
"scripts": {
  "dev": "next dev",
  "build": "next build",
  "start": "next start"
}
```

---

### 📦 **package-lock.json**

Exact versions of all installed packages — ensures consistent installs.

---

### ⚙️ **postcss.config.mjs**

Config for **PostCSS**, which processes CSS (used with Tailwind CSS).

---

### 📘 **README.md**

Project overview or instructions — markdown file shown on GitHub.

---

### ⚙️ **tsconfig.json**

TypeScript configuration — controls how TypeScript compiles your code.

---

### 🖼️ **favicon.ico**

* The small icon shown in the **browser tab**.
* Located in `public/` folder.
* You can replace it with your own logo.

---

### 🎨 **globals.css**

* Contains **global styles** that apply to the whole app.
* Usually imported in `layout.tsx`.
* Good place for CSS resets or common styles (e.g. body font, background).

---

### 🧩 **layout.tsx**

* Defines a **shared layout** for all pages.
* Wraps around every page (e.g., header, footer, theme).
* You can have nested layouts too.

```tsx
export default function RootLayout({ children }) {
  return (
    <html>
      <body>
        <Navbar />
        {children}
      </body>
    </html>
  )
}
```

---

### 📄 **page.tsx**

* The **actual page content** shown for a route.
* For example, `app/page.tsx` → `/`, `app/about/page.tsx` → `/about`.
* You can have multiple `page.tsx` files inside folders for different routes.

---

