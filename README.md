# EdgeWatch — Advanced IoT Edge Simulator & Pipeline

EdgeWatch is a single-file IoT demo that simulates an edge device publishing telemetry, a collector that stores telemetry into SQLite, simple anomaly detection, a small REST API, OTA update simulation, and a Plotly dashboard. The project is designed to run in **Google Colab** or locally and is git-ready for GitHub.

## Files
- `edgewatch.py` — main application (single-file)
- `requirements.txt` — Python dependencies

## Features
- Sensor simulation: temperature, humidity, vibration, GPS
- MQTT publisher (simulated device), configurable broker + topic
- MQTT subscriber (collector) -> SQLite storage
- Simple anomaly detection (z-score + optional IsolationForest)
- Flask REST API (`/health`, `/telemetry/recent`, `/anomalies`, `/ota`)
- Plotly offline dashboard generator
- OTA update simulation endpoint (manifest + URL)

## Architecture

## Quick start (Google Colab)
1. Create a fresh Colab notebook.
2. Install dependencies:
```python
!pip install -r requirements.txt
%%bash
cat > edgewatch.py <<'PY'
# <paste the contents of edgewatch.py here>
PY
!python edgewatch.py --mode all --device colab-edge-001 --publish-for 120
