# My Daily Routine

A personalised daily routine tracker built as a Progressive Web App (PWA). Designed to be installed on your iPhone home screen and used like a native app — no App Store required.

Built around a brain health routine to improve memory, focus, and reduce mindless scrolling.

---

## Features

- **Personalised onboarding** — prompts for your name on first launch and remembers it across sessions
- **Daily task dashboard** — tasks grouped by Morning, Midday, Evening, and Sleep with a live progress bar
- **Tap to complete** — tap any task card to mark it done, with a timestamp recorded
- **Routine manager** — add, view, and delete tasks at any time
- **Daily summary** — see completed vs missed tasks at a glance
- **AI-powered day summary** — generates a personalised end-of-day reflection using the Claude API
- **Persistent storage** — tasks and daily logs saved to localStorage, tasks reset each new day
- **Mobile-first design** — built for iPhone with safe area support and a native-feeling bottom nav

---

## Tech Stack

- Vanilla HTML, CSS, and JavaScript — zero dependencies, zero build step
- Progressive Web App (PWA) — installable on iOS via Safari's "Add to Home Screen"
- [Claude API](https://www.anthropic.com/) (`claude-sonnet-4-20250514`) for AI summary generation
- Google Fonts — DM Sans + DM Serif Display
- localStorage for all persistent data

---

## Getting Started

### 1. Deploy

No code changes needed. Just deploy the file as-is.

The simplest option is [Netlify Drop](https://app.netlify.com/drop):

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Rename `focus-improvement-routine.html` to `index.html`
3. Drag and drop it onto the page
4. Netlify gives you a live URL instantly — no account needed

Other options: GitHub Pages, Vercel, Cloudflare Pages, or any static host.

### 2. First launch — enter your name and API key

When you open the app for the first time it will walk you through two steps:

1. **Your name** — used to personalise the greeting and AI summary
2. **Your Anthropic API key** — needed for the AI daily summary feature. Get one at [console.anthropic.com](https://console.anthropic.com). It starts with `sk-ant-`. You can skip this step and add it later.

Both are saved to your browser's localStorage and never sent anywhere except the Claude API.

### 3. Install on iPhone

1. Open your live URL in **Safari** on your iPhone
2. Tap the **Share** button (box with arrow at the bottom)
3. Scroll down and tap **Add to Home Screen**
4. Tap **Add**

The app will appear on your home screen and open full-screen like a native app.

---

## Default Tasks

The app comes pre-loaded with a brain health routine:

| Time | Task | Category |
|------|------|----------|
| 7:00 am | Drink a full glass of water | Morning |
| 7:02 am | Morning brain journal | Morning |
| 7:10 am | Morning walk outside | Morning |
| 12:00 pm | Struggle window | Midday |
| 12:30 pm | Instagram batch 1 | Midday |
| 7:00 pm | Evening walk / exercise | Evening |
| 8:00 pm | Instagram batch 2 | Evening |
| 10:00 pm | Daily recall | Evening |
| 10:30 pm | Screens off | Sleep |

You can add, modify, or delete any tasks from the Routine tab inside the app.

---

## Project Structure

```
.
└── index.html    # The entire app — HTML, CSS, and JS in a single file
```

---

## Customisation

- **Change the default tasks** — edit the `DEFAULT_TASKS` array in the script section of `index.html`
- **Change colours** — all colours are CSS variables in the `:root` block at the top of the `<style>` section
- **Change the AI summary prompt** — find the `generateSummary()` function and edit the `prompt` string

---

## Privacy

All data (name, API key, tasks, daily logs) is stored locally in your browser's localStorage and never leaves your device, except for the Claude API call when you generate a summary — which sends only your task completion data for that day to Anthropic's servers. Your API key is stored locally and used only for that request.

---

## License

MIT — free to use and modify for personal projects.
