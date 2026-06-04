# Wandr — your travel friend

AI-powered conversational travel planner. Built as a single-file prototype, ready to componentize.

## What it does
- Freeform prompt entry ("Somewhere in India with my elderly parents")
- Wandr asks follow-up questions one at a time, like a friend
- Generates real destination recommendations via Claude AI
- Conversational itinerary building, duration recommendations, neighborhood picks

## Run locally (30 seconds)
Just open `index.html` in a browser. No build step, no dependencies.

> **Note:** The Claude API is called client-side in this prototype. For production, move API calls to a backend/edge function so your key is never exposed.

## Deploy to GitHub Pages
1. Create a new repo on github.com (e.g. `wandr`)
2. Push this folder:
   ```bash
   git init
   git add .
   git commit -m "initial wandr prototype"
   git remote add origin https://github.com/YOUR_USERNAME/wandr.git
   git push -u origin main
   ```
3. Go to repo Settings → Pages → Source: `main` branch → `/root`
4. Your app is live at `https://YOUR_USERNAME.github.io/wandr`

## Move to Cursor (componentize into React)
Open this project in Cursor and use this prompt to get started:

```
I have a single-file HTML/CSS/JS travel app prototype called Wandr.
Please help me convert it into a React app with:
- Vite as the build tool
- Components: App, Header, ConvoArea, MessageBubble, DestinationCards, InputArea
- The Anthropic API call moved to a Vite proxy or edge function (keep key server-side)
- Same visual design — CSS variables, colors, and layout unchanged
- TypeScript optional but welcome

Start by scaffolding the Vite project and showing me the component structure.
```

## File structure (current)
```
wandr/
└── index.html    ← everything lives here for now
└── README.md
```

## Design tokens
| Token | Value | Usage |
|---|---|---|
| `--sand` | `#F5EFE6` | App background |
| `--linen` | `#FDFAF6` | Cards, header, input |
| `--terra` | `#C4521A` | Primary — user bubbles, CTA, Wandr avatar |
| `--terra-2` | `#E8845A` | Hover states |
| `--teal` | `#1A7B6B` | Success, best-fit highlights |
| `--gold` | `#B07D20` | Warnings, visa strip |
| `--ink` | `#1A1510` | Primary text |
| `--ink-2` | `#6B5C4E` | Secondary text |
| `--ink-3` | `#A89484` | Tertiary / placeholder |

## Destination card color pairs
Each destination card gets a unique color pair (text/bg):
- Blue: `#4A7FB5` / `#EBF1F8`
- Purple: `#7B5EA7` / `#F2EEF8`
- Terracotta: `#C4521A` / `#FBF0EA`
- Teal: `#1A7B6B` / `#EAF4F2`
- Gold: `#B07D20` / `#FBF3E0`

## Spec doc
Full UX spec lives in the Claude conversation where this was built.
Key decisions: anonymous-first, freeform prompt, conversational follow-ups,
2-stop cap, witty friend voice, neighborhood rec driven by itinerary clusters.

## Next steps
- [ ] Move API key to server-side
- [ ] Add itinerary editing (drag/reorder, add/remove attractions)
- [ ] Wire real Google Places API for attraction data
- [ ] Add Mapbox neighborhood map view
- [ ] Mobile polish (bottom sheet for clarifiers)
- [ ] Save trip to localStorage → prompt account creation
