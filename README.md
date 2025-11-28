📰 LiveHindustan Clone – News Portal

A fully responsive Hindi News Website built using Next.js (Pages Router), Tailwind CSS, and NewsAPI, featuring infinite scroll, trending news, categories, dynamic articles, and automatic fallback to local JSON data.

🚀 Features
✅ Modern, Responsive UI

Clean layout inspired by LiveHindustan

Multi-column layout

Hero section for top story

Trending news sidebar

Tailwind-based UI

✅ Infinite Scrolling

Uses IntersectionObserver

Auto loads next page

Handles loading, end-of-data, and errors

✅ Category-Based News

Supports:

Home

Business

Sports

Technology

Entertainment

Science

Health

✅ Dynamic Routing

Every article gets its own page:

/articles/[slug]

✅ API Layer
/api/news


Supports:

Pagination

Category filtering

Trending fetch

Fallback to local JSON

✅ Local JSON Fallback

If no NEWSAPI_KEY present → uses:

data/articles.json


Project works 100% offline.

📁 Project Structure
news-portal/
│── pages/
│   ├── index.js
│   ├── articles/[slug].js
│   └── api/news.js
│
│── components/
│   ├── Navbar.jsx
│   ├── NewsCard.jsx
│   ├── InfiniteScrollBox.jsx
│   ├── TrendingSidebar.jsx
│
│── lib/
│   └── news.js
│
│── data/
│   └── articles.json
│
│── public/
│── styles/
│── package.json
│── README.md

🛠 Technologies Used
Tech	Purpose
Next.js	Routing + Server-side fetching
Tailwind CSS	UI styling
NewsAPI.org	Real news feed
React Hooks	State + Effects
IntersectionObserver	Infinite scroll
Slugify algorithm	URL slugs
⚙️ Installation & Setup
1️⃣ Clone the repository
git clone https://github.com/yourusername/news-portal.git
cd news-portal

2️⃣ Install dependencies
npm install

3️⃣ Add environment variable

Create a .env.local file:

NEWSAPI_KEY=your_api_key_here


If empty → project automatically falls back to local JSON.

4️⃣ Start dev server
npm run dev


Server starts on:
👉 http://localhost:3000

📡 API Endpoints
/api/news
Query Param	Example	Purpose
page	?page=2	Pagination
pageSize	?pageSize=9	Limit
category	?category=sports	Filter
top	?top=1	Trending

Example:

/api/news?page=1&pageSize=10&category=business

🧪 Testing & Edge Cases

✔ Fallback image when image missing
✔ Graceful message when no articles
✔ Infinite scroll stops correctly
✔ Long titles wrap properly
✔ Trending fetch error → silent fallback
✔ Article slug lookup works even offline

🪵 Data Model

Each article contains:

{
  id: "",
  slug: "",
  title: "",
  summary: "",
  content: "",
  image: "",
  author: "",
  publishedAt: "",
  url: ""
}

🚧 Known Issues

NewsAPI returns limited Hindi content

Rate limit restrictions

Trending highly dependent on API quality

🚀 Future Improvements

Add search bar

Add weather widget

Save/bookmark articles

Dark mode toggle

More real-time trending logic

🤖 AI Usage & Reflection

Parts where AI was used:

Component boilerplates

Tailwind class suggestions

Debugging API logic

Improving infinite scroll logic

How AI was corrected:

Fixed incorrect imports

Adjusted layout manually

Fixed slug generation

Improved error handling

Custom improvements by the developer:

Local JSON fallback logic

Custom-designed UI

Better performance handling

Cleaned code organization

👨‍💻 Author

Sahitya Pandey
Full-Stack Developer
🔥 Passionate about building modern UI & real-world clones.
