# 🧩 HeyEV Community Plugins & Extensions Repository

Yeh public Git repository **HeyEV Video Streaming App** ke dynamic plugins aur extensions ko host karne ke liye banayi gayi hai. Is system ki madad se koi bhi user ya community developer **bina app ko recompile kiye** naye websites, scrapers, video extractors, aur Live TV channels add kar sakta hai!

---

## 🌟 Features of the Plugin System
- **⚡ 100% Modularity**: App ka jo default functionality hai wo waise hi rehta hai, naye features plugins ke through aate hain.
- **🌐 Public Git Ecosystem**: GitHub par repo host karein, aur app me repository link paste karke instant install karein.
- **📺 Seamless In-App Working**:
  - **Watch History**: Plugin ka video play hote hi app ke Watch History me save hota hai with resume position!
  - **Database & Library**: Plugin ke kisi bhi video/movie ko 1-click me user apne Cloudflare D1 Database ("My Links") me save kar sakta hai.
  - **Player & MiniPlayer**: In-app hardware-accelerated video player me custom headers ke sath smooth playback.
  - **URL Interceptor**: Agar user "Play by URL" ya "Add Link" me plugin ka supported domain daalta hai, plugin automatically URL ko extract kar leta hai.

---

## 📁 Repository Structure

```
HeyEV-Plugins/
├── repo.json                              <-- Master Repository Index Catalog
└── plugins/
    ├── hdhub4u_provider.json             <-- HDHub4u Movies Scraper Plugin
    ├── livetv_india_provider.json        <-- Live TV India IPTV Plugin
    ├── dailymotion_provider.json         <-- Dailymotion Video Extractor Plugin
    ├── archiveorg_provider.json          <-- Internet Archive Media Plugin
    └── livetv_channels.m3u               <-- Live TV M3U Channels Playlist
```

---

## 🛠️ Nayi Website Ya Extractor Ka Plugin Kaise Banayein?

Plugin ek declarative JSON file hoti hai jo `plugins/` folder me rakhi jaati hai aur `repo.json` me list hoti hai.

### 1. Website Scraper Plugin Example (`website_scraper`)
Agar kisi video/movie website ko browse aur search karne ke liye plugin banana hai:

```json
{
  "id": "org.mywebsite.movies",
  "name": "MyMovies Scraper",
  "version": "1.0.0",
  "description": "Browse and stream movies from MyMovies site.",
  "author": "Community Dev",
  "type": "website_scraper",
  "supportedDomains": ["mymovies.com"],
  "config": {
    "baseUrl": "https://mymovies.com",
    "catalogEndpoint": "https://api.mymovies.com/catalog?page={page}&cat={category}",
    "searchEndpoint": "https://api.mymovies.com/search?q={query}&page={page}",
    "streamTemplate": "https://mymovies.com/watch/{id}",
    "categories": ["All", "Action", "Drama", "Sci-Fi"]
  }
}
```

### 2. Video Extractor Plugin Example (`video_extractor`)
Agar kisi specific video host ya website URL ko resolve karne ke liye plugin banana hai (jaise Dailymotion, Bilibili, etc.):

```json
{
  "id": "com.community.dailymotion",
  "name": "Dailymotion Extractor",
  "version": "1.0.0",
  "description": "Resolves Dailymotion video URLs to direct streams.",
  "author": "Community",
  "type": "video_extractor",
  "supportedDomains": [
    "dailymotion.com",
    "dai.ly"
  ],
  "config": {
    "extractType": "api",
    "streamEndpoint": "https://www.dailymotion.com/player/metadata/video/{id}"
  }
}
```

### 3. Live TV / IPTV Playlist Plugin Example (`iptv`)
```json
{
  "id": "in.stream.livetv.india",
  "name": "Live TV India (IPTV)",
  "version": "1.0.1",
  "description": "Watch 100+ Live Indian TV channels.",
  "author": "IPTV Community",
  "type": "iptv",
  "config": {
    "playlistUrls": [
      "https://iptv-org.github.io/iptv/countries/in.m3u"
    ]
  }
}
```

---

## 🚀 Apna Git Repository GitHub Par Kaise Host Karein?

1. **GitHub par New Repo Banayein**:
   - [GitHub.com](https://github.com) par jayein $\rightarrow$ `New Repository`.
   - Name rakhein: `HeyEV-Plugins` (ya apna custom naam).
   - Visibility: **Public**.

2. **Files Commit & Push Karein**:
   ```bash
   git init
   git add .
   git commit -m "feat: initial release of community plugins"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/HeyEV-Plugins.git
   git push -u origin main
   ```

3. **App Me Repository Add Karein**:
   - `repo.json` ka GitHub Raw link copy karein:
     ```
     https://raw.githubusercontent.com/YOUR_USERNAME/HeyEV-Plugins/main/repo.json
     ```
   - HeyEV App open karein $\rightarrow$ **Plugins & Extensions** $\rightarrow$ **Repositories** tab $\rightarrow$ **+ Add Public Git Repo** $\rightarrow$ Link paste karein!
   - Sabhi plugins **Discover** tab me instant display ho jayenge aur user 1-tap me install kar sakega!

---

## 📱 App Ke Andar Custom Plugin Direct Import Karna

Developer test karne ke liye bina Git push kiye direct bhi plugin install kar sakte hain:
1. HeyEV App $\rightarrow$ **Plugins & Extensions** screen.
2. Top bar me **[+] Import Custom Plugin** icon tap karein.
3. Apna JSON paste karein aur **Install** dabayein!
