# Hotwire Cache Repro

The [Turbo handbook](https://turbo.hotwired.dev/handbook/building#understanding-caching) states:

> When navigating by history (via Restoration Visits), Turbo Drive will restore the page from cache without loading a fresh copy from the network, if possible.

This behavior works as expected:

[Kapture 2025-04-03 at 11.15.36.webm](https://github.com/user-attachments/assets/b04c2456-91b1-49cd-aff1-7b8886e11266)


> Otherwise, during standard navigation (via Application Visits), Turbo Drive will immediately restore the page from cache and display it as a preview while simultaneously loading a fresh copy from the network. This gives the illusion of instantaneous page loads for frequently accessed locations.

This behavior does not work as expected:

[Kapture 2025-04-03 at 11.16.18.webm](https://github.com/user-attachments/assets/62493760-f5db-4eed-9038-b1ac322fdb82)


1. `/page1` loaded after a second (expected)
2. `/page2` navigated to after a second (expected)
3. `/page1` clicked again. No preview is shown and the page is loaded after a second (not expected)

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
