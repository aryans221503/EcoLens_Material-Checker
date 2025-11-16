DEMO VIDEO DRIVE LINK : (https://drive.google.com/file/d/1X-4x4hMMXZmo-WtEs5-YILN06YwL78Ch/view?usp=drive_link)
DEPLOYED PROJECT LINK : (https://aryans221503.github.io/EcoLens_Material-Checker/)

# EcoLens_Material-Checker
EcoLens is a smart web application that uses generative AI to analyze and classify the environmental sustainability of materials from a single image.  Users can upload a photo or capture a new one with their device camera, and the app's AI-driven backend will instantly identify the material and provide a detailed report on its environmental impact.
Core Problem

It's often difficult for consumers, designers, or hobbyists to determine if a material is eco-friendly just by looking at it. Is that plastic compostable bioplastic or petroleum-based? Is that wood from a sustainable source or a processed composite? EcoLens aims to bridge this knowledge gap by providing an instant, accessible analysis.

How It Works

Image Input: The user provides an image using either the "Upload File" button or the "Capture Image" button, which activates their device's camera.

AI Analysis: The image is converted to a base64 string and sent to the Google Gemini API (gemini-2.5-flash-preview-09-2025) along with a specialized system prompt.

Expert Persona: The prompt instructs the AI to act as a "sustainability expert," analyzing the material's visual properties (texture, form, color, processing evidence) to determine its classification.

Structured Response: The app requests a specific JSON-formatted response from the API, which includes:

prediction: "Eco-Friendly" or "Non-Eco-Friendly"

confidence: A numerical score (0.60 - 0.99)

reasoning: A text explanation for the classification.

Dynamic Results: The front-end parses this JSON and dynamically updates the UI. The results card changes color (green for Eco-Friendly, red for Non-Eco-Friendly) and displays the confidence bar and detailed reasoning.

Key Features

AI-Powered Classification: Leverages the Gemini multi-modal vision model to understand and classify materials.

Dual Image Input: Supports both static file uploads (<input type="file">) and live camera capture (navigator.mediaDevices.getUserMedia).

Detailed Reasoning: Provides not just a label, but an "expert" explanation for why a material is classified a certain way.

Dynamic UI: A clean, responsive interface built with Tailwind CSS that provides instant visual feedback.

Single-File Application: The entire application (HTML, CSS, and JavaScript) is self-contained in a single index.html file for easy deployment.

Resilient API Calls: Implements exponential backoff to handle API rate limits gracefully.

Technology Stack

Front-End: HTML5, CSS3, modern JavaScript (ES6+)

Styling: Tailwind CSS (loaded via CDN)

Core AI: Google Gemini API (gemini-2.5-flash-preview-09-2025)

Web APIs:

FileReader API (for converting images to base64)

navigator.mediaDevices.getUserMedia (for camera access)

Fetch API (for communicating with the Gemini API)

Authentication (Optional): Firebase Authentication (used in the original environment for API access, setup for anonymous sign-in).
