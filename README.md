# Hotwire Turbo Example

A simple example demonstrating Hotwired Turbo frames for navigation between pages.

## Features

- Two endpoints with similar HTML structure
- Navigation between pages using Turbo frames
- Current page link is grayed out

## Setup and Run

1. Create and activate a virtual environment using UV:
   ```
   uv venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

2. Install the dependencies:
   ```
   uv pip install -r requirements.txt
   ```

3. Run the Flask application:
   ```
   python app.py
   ```

4. Open your browser and go to:
   ```
   http://localhost:5000/
   ```

## Troubleshooting

If you encounter an error like `ImportError: cannot import name 'url_quote' from 'werkzeug.urls'`, make sure you're using the exact versions specified in requirements.txt. The app requires Flask 2.0.1 with Werkzeug 2.0.3.

## How it Works

This example uses Hotwire Turbo frames to handle navigation between pages without full page reloads.

Each page contains:
- A `<turbo-frame>` with the ID "main-content"
- Two navigation links within the frame
- The current page's link is disabled and grayed out

When clicking a link within a Turbo frame, Turbo will only replace the content of the frame instead of loading the entire page, resulting in a smoother user experience. 