# SIMBAD VIEWER
SIMBAD VIEWER is a web platform for visualizing and analyzing geospatial data related to marine, agricultural, wildfire, and water quality monitoring. It provides interactive maps, layer management, and advanced tools for researchers and professionals.

![image](https://github.com/user-attachments/assets/69b4f18d-352d-4915-ae51-b7d355096fe7)

![image](https://github.com/user-attachments/assets/94445236-16b5-4e14-ad1e-9ba8a5a09249)


# Project Structure

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
│   │
│   ├── marine_ecosystems/
│   │   ├── mar_eco.html              # Marine Ecosystems viewer
│   │   ├── comparison_layers.html    # Marine Ecosystems comparison layers viewer
│   │   ├── css/
│   │   │   └── mar_eco.css           # Marine Ecosystems specific styles
│   │
│   ├── water_quality_monitoring/
│   │   ├── wat_qlty.html             # Water Quality Monitoring viewer
│   │   ├── css/
│   │   │   └── wat_qlty.css          # Water Quality specific styles
│   │
│   ├── wildfire_monitoring/
│   │   ├── fire_mon.html             # Wildfire Monitoring viewer
│   │   ├── css/
│   │   │   └── fire_mon.css          # Wildfire Monitoring specific styles
│   │
│   ├── precision_agriculture/
│   │   ├── pre_agr.html              # Precision Agriculture viewer
│   │   ├── css/
│   │   │   └── pre_agr.css           # Precision Agriculture specific styles
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

> ⚠️ Some features might **not work correctly** without a local server due to browser security restrictions.

---

### Option 2: Use a Local Server

#### -With Node.js (`http-server`)
If you have Node.js and npm installed:

1. Open a terminal in the project folder.
2. Install `http-server` globally (only once):
   
```bash
npm install -g http-server
```
Start the server from the src/main folder:

```bash
cd SIMBAD_VIEWER\src

http-server
```
Open the URL shown in the terminal (usually http://localhost:8080) in your browser.

#### -With Python (3)
If you have Python installed:

Start a simple HTTP server:

```bash
cd SIMBAD_VIEWER\src

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

# Technologies and Libraries Used

### Web Mapping and Visualization

- **[Leaflet.js](https://leafletjs.com/)**  
  JavaScript library for building interactive web maps.
- **[Leaflet Draw](https://github.com/Leaflet/Leaflet.draw)**  
  Plugin for drawing and editing shapes like polygons, polylines, and rectangles on the map.
- **[Leaflet MiniMap](https://github.com/Norkart/Leaflet-MiniMap)**  
  Displays a small overview map in a corner of the main map.
- **[Leaflet.browserPrint](https://github.com/Igor-Vladyka/leaflet.browser.print)**  
  Enables users to print the map directly from the browser.
- **[Leaflet.Locate](https://github.com/domoritz/leaflet-locatecontrol)**  
  Adds a button to show the user's current location on the map.
- **[Leaflet.MousePosition](https://github.com/ardhi/Leaflet.MousePosition)**  
  Displays the geographic coordinates of the mouse pointer.
- **[Leaflet.Fullscreen](https://github.com/Leaflet/Leaflet.fullscreen)**  
  Allows toggling the map to fullscreen mode.
- **[Leaflet.GeometryUtil](https://github.com/makinacorpus/Leaflet.GeometryUtil)**  
  Provides tools for measuring areas and distances on the map.

### Geospatial Data Services

- **[GeoServer](https://geoserver.org/)**  
  Open-source server for sharing and publishing geospatial data using open standards.
- **WMS (Web Map Service)**  
  Standard protocol for serving georeferenced map images over the internet.
  - `GetCapabilities`: Retrieves metadata including available layers and styles.

### Web Development Stack

- **HTML5, CSS3, JavaScript**  
  Core technologies for the UI and logic of the web application.
- **Fetch API**  
  Used to retrieve WMS metadata (`GetCapabilities`) and other remote resources.
- **DOMParser API**  
  Converts raw XML into a navigable DOM structure for further data processing.
   
# License & Credits
> - Project developed by [Quasar Science Resources](https://quasarsr.com/).
> - Uses [Leaflet.js](https://leafletjs.com/) and open-source plugins.
> - Logos and images © Quasar Science Resources and partners.
