# STARTS JOURNEY — live news + restored articles

## What is fixed
- Restored 27 editorial articles remain in `data/db.json`.
- Homepage search is a real `<form>` with a working Search button.
- Every story has a `READ FULL STORY` page.
- Live news can be refreshed from the homepage with **REFRESH NOW**.
- Server automatically attempts a live RSS sync at startup and every 10 minutes while the server is running.
- Live stories are deduplicated by source URL/title and the cache is capped at 200 stories.
- Live stories link to the original publisher; the site does not copy a publisher's full copyrighted article.
- `GET /api/health` reports the server and article count.

## Run on Windows
1. Extract the ZIP.
2. Double-click `START-STARTS-JOURNEY.bat`.
3. Allow `npm install` the first time if Node modules are not present.
4. The site opens at `http://localhost:3000/`.

**Important:** Do not double-click `public/index.html`. That bypasses the Node server and can show a Windows `Index of C:\` page.

## Automatic news
The server uses Google News RSS search feeds for Bollywood/celebrity and Indian cricket. It fetches headlines and available summaries and stores them locally. The original publisher URL is kept as `sourceUrl`.

Automatic updates happen only while this Node server is running. On a deployed server, keep the process running with a process manager/hosting service.

## API smoke checks
- `http://localhost:3000/api/health`
- `http://localhost:3000/api/content`
- `http://localhost:3000/api/sync-news`
