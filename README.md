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
