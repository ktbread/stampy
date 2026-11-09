# Stampy 打卡

A playful, illustrated travel 打卡 site. Pick a city stamp, explore an illustrated map of what people recommend (see / eat / drink / do), take a short quiz to filter it to what you're into, and check spots off with your own photo. Each check-in gets postmarked into your stamp book with a mood sticker.

First city: **Hong Kong**.

## What's in v1

- **Stamp wall** (`#wall`): one stamp per city. Hong Kong is open; others are "next trip?" outlines. Your collected stamps and mood stickers live below.
- **Hong Kong map** (`#map`): an illustrated map with 10 areas and about 50 recommendations. Hover (or tap) an area to see them. Day / golden hour / night switch.
- **Quiz** (`#quiz`): 5 quick questions give you a travel type (for example "Ridge Chaser") and filter the map.
- **打卡**: upload a photo, optionally pick a mood sticker and a short note. Photos stay as you took them (polaroids on the map, a neutral lightbox). Only the stamp cover can be "cartoon-ified".
- **My traveller** (`#me`): a simple avatar that walks around the map.

Everything is one file, `index.html`, with no build step. Check-ins are saved in your browser's local storage, so they stay on your device only.

## Run it on your computer

You only need a browser.

1. Clone the repo: `git clone https://github.com/ktbread/stampy.git` and `cd stampy`.
2. Start a tiny local web server (Python comes with macOS):
   ```
   python3 -m http.server 8000
   ```
3. Open http://localhost:8000 in your browser. Refresh after each change.

(You can also just double-click `index.html`, but a local server behaves more like the real site.)

## Changing it with Claude Code

1. Install Claude Code: see https://code.claude.com/docs (the quickstart has a one-line installer).
2. In your terminal, `cd` into this folder and run `claude`.
3. Ask for changes in plain words, for example:
   - "Add a new recommendation to Sai Kung: Ham Tin beach, tags nature and chill."
   - "Make the mood stickers bigger on phones."
   - "Add Taipei as a second city."
4. Keep the server from step 2 running in another terminal tab and refresh the browser to see changes.
5. When you're happy, ask Claude to commit and push, or run `git add -A && git commit -m "your message" && git push`.

## Where things live in `index.html`

- `AREAS`: the map areas and their recommendations (type, name, note, tags).
- `MOODS`: the mood sticker set.
- `QUESTIONS` and `PERSONA`: the quiz and the travel types.
- `buildMapSVG()`: the illustrated map drawing.
- `avatarSVG()`: the little traveller.
