# 📱 Video Frame Capturer – Pro

An advanced, high-fidelity, and lightning-fast developer utility to capture precise, frame-accurate screenshots from video files, apply beautiful mobile overlays, write instructions, and export structured step-by-step documentation.

---

## 🌟 Key Features

### 1. Lightning-Fast Frame Extraction & Paint Engine
- **Deterministic Seek & Decode**: Built with a custom playback-override engine using play-pause pulses combined with a dual `requestAnimationFrame` loop. This bypasses browser frame latency and ensures you capture crisp, non-blurry, fully-painted UI images immediately, even during complex CSS animations or high-motion transitions.
- **Debounced Interactive Synchronization**: Edit timestamps inline on any step card; the app automatically debounces (350ms) and pulls the exact frame in real-time, letting you verify its visual quality on the fly.
- **Canvas-Level Precise Cropping**: Dynamically adjust frame cropping ratios to fit standard mobile or desktop dimensions.

### 2. Beautiful Mobile Device Overlays
- **Realistic UI Containers**: Choose to wrap frame captures with high-fidelity mobile borders including mock speaker notches, realistic shadows, glass-reflection glares, and side button reliefs.
- **Adaptive Canvas**: Respects orientation and proportions dynamically using standard HTML5 Canvas image placement.

### 3. Comprehensive Documentation & Exports
- **Interactive Instruction Panels**: Add custom visual feedback labels, step names, and user action steps for each capture.
- **One-Click Exports**: Download all steps as high-quality PNGs, or generate a structured Markdown guide packaged cleanly alongside raw screenshots in a single compiled `.zip` file.

---

## 🚀 GitHub Automation Pipelines

This repository is equipped with **GitHub Actions workflows** to make project maintenance completely automated:

### 📥 1. Auto-ZIP Extraction Workflow (`extract-zip.yml`)
If you have a local build or a folder structure exported as a ZIP file, you don't need to manually extract or sort files.
- **How it works**: Simply commit or upload any `.zip` file directly to the root of your `main` or `master` branch.
- **The Magic**: The GitHub Actions runner immediately detects the `.zip` archive, unzips its contents with full overwrite (`unzip -o`), deletes the original `.zip` file, and commits the clean, extracted directory back to your repository automatically.

### 🌐 2. Auto-Deployment to GitHub Pages (`deploy.yml`)
- **How it works**: Every time a change is pushed to the repository (either by you or by the ZIP extractor bot), this workflow automatically runs.
- **Outcome**: It installs packages, compiles the React SPA via Vite production settings, configures custom client-side router fallbacks (`404.html`), and deploys your live web tool to the `gh-pages` branch.

---

## 🛠️ Local Development & Quick Start

Follow these steps to run the Video Frame Capturer on your local machine:

### Prerequisites
- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- `npm` (packaged automatically with Node)

### Step-by-Step Installation

1. **Clone the Repository**:
   ```bash
   git clone <your-repository-url>
   cd <your-repository-name>
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   ```

3. **Start the Development Server**:
   ```bash
   npm run dev
   ```
   Open your browser and navigate to `http://localhost:3000` to start capturing frames!

4. **Compile Production Build**:
   To bundle the client-side SPA and compile the full-stack server entry-point:
   ```bash
   npm run build
   ```

---

## 📁 Project Structure

```text
├── .github/workflows/
│   ├── deploy.yml          # GitHub Pages automated build & release
│   └── extract-zip.yml     # Auto-ZIP extractor and branch cleaner
├── src/
│   ├── components/
│   │   ├── StepCard.tsx    # Responsive capture card & inline editor
│   │   ├── BuilderTab.tsx  # Dynamic timeline editor
│   │   └── ...
│   ├── App.tsx             # Primary layout, seek timeline, and state manager
│   └── main.tsx            # React application entry point
├── package.json            # Scripts and dependencies
└── README.md               # You are here!
```

---

## 🎨 Visual Identity & Aesthetic Guidelines

- **Typography**: Paired with modern "Inter" (sans-serif) readability and "JetBrains Mono" for timestamp tracking.
- **Theme**: Includes a deep-space slate dark canvas with custom glowing active states to allow fatigue-free use during prolonged video review.
