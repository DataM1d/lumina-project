🌟 Lumina Project
Lumina is an AI driven 3D web visualizer that transforms long form articles into immersive spatial experiences. Using Gemini 2.5 Flash, it extracts core sentiments and styles to drive a real time Three.js particle system.

🚀 The 2025 Frontier Fix
This project is being developed during the rapid transition to the Gemini 2.5 model series. During development, I encountered persistent 404 Not Found errors when using the standard Google AI Go SDK due to backend versioning shifts and model deprecations of the 1.5/2.0 series.

The Solution: I implemented a Native HTTP Architecture. By bypassing the SDK and communicating directly with the v1beta REST endpoint, the backend achieved 100% stability. This approach is significantly more resistant to the "Model Sunset" issues affecting modern AI implementations.

✨ Core Capabilities
The engine features a Smart Extraction layer that scrapes any URL and summarizes it into a single punchy sentence. This is paired with a Visual Style Analysis module that categorizes content into energetic, calm, or dramatic profiles. Finally, the Three.js Integration drives 3D motion and color based on AI derived sentiment scores ranging from 0.0 to 1.0.

🛠️ Tech Stack
The backend is built with Go 1.24+ using a custom Native Net/HTTP client. The intelligence is powered by Google Gemini 2.5 Flash, and the frontend utilizes Three.js with JavaScript ESM for high performance 3D rendering.

📦 Installation
1. Setup Backend
Bash

cd backend
go mod tidy

2. Configure Environment 
Create a .env file in the backend directory and add your key: GEMINI_API_KEY=your_actual_key_here

3. Launch
Bash

go run ./cmd/api
⚠️ Troubleshooting the 404 Error
If you encounter a 404 error even with a valid API key, ensure you are hitting the /v1beta/ endpoint rather than /v1/. In late 2025, many projects are restricted to the beta route for Gemini 2.5 Flash access. Our implementation in internal/ai/gemini.go handles this routing automatically.
