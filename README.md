🤖 Private AI Hub (Qwen Edition)
A high-performance, privacy-first Progressive Web App (PWA) designed to run Large Language Models (LLMs) entirely in your browser. This version is specifically optimized for legacy hardware and low-RAM environments.

✨ Key Features
Local Inference: AI processing happens on your machine. No data leaves your browser.

Legacy Support: Optimized for systems with NVIDIA GeForce 210 GPUs and 3GB RAM.

Persistent History: Automatically saves your chats locally using Dexie.js (IndexedDB).

Qwen Integration: Powered by the Qwen1.5-0.5B-Chat model for smart, efficient responses.

PWA Ready: Installable on desktop and mobile for an app-like experience.

🛠️ Hardware-Specific Optimizations
This app includes specialized "Bulletproof" logic to run on older hardware:

Forced WASM Engine: Bypasses the eglCreateContext error on older GPUs by using the CPU (WebAssembly) for all AI math.

4-Bit Quantization (q4): Compresses the model from ~500MB to ~150MB, ensuring it fits within the strict 3GB RAM limit.

Security Bypass: Uses env.allowLocalModels = false to fix the "Unauthorized access" network errors common in PWA environments.

🚀 Getting Started
Prerequisites
Browser: Google Chrome (latest version recommended).

Secure Context: Must be hosted on https:// (e.g., GitHub Pages) or http://localhost.

Installation
Clone or Download this repository.

Upload the files to a GitHub repository.

Go to Settings > Pages and enable deployment from your main branch.

Open the generated https:// link.

⚠️ Troubleshooting
"Unauthorized access to tokenizer.json"
If you see this error, it means the browser is blocking the network request to Hugging Face.

Check the URL: Ensure you are not opening the file via file:///C:/.... It must be hosted on GitHub Pages.

Clear Cache: Open DevTools (F12) -> Application tab -> Storage -> Clear site data.

App is slow or crashing
Ensure no other heavy tabs (like YouTube) are open. With 3GB of RAM, memory is a shared resource.

The first load may take 1-2 minutes as it downloads the 150MB model to your browser cache.

📦 Built With
- Browser-based AI engine.

- Minimalist wrapper for IndexedDB.

- The underlying LLM.

Created as a high-efficiency solution for legacy hardware AI interaction.
