# FoodSnap 📸🍳

**Cook with what you have.** FoodSnap is a cross-platform mobile app (iOS & Android) that turns a photo of your ingredients into real recipes you can cook right now.

Snap what's in your fridge → AI suggests recipes → start cooking.

## How it works

1. **Snap or upload** a photo of your ingredients — native camera on device, file upload on web.
2. **Edit the detected ingredients** — add, remove or adjust the list.
3. **Get AI recipe suggestions** powered by Gemini, matched to exactly what you have.
4. **Open any recipe** for ingredients, steps and an AI-generated dish photo.

## Features

- 📷 Native camera capture via Capacitor (with web fallback)
- 🤖 Recipe generation with Google Gemini 1.5 Flash
- 🖼️ AI-generated dish imagery
- 🧂 Ingredient editor — fine-tune what the AI works with
- 📱 One codebase for web, iOS and Android

## Tech stack

| Layer | Technology |
|---|---|
| UI | React 19, TypeScript |
| Build | Vite 6 |
| Mobile | Capacitor 7 (`@capacitor/camera`, `@capacitor/core`) |
| AI | Google GenAI SDK (`gemini-1.5-flash`) |

## Run it

**Requirements:** Node.js 20+, a Gemini API key.

```bash
npm install
```

Create a `.env` file with your key:

```bash
API_KEY=your_gemini_api_key
```

Run on web:

```bash
npm run dev
```

### Build the Android app

```bash
npm run build
npx cap sync android
```

Then open the `android/` folder in Android Studio to run it on a device or emulator. (iOS works the same way with `npx cap add ios`.)

## Project structure

```
├── App.tsx                    # app entry + screens
├── components/                # ImageUploader, IngredientEditor, RecipeCard, RecipeDetailView, …
├── services/geminiService.ts  # Gemini prompts: ingredient detection → recipes
├── types.ts                   # Ingredient, Recipe, UserPreferences
├── android/                   # native Android shell (Capacitor)
└── capacitor.config.ts        # appId com.jooelmortees.app
```

## Related

- **[FoodSnap](https://github.com/jooelmortees/FoodSnap)** — the original web version.

## License

Proprietary, source-available. See [`LICENSE`](LICENSE).
