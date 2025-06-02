# SIMBAD_VIEWER
SIMBAD VIEWER is a web platform for visualizing and analyzing geospatial data related to marine, agricultural, wildfire, and water quality monitoring. It provides interactive maps, layer management, and advanced tools for researchers and professionals.

![image](https://github.com/user-attachments/assets/69b4f18d-352d-4915-ae51-b7d355096fe7)

![image](https://github.com/user-attachments/assets/94445236-16b5-4e14-ad1e-9ba8a5a09249)


# Project structure

```text
SIMBAD_VIEWER/
│
├── src/
│   ├── main/
│   │   ├── index.html                # Main landing page with product links
│   │   ├── css/
│   │   │   └── style.css             # Main styles for the landing and shared elements
│   │   ├── main_images/              # Logos and other images
│   │   ├── libs/                     # External libraries
│   │
│   ├── maritime_monitoring/
│   │   ├── mar_mon.html              # Maritime Monitoring viewer
│   │   ├── css/
│   │   │   └── mar_mon.css           # Maritime Monitoring specific styles
│   │   ├── util/
│   │       └── mar_mon_layers.json   # Maritime Monitoring layers config
│   │
│   ├── marine_ecosystems/
│   │   ├── mar_eco.html              # Marine Ecosystems viewer
│   │   ├── comparison_layers.html    # Marine Ecosystems comparison layers viewer
│   │   ├── css/
│   │   │   └── mar_eco.css           # Marine Ecosystems specific styles
│   │   ├── util/
│   │       └── mar_eco_layers.json   # Marine Ecosystems layers config
│   │
│   ├── water_quality_monitoring/
│   │   ├── wat_qlty.html             # Water Quality Monitoring viewer
│   │   ├── css/
│   │   │   └── wat_qlty.css          # Water Quality specific styles
│   │   ├── util/
│   │       └── wat_qlty_layers.json  # Water Quality layers config
│   │
│   ├── wildfire_monitoring/
│   │   ├── fire_mon.html             # Wildfire Monitoring viewer
│   │   ├── css/
│   │   │   └── fire_mon.css          # Wildfire Monitoring specific styles
│   │   ├── util/
│   │       └── fire_mon_layers.json  # Wildfire Monitoring layers config
│   │
│   ├── precision_agriculture/
│   │   ├── pre_agr.html              # Precision Agriculture viewer
│   │   ├── css/
│   │   │   └── pre_agr.css           # Precision Agriculture specific styles
│   │   ├── util/
│   │       └── pre_agr_layers.json   # Precision Agriculture layers config
│
├── README.md                         # Project documentation
├── .gitignore                        # Git ignore file
```
# Download

$ git clone https://github.com/AleksandarAleksandrov11/SIMBAD_VIEWER.git

# How to Run the Project

### Option 1: Open Directly in Browser (no server)

1. Download or clone the repository.
2. Open the file `src/main/index.html` with your web browser (e.g. double-click it).
3. Click on any product to access its dedicated viewer.

> ⚠️ Some features (like loading JSON files or using Leaflet layers) might **not work correctly** without a local server due to browser security restrictions.

---

### Option 2: Use a Local Server

#### -With Node.js (`http-server`)
If you have Node.js and npm installed:

1. Open a terminal in the project folder.
2. 2. Install `http-server` globally (only once):
   
```bash
npm install -g http-server
```
Start the server from the src/main folder:

```bash
cd src/main

http-server
```
Open the URL shown in the terminal (usually http://localhost:8080) in your browser.

#### -With Python (3)
If you have Python installed:

Start a simple HTTP server:

```bash
cd src/main

python -m http.server
```
Go to http://localhost:8000 in your browser.

# Main Functionalities

- **Layer Visualization**: Toggle different map layers for each product.
- **Floating Menus**: Select layers and options via floating or modal menus.
- **Export Map**: Download the current map view as an image.
- **Layer Comparison**: Use a slider to compare two layers side by side.
- **Measurement Tools**: Draw and measure distances or areas on the map.
- **Base Layer Switch**: Change between dark, light, and satellite map backgrounds.

# How to Add or Modify Layers

To add or update map layers for a specific viewer:

1. Open the corresponding JSON configuration file, located in the `util/` folder of each product (e.g., `mar_eco_layers.json` for Marine Ecosystems).
2. Add or edit entries using the following structure:
   
If water_quality_monitoring:

```json
{
  "Country": {
      "City": [
        {
          "layer": "your_workspace:your_layer_name",
          "url": "https://your-geoserver-domain/geoserver/your_workspace/wms?service=WMS&version=1.1.0&request=GetMap&layers=your_workspace:your_layer_name&bbox=minX,minY,maxX,maxY&width=768&height=673&srs=EPSG:4326&format=image/png"
        }
      ]
  }
}
```

Else:

```json
{
  "Country": {
    "City": {
      "Category": [
        {
          "layer": "your_workspace:your_layer_name",
          "url": "https://your-geoserver-domain/geoserver/your_workspace/wms?service=WMS&version=1.1.0&request=GetMap&layers=your_workspace:your_layer_name&bbox=minX,minY,maxX,maxY&width=768&height=673&srs=EPSG:4326&format=image/png"
        }
      ]
    }
  }
}
```

# License & Credits
> - Project developed by Quasar Science Resources.
> - Uses [Leaflet.js](https://leafletjs.com/) and open-source plugins.
> - Logos and images © Quasar Science Resources and partners.


