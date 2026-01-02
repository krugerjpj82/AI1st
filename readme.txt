{
  "project_name": "Private_AI_Hub_Legacy_Edition",
  "optimization_target": "CPU_WASM_LOW_RAM",
  "dependencies": [
    "https://unpkg.com/dexie/dist/dexie.js",
    "https://cdn.jsdelivr.net/npm/@xenova/transformers@2.17.2"
  ],
  "configuration": {
    "transformers_env": {
      "allowRemoteModels": true,
      "useBrowserCache": true,
      "allowLocalModels": false
    },
    "model_settings": {
      "model_id": "Xenova/SmolLM2-135M-Instruct",
      "device": "wasm",
      "dtype": "q4",
      "max_new_tokens": 64
    }
  },
  "ui_components": {
    "theme": "dark_cyberpunk",
    "status_bar": "Always visible, identifies hardware as 'Legacy CPU Mode'",
    "chat_interface": "IndexedDB persistent history",
    "file_explorer": "Web File System Access API with WASM categorization"
  },
  "logic_overrides": {
    [span_1](start_span)"initialization": "Skip WebGPU detection; force WASM immediately to prevent EGL context failure[span_1](end_span).",
    [span_2](start_span)"memory_management": "Limit total model load to < 200MB to fit within 3GB system RAM[span_2](end_span).",
    "error_handling": "Redirect 403/401 network errors to an automated cache-retry loop."
  },
  "metadata": {
    [span_3](start_span)"detected_gpu": "NVIDIA GeForce 210[span_3](end_span)",
    [span_4](start_span)"detected_ram": "3GB[span_4](end_span)",
    [span_5](start_span)"d3d_feature_level": "10_1[span_5](end_span)",
    [span_6](start_span)"issue_ref": "eglCreateContext: Requested version is not supported[span_6](end_span)"
  }
}
