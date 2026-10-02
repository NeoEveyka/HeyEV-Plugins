# 🧩 Stream Plugins & Extensions Repository

Yeh repository **Video Streaming App** ke dynamic plugins ko host karne ke liye banayi gayi hai. Isse app me bina kisi update ke Live TV aur HDHub4u Movie scrapers ko update kiya ja sakta hai.

---

## 📁 Repository Structure

```
stream-plugins/
├── repo.json                              <-- Master Repository Catalog
└── plugins/
    ├── hdhub4u_provider.json             <-- HDHub4u Movies Scraper Plugin
    ├── livetv_india_provider.json        <-- Live TV India IPTV Plugin
    └── livetv_channels.m3u               <-- Live TV M3U Channels Playlist
```

---

## 🚀 GitHub Par Upload / Host Karne Ka Tarika (Step-by-Step)

### Step 1: GitHub Par New Repository Banayein
1. [GitHub.com](https://github.com) par jayein aur **"New Repository"** par click karein.
2. Repository ka naam rakhein: `stream-plugins`
3. Visibility select karein: **Public** (taaki direct raw link accessible rahe) ya **Private with Token**.
4. **Create Repository** dabayein.

### Step 2: Files Upload Karein
Terminal se push karne ke liye:
```bash
cd plugins_repository
git init
git add .
git commit -m "feat: initial release of stream plugins"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/stream-plugins.git
git push -u origin main
```
*(Ya aap direct GitHub website par **Upload files** button se `repo.json` aur `plugins/` folder drag & drop kar sakte hain).*

---

## 🔗 App Me Repository Add Kaise Karein?

1. GitHub par `repo.json` file open karein aur **"Raw"** button par click karein.
2. Raw URL kuch aisa hoga:
   ```
   https://raw.githubusercontent.com/YOUR_USERNAME/stream-plugins/main/repo.json
   ```
3. App me jayein $\rightarrow$ **Extensions & Plugins** $\rightarrow$ **Repos** tab $\rightarrow$ **+ Add Repository** $\rightarrow$ Link paste karein!
4. **Discover** tab me aapko **HDHub4u Movies** aur **Live TV India** dikhai dega, jahan se user **1-Click Install** kar sakta hai.

---

## 🔄 Plugin Update Kaise Karein? (Jab Mirror Ya Links Change Hon)

Jab bhi HDHub4u ka domain change ho ya Live TV link badle:
1. Bas GitHub par `plugins/hdhub4u_provider.json` me naye domains/mirrors update karein.
2. `repo.json` me version `1.0.2` se `1.0.3` kar dein.
3. Users ki app me automatic **Update** button aa jayega!
