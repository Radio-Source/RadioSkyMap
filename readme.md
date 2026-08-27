

# RadioSkyMap v 0.9  
HI & 408 MHz Synchrotron Visualizer desktop software for Windows and Linux (coming soon stay tuned)

## 1. Overview

**RadioSkyMap** is an desktop application designed for radio astronomy enthusiasts and amateur astronomers. It provides a **real-time sky map **with (azimuth/elevation) overlaid with **Neutral Hydrogen (HI) emission data (Leiden/Argentine/Bonn (LAB) survey), 408 MHz synchrotron continuum maps (haslam Remazeilles 2014)**, and major celestial radio source catalogs (such as **3CR,Third Cambridge Catalogue of Radio Sources (3C Revised), Parkes PKSCAT90 - The Southern RadioSource Database**, and **GLEAM 4-Jy (G4Jy) catalog**). It also integrates seamlessly with **ASCOM-compliant telescope** mounts for automated tracking and pointing ("**GOTO**"), alongside spectral profile data acquisition from the **Leiden/Argentine/Bonn (LAB) survey** or off line local databases.

## 2. Main Interface Layout

The user interface is split into three main interactive sections:

- **Top Control Bar:** Configures your geographic coordinates (Longitude, Latitude), antenna parameters (Diameter, Frequency, Azimuth, Elevation), UTC date/time, and live synchronization mode.

- **Polar Sky Map (Left Panel):** Displays a real-time 360° horizon view with cardinal points (N, E, S, W), bright stars, solar system bodies (Sun, Moon, Jupiter), and radio overlays.

- **Spectra & ASCOM Panel (Right Panel):** Houses the spectral velocity profile graph (HI line at 1420.4 MHz) and the ASCOM telescope control hub with live telemetry.

![RadioSkyMap Gui](https://github.com/Radio-Source/RadioSkyMap/blob/main/img/radioskymap_gui0.jpg)






## 3. Key Features & Operations

### A. Geographic & Antenna Configuration

- **Location Settings:** Enter your station's **Longitude** and **Latitude** in decimal degrees. These values are automatically saved in config.ini upon editing.

- **Beamwidth Calculation (FWHM):** Based on your antenna diameter (in meters) and observation frequency (in MHz), the application automatically computes and displays the Half-Power Beamwidth using the standard formula:  
*FWHM *= 1.22 \* (λ/D)

- **Manual vs. Live Time Mode:** By default, the application runs in **Live Mode**, synchronizing with your computer's current UTC time and updating the Local Sidereal Time (LST). Changing the date/time manually via the calendar picker switches the app to Custom Mode, which can be reverted by clicking **GO LIVE**.


### B. Polar Sky Map & Overlays

- **Interactive Layers:** Using the overlay checkboxes on the map, you can toggle:

  - *HI Map (1420 MHz):* Neutral hydrogen gas distribution from survey data.

  - *408 MHz Map:* Synchrotron continuum background radiation.

  - *Radio Sources:* High-flux cosmic sources (e.g., Cygnus A, Cassiopeia A, Taurus A) filtered dynamically by a user-defined flux threshold (in Jansky / Jy).  
  
\* Slowdowns prior to display are sometimes observed, due to data calculations and loading.

- **Mouse Interaction:** Clicking anywhere on the polar map instantly updates the antenna target coordinates (Azimuth/Elevation) and queries database information if a celestial object is nearby.







### C. Spectral Profile Fetching ("Fetch Lab Profile")

- By clicking the **Fetch Lab Profile** button, the app queries the Bonn HI survey server or falls back to a local SQLite database (lab\_sky\_survey.db).

- It plots the brightness temperature (Tb) against radial velocity (km/s) and provides secondary axes for frequency and flux density (Jy).

### D. ASCOM Telescope Integration

- If you have a mount controllable via the ASCOM standard, and you have already configured and successfully tested the **ASCOM Hub**, you can use this software feature to control your mount via RadioSkyMap.  
You must first set up your mount and its electronics. 

- **Connection:** Click "**Connect ASCOM Hub**" to link the software to your ASCOM-compatible telescope driver/mount. 

- **Telemetry: **Real-time data streams include azimuth, altitude, right ascension (RA), declination (Dec), LST, hour angle (HA), tracking status, and pier side. 

- **GOTO Pointing:** Click on an object on the map and use the "**Goto**" button to automatically send the target coordinates to your telescope mount.  
The telescope mount will automatically point to the object.
Pierre Terrier  August 2026    RadioSkyMap v 0.9

![RadioSkyMap Gui](https://github.com/Radio-Source/RadioSkyMap/blob/main/img/radioskymap_gui3.jpg)
# RadioSkyMap   


Pierre Terrier  August 2026    RadioSkyMap v 0.9

