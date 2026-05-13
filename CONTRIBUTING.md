# Contributing to Late Meet

First off, thank you for considering contributing to Late Meet! It's people like you that help make this a great tool for meeting productivity and privacy.

## Prerequisites

Before you begin, ensure you have the following:

* **Node.js**: Version 18 or higher.
* **Google Chrome**: Latest stable version with Developer Mode enabled.
* **API Keys**: An [OpenAI API Key](https://platform.openai.com/api-keys) and optionally an [ElevenLabs API Key](https://elevenlabs.io/) for transcription.

## How to Fork and Clone

1. Fork the project on GitHub by clicking the **Fork** button in the top right corner.
2. Clone your fork locally:
   ```bash
   git clone https://github.com/<your-username>/Late-Meet.git
   cd Late-Meet
   ```
3. Add the original repository as an upstream remote:
   ```bash
   git remote add upstream https://github.com/shouri123/Late-Meet.git
   ```

## How to Run Locally

1. Install all dependencies:
   ```bash
   npm install
   ```
2. Build the extension:
   ```bash
   npm run build
   ```
3. Load the extension in Chrome:
   - Open Chrome and navigate to `chrome://extensions/`
   - Enable **Developer mode** (top right toggle)
   - Click **Load unpacked** and select the **`dist/`** directory
4. Configure API keys:
   - Click the extension icon → **Options**
   - Enter your ElevenLabs and OpenAI API keys

## Project Structure

The main source code is in the `src/` directory:

```text
src/
├── background.ts        # Service worker — central state manager, AI coordination
├── offscreen.ts         # Audio capture engine via Chrome tabCapture API
├── offscreen.html       # Hidden offscreen document for audio processing
├── content.ts           # UI injector — floating buttons, late-joiner overlays
├── content.css          # Styles for injected UI elements
├── dashboard.ts         # Side panel real-time intelligence dashboard logic
├── dashboard.html       # Side panel HTML structure
├── dashboard.css        # Side panel styling
├── popup.ts             # Extension popup controls
├── popup.html           # Popup HTML structure
├── popup.css            # Popup styling
├── options.ts           # API key configuration page logic
├── options.html         # Options page HTML
├── options.css          # Options page styling
├── audioProcessing.ts   # Audio processing utilities
├── types.ts             # TypeScript type definitions
├── manifest.json        # Chrome extension manifest (MV3)
└── utils/
    └── api.js           # API helper functions
```

## How to Pick an Issue

1. Check the [Issues](https://github.com/shouri123/Late-Meet/issues) tab for open issues.
2. Look for issues labeled `good first issue` or `help wanted` if you're new to the project.
3. Comment on the issue you want to work on so others know it's being handled.
4. If you have a new idea, please open an issue to discuss it before you start coding!

## Branch Naming

Use descriptive branch names:

- `feature/add-transcript-export`
- `fix/meeting-detection-bug`
- `docs/update-setup-guide`
- `ui/improve-dark-mode`

## Pull Request Guidelines

1. **Create a new branch** for your feature or bug fix:
   ```bash
   git checkout -b feature/my-awesome-feature
   ```
2. Make your changes and commit with clear, descriptive messages.
3. Push your branch to your fork:
   ```bash
   git push origin feature/my-awesome-feature
   ```
4. Open a Pull Request from your fork to the `main` branch of the original repository.
5. Provide a detailed description. Link any relevant issues (e.g., "Fixes #12").
6. **Add screenshots** for any UI changes.
7. Wait for a review — we'll respond as soon as we can!

## How to Test Changes

1. Run the build to catch TypeScript errors:
   ```bash
   npm run build
   ```
2. Load the updated `dist/` folder in Chrome (or click the refresh icon on `chrome://extensions/`).
3. **Manually test** by joining a Google Meet and verifying the copilot functionality.
4. If adding new utility functions, write tests in a corresponding `.test.ts` file.

## Code Style

- Use **TypeScript** for all new source files.
- Follow the existing **monochromatic UI design system** (deep blacks, whites, glassmorphism).
- Use **vanilla CSS** — no CSS frameworks.
- Prefer **zero-dependency** approaches where possible.

## Need Help?

If you're stuck or have questions, feel free to open a [Discussion](https://github.com/shouri123/Late-Meet/discussions) or reach out via the issue you're working on.
