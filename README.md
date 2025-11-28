# 📰 Live Hindustan Style News Portal  
A fully functional Hindi News Website built using **Next.js**, **TailwindCSS**, and **NewsAPI.org**, inspired by the layout and design style of *LiveHindustan.com*.

---

# 📌 Part A – Project Overview

## 🎯 Project Title  
**LiveHindustan-Style News Portal with Infinite Scroll & Trending Feed**

## 📘 Project Description  
This project is a Hindi News Portal clone inspired by LiveHindustan.com.  
The website provides real-time news updates using **NewsAPI**, supports **infinite scrolling**, **category-based filtering**, **trending news**, and a **Hindi-first UI**.

Built using:

- **Next.js**
- **TailwindCSS**
- **API Route Handlers**
- **NewsAPI.org**
- **Dynamic Categories**
- **Trending Top Stories**
- **Infinite Scroll List**

---

## ✨ Features Implemented

### ✔ LiveHindustan-like layout  
- Hero top story  
- 3-column layout  
- Trending sidebar  
- Infinite scroll on the right side  

### ✔ Real-time updated news  
Fetched securely from NewsAPI backend.

### ✔ Hindi UI  
Typography, labels, and content styling optimized for Hindi news layout.

### ✔ Fast Loading  
Infinite scrolling ensures seamless browsing experience.

---

# 📝 Part B – Explanation & Documentation

## 1. 🎨 Design Document

### 🖼 Wireframe Overview

┌──────────────────────────────────────────────┐
                │ Navbar │
└──────────────────────────────────────────────┘

┌───────────────┬──────────────────────────────┬───────────────┐
│ Trending │ Hero Top Story │ Latest News │
│ Sidebar │ (Large Featured Article) │ List Cards │
└───────────────┴──────────────────────────────┴───────────────┘

┌──────────────────────────────────────────────┐
│ Infinite Scroll List │
└──────────────────────────────────────────────┘


### 📐 Layout Decisions

- Followed the **LiveHindustan 3-column layout**
- Center block used to highlight the **main article**
- Left side contains **Top Trending** for quick reading
- Right side shows **Infinite Scroll List**
- Used TailwindCSS for typography, spacing, and responsiveness

---

## 2. 🛰 Data-Fetching Strategy

### ✔ API Route Handler  
`/api/news` used so API key stays secure.

### ✔ Client-side Fetching  
Used in **InfiniteScrollBox** to load next pages.

### ✔ Why Route Handlers + Client Fetch (Hybrid)?  
| Method | Reason |
|--------|--------|
| API Route Handler | Protect API key and structure response |
| Client Fetch | Needed for infinite scrolling |
| SSR | Used for first-page fast loading |

---

## 3. 🧩 Component Explanation

### Components Used in the Project

- **Navbar.jsx** → Category navigation in Hindi  
- **Hero.jsx** → Displays top main story  
- **TrendingSidebar.jsx** → Top stories list  
- **InfiniteScrollBox.jsx** → Loads stories as user scrolls  
- **NewsCard.jsx** → Single card for each article  
- **Error + Loading Components** → Improve UX  

---

## 4. 🗂 Data Model Structure

### Article Object Example

```js
{
  title: "Breaking News",
  description: "Important event occurred...",
  image: "https://example.com/image.jpg",
  publishedAt: "2025-01-01",
  url: "https://source.com",
  source: "BBC"
}

## 📌 Part C – Challenges Faced & Learnings

### **1️⃣ Tailwind & Next.js Setup Issues**
- Faced errors during Tailwind installation (`npm error ETARGET`, `could not determine executable to run`).
- Fixed by:
  - Deleting `node_modules` and `package-lock.json`
  - Installing correct Tailwind packages
  - Running:
    ```bash
    npx tailwindcss init -p
    ```

### **2️⃣ App Router vs Pages Router Conflict**
- Error: **“App Router and Pages Router both match path: /”**
- Cause: Having both `pages/` and `app/` folders.
- Fix: Removed the `pages/` folder and kept only App Router.

### **3️⃣ Layout.js Error**
- Missing required export in `layout.js`.
- Fixed by adding:
  ```js
  export const metadata = { title: "Home" };
<html lang="en">
  <body>{children}</body>
</html>

## 🔧 4️⃣ News Not Displaying

### **Issues Included**
- Wrong API URL
- Missing `await` while fetching data
- Undefined article fields

### **Fixes**
- Created a clean data-fetching function
- Used `console.log()` to inspect API response
- Added optional chaining + fallback values  
  ```js
  article?.title || "No title available"
## 🖼️ 5️⃣ Image Rendering Errors

### **Problem**
Some news articles from the API do not include images, which caused:
- Layout breaking
- Broken `<img>` elements
- Blank blocks in UI

### **Solution**
- Added a fallback placeholder image
- Checked `urlToImage` before rendering
- Used a safe default image when missing

```js
<img 
  src={article?.urlToImage || "/placeholder.jpg"} 
  alt={article?.title || "News Image"} 
/>
## 🎨 6️⃣ UI Layout Problems

### **Issues Noticed**
- Layout breaking on smaller screens  
- Cards overlapping  
- Uneven spacing between sections  
- No proper grid structure  

### **Fix Implemented**
- Added Tailwind spacing utilities (`p-4`, `mt-6`, `gap-6`)
- Used a responsive grid layout
- Ensured proper mobile → desktop scaling

### **Code Snippet**

```html
<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
  <!-- News cards here -->
</div>
## 🧪 7️⃣ Error Handling & Edge Cases

### **Handled Edge Cases**
- API returns `null` or malformed data  
- Missing fields like `title`, `image`, `author`  
- Layout breaking due to long text  
- Network/API failure  

---

### ✅ **Fallbacks Added**

#### **1. Missing Image → Show Placeholder**
```js
<Image 
  src={article.urlToImage || "/placeholder.jpg"} 
  alt={article.title || "News Image"} 
  fill
/>

Missing Title or Description
<h2>{article?.title || "Untitled Article"}</h2>
<p>{article?.description || "No description available."}</p>

API Failure → Show Error UI
if (!articles || articles.length === 0) {
  return <div className="text-center text-gray-600">No news available. Please try again.</div>;
}

Loading State

{loading && <p className="text-center">Loading news...</p>}
