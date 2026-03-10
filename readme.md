# Freddie Freeloader — Website Setup Guide

## Files in this folder
- `index.html` — Home page (albums grid + singles list)
- `album.html` — Album page (cover, tracklist, waveform, lyrics)

---

## How to set up your site

### Step 1 — Folder structure
Create a folder on your computer called `freddie-freeloader-site` and put these files in it:

```
freddie-freeloader-site/
├── index.html
├── album.html
├── covers/
│   └── album1.jpg       ← your album cover image
└── audio/
    ├── track01.mp3
    ├── track02.mp3
    └── ...
```

### Step 2 — Add your album cover
In both `index.html` and `album.html`, find this comment:
```
<!-- Replace with: <img class="album-cover-img" src="covers/album1.jpg" alt="Album Cover"> -->
```
Delete the placeholder `<div>` below it and uncomment/add the `<img>` tag pointing to your image file.

### Step 3 — Add your tracks & lyrics
Open `album.html` in a text editor (Notepad, VS Code, etc).
Find the `TRACKS` array near the top of the `<script>` section.

Fill in each track:
```javascript
{
  title: "Your Real Song Title",
  duration: "3:42",
  file: "audio/track01.mp3",   // path to your MP3/WAV
  lyrics: `Paste your full lyrics here.
Each line on its own row.

[Chorus]
Just like Genius.com.`
},
```

### Step 4 — Update the home page
In `index.html`, update:
- Album title, year, track count, runtime in the `.album-info` div
- Your singles list (title, year, duration) in the `.singles-list` section
- Your artist name everywhere it says "Freddie Freeloader"

### Step 5 — Host it for free
**Option A — Netlify (easiest, free)**
1. Go to netlify.com → sign up free
2. Drag your entire site folder onto the Netlify dashboard
3. Done — you get a URL like `yourname.netlify.app`
4. You can connect a custom domain later

**Option B — GitHub Pages (also free)**
1. Create a free GitHub account
2. Create a new repository
3. Upload all your files
4. Go to Settings → Pages → Deploy from main branch
5. Your site will be at `yourusername.github.io/repo-name`

---

## Playing audio locally
Because of browser security, audio won't play if you just double-click the HTML file.
To test locally, use VS Code with the "Live Server" extension, or run:
```
npx serve .
```
in the folder, then open `http://localhost:3000`

---

## The "Load Audio File" button
On the album page, there's a "Load Audio File" button. This lets you manually load an MP3 from your computer directly in the browser — great for testing without a server.
