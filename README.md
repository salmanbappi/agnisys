<div align="center">

<img src="app/src/main/res/drawable/ic_launcher.png" width="120" alt="AgniSYS Icon"/>

# 🔥 AgniSYS

**An Aniyomi extension for a private Jellyfin media server**

[![Build AgniSYS](https://github.com/salmanbappi/agnisys/actions/workflows/build.yml/badge.svg)](https://github.com/salmanbappi/agnisys/actions/workflows/build.yml)
![Version](https://img.shields.io/badge/version-14.1000+-orange)
![Lang](https://img.shields.io/badge/lang-All-blue)
![Type](https://img.shields.io/badge/type-Jellyfin-purple)

</div>

---

## 📖 Overview

**AgniSYS** is a private Aniyomi extension that connects to a self-hosted [Jellyfin](https://jellyfin.org) media server. It can be installed **side-by-side** with the `Bijoy` extension since it uses a completely separate package ID and source ID.

| Property | Value |
|----------|-------|
| **Extension name** | AgniSYS |
| **Package ID** | `eu.kanade.tachiyomi.animeextension.all.agnisys` |
| **Server URL** | `http://182.252.81.180:8096` |
| **Username** | `vibe` |
| **Total content** | ~24,461 items |
| **Language** | All (multi-language library) |
| **Version** | 14.1000+ (auto-increments on each build) |

---

## 📦 Installation

Install via the **SalmanBappi extension repo**:

```
https://raw.githubusercontent.com/salmanbappi/extensions-repo/main/index.min.json
```

Or download the latest APK directly from the [Releases](https://github.com/salmanbappi/agnisys/releases/latest) page.

> ✅ Safe to install alongside **Bijoy** — different package ID, no conflicts.

---

## 🗂️ Library Categories

The server exposes **15 real library sections**, all accessible from the **Filter → Library** menu:

| # | Category | Content |
|---|----------|---------|
| 1 | All Libraries | Everything (24,461+ items) |
| 2 | Bangla Movies | Bangladeshi cinema |
| 3 | Bollywood Movies | Hindi films |
| 4 | Hollywood Movies | English films |
| 5 | Animation Movies | Animated features |
| 6 | Horror Movies | Horror genre |
| 7 | Turkish Movies | Turkish cinema |
| 8 | Iranian Movies | Iranian cinema |
| 9 | Korean & Hindi Movies | Korean + Hindi dubs |
| 10 | Chinese Movies | Chinese cinema |
| 11 | Web Series | TV series & web shows |
| 12 | IMDB Top Movies | IMDB highest-rated |
| 13 | Tutorials | Educational content |
| 14 | Collections | Boxsets & collections |
| 15 | Music Videos | Music video library |

---

## 🔥 Browse Sections

### Popular
Sorted by **Community Rating (Descending)** — the highest-rated titles appear first.  
Ratings are IMDB/TMDB community scores (scale 0–10).

### Latest
Sorted by **Date Added (Descending)** — shows the most recently added content first.  
Perfect for checking new uploads to the server.

---

## 🔍 Filters

Four independent filter dimensions that can be combined freely:

### 📁 Library Filter
Select from any of the 15 server libraries listed above.  
Narrows results to that specific collection.

### 🎭 Genre Filter
**27 genres** pulled directly from the server's `/Genres` endpoint:

`Action` · `Adult` · `Adventure` · `Animation` · `Biography` · `Comedy` · `Crime` · `Documentary` · `Drama` · `Family` · `Fantasy` · `History` · `Horror` · `Music` · `Musical` · `Mystery` · `Reality-TV` · `Romance` · `Science Fiction` · `Sci-Fi` · `Short` · `Sport` · `Talk-Show` · `Thriller` · `TV Movie` · `War` · `Western`

### 🔀 Sort Filter
5 sort options with **ascending / descending** toggle:

| Option | API Field |
|--------|-----------|
| Name | `SortName` |
| Date Added | `DateCreated, SortName` |
| Rating | `CommunityRating, SortName` |
| Release Year | `ProductionYear, SortName` |
| Play Count | `PlayCount, SortName` |

### 📅 Year Filter
Free-text input — type any year (e.g. `2024`) to filter content by production year.  
Example: `2024` returns **3,811 items**.

---

## 🎬 Content Structure

This Jellyfin server stores all content as the `Movie` type — including multi-episode series.

| Content | How it works |
|---------|-------------|
| **Single movie** | 1 episode, direct stream |
| **Web series / folder** | Recursively fetches child items as individual episodes |
| **Collections** | Fetches all movies within the boxset |

---

## 📺 Video Streams

Two stream options are provided for each item:

| Stream | Description |
|--------|-------------|
| **Direct Stream** | No transcoding — original file quality, fastest |
| **HLS (8Mbps)** | Transcoded HLS stream — better for slow/remote connections |

---

## 🤖 CI/CD

Every push to `main` triggers the GitHub Actions workflow which:
1. Auto-bumps the `versionCode` and `versionName`
2. Builds the signed release APK
3. Creates a GitHub Release with the APK attached
4. Pushes the APK to [salmanbappi/extensions-repo](https://github.com/salmanbappi/extensions-repo) and regenerates `index.min.json`

---

## 🏗️ Architecture

Built on the same base as **jellyfin-bijoy**, using Clean Kotlin architecture:

- **Auth**: Auto-login with hardcoded credentials, token refresh on `401`
- **Interceptor**: Transparent `Authorization: MediaBrowser ...` header injection
- **Pagination**: 20 items per page
- **Caching**: SharedPreferences for `access_token`, `user_id`, `device_id`

---

## 👤 Author

**@salmanbappi**

---

<div align="center">
<sub>Built with 🔥 for the Aniyomi/Anikku ecosystem</sub>
</div>
