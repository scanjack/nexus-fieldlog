# 🦇 NEXUS Field Log

> **Citizen Science · Bio-Akustik & Mikroklima · Interaktive Mess-Dashboards**  
> **Citizen Science · Bio-Acoustics & Microclimate · Interactive Measurement Dashboards**

---

## 🇩🇪 Deutsch

### Was ist NEXUS?

NEXUS ist ein selbst entwickeltes mobiles Messsystem für die Citizen-Science-Feldforschung im Bereich Fledermaus-Bio-Akustik und Mikroklima. Es erfasst gleichzeitig Umweltdaten, GPS-Position und Ultraschall-Signale in fünf Frequenzbändern — kompakt, robust und für den Außeneinsatz optimiert.

### Hardware

| Komponente | Funktion |
|---|---|
| **SEEED XIAO ESP32S3 Sense** | Mikrocontroller, WLAN, Verarbeitung |
| **BME680** | Temperatur, Luftfeuchte, Luftdruck, Gas-Widerstand (VOC/IAQ) |
| **AIR530** | GPS-Empfänger (Position, Höhe, Satelliten, HDOP) |
| **SparkFun SEN-15901** | Wetterstation (Wind, Böen, Windrichtung, Niederschlag) |
| **5-Kanal Ultraschall-Frontend** | Amplitudenmessung bei 20k / 40k / 55k / 80k / 110k Hz |

### Datenformat — CSV-Spalten

Jede Messsession erzeugt eine CSV-Datei mit 2-Sekunden-Intervall:

| Spalte | Einheit | Beschreibung |
|---|---|---|
| `Date` | TT.MM.JJJJ | Datum der Messung |
| `Time` | HH:MM:SS | Uhrzeit (Lokalzeit) |
| `Lat` / `Lon` | Dezimalgrad | GPS-Koordinaten |
| `Alt` | m | GPS-Höhe über NN |
| `Sats` | — | Anzahl empfangener Satelliten |
| `HDOP` | — | Horizontale GPS-Genauigkeit (kleiner = besser) |
| `Temp` | °C | Lufttemperatur (BME680) |
| `Hum` | % rel. | Relative Luftfeuchte (BME680) |
| `DewPoint` | °C | Taupunkt (berechnet) |
| `Pres` | hPa | Luftdruck (BME680) |
| `Gas` | kΩ | Gas-Widerstand BME680 (VOC-Indikator) |
| `Bewolkung` | Okta 0–8 | Bewölkungsgrad (manuell) |
| `Wind_Avg_ms` | m/s | Durchschnittliche Windgeschwindigkeit |
| `Wind_Gust_ms` | m/s | Böengeschwindigkeit |
| `Wind_Dir` | Himmelsrichtung | Windrichtung (textuell) |
| `Wind_Dir_deg` | ° | Windrichtung in Grad |
| `Rain_mm` | mm | Niederschlagsmenge |
| `Modus` | — | Betriebsmodus (`Mobil` / `Stationär`) |
| `a20k_Low` | V | Ultraschall-Amplitude 20 kHz (Low-Band) |
| `a40k_Mid` | V | Ultraschall-Amplitude 40 kHz (Mid-Band) |
| `a55k_High` | V | Ultraschall-Amplitude 55 kHz (High-Band) |
| `a80k_FM` | V | Ultraschall-Amplitude 80 kHz (FM-Rufe) |
| `a110k_CF` | V | Ultraschall-Amplitude 110 kHz (CF-Rufe) |

### Sessions

Jede Messsession liegt als eigenständiges Verzeichnis unter `sessions/` mit zugehörigem interaktivem HTML-Dashboard und den Rohdaten als CSV.

### Lizenz

MIT License — siehe [LICENSE](LICENSE)  
Messdaten und Inhalte stehen zusätzlich unter [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

---

## 🇬🇧 English

### What is NEXUS?

NEXUS is a custom-built mobile measurement system for citizen science field research in bat bio-acoustics and microclimate monitoring. It simultaneously captures environmental data, GPS position, and ultrasound signals across five frequency bands — compact, robust, and optimised for outdoor use.

### Hardware

| Component | Function |
|---|---|
| **SEEED XIAO ESP32S3 Sense** | Microcontroller, WiFi, processing |
| **BME680** | Temperature, humidity, air pressure, gas resistance (VOC/IAQ) |
| **AIR530** | GPS receiver (position, altitude, satellites, HDOP) |
| **SparkFun SEN-15901** | Weather station (wind speed, gusts, direction, precipitation) |
| **5-channel ultrasound frontend** | Amplitude measurement at 20k / 40k / 55k / 80k / 110k Hz |

### Data Format — CSV Columns

Each measurement session produces a CSV file at 2-second intervals:

| Column | Unit | Description |
|---|---|---|
| `Date` | DD.MM.YYYY | Date of measurement |
| `Time` | HH:MM:SS | Local time |
| `Lat` / `Lon` | Decimal degrees | GPS coordinates |
| `Alt` | m | GPS altitude above sea level |
| `Sats` | — | Number of satellites received |
| `HDOP` | — | Horizontal GPS accuracy (lower = better) |
| `Temp` | °C | Air temperature (BME680) |
| `Hum` | % rel. | Relative humidity (BME680) |
| `DewPoint` | °C | Dew point (calculated) |
| `Pres` | hPa | Air pressure (BME680) |
| `Gas` | kΩ | Gas resistance BME680 (VOC indicator) |
| `Bewolkung` | Okta 0–8 | Cloud cover (manual entry) |
| `Wind_Avg_ms` | m/s | Average wind speed |
| `Wind_Gust_ms` | m/s | Gust speed |
| `Wind_Dir` | Cardinal direction | Wind direction (text) |
| `Wind_Dir_deg` | ° | Wind direction in degrees |
| `Rain_mm` | mm | Precipitation amount |
| `Modus` | — | Operating mode (`Mobil` / `Stationär`) |
| `a20k_Low` | V | Ultrasound amplitude 20 kHz (low band) |
| `a40k_Mid` | V | Ultrasound amplitude 40 kHz (mid band) |
| `a55k_High` | V | Ultrasound amplitude 55 kHz (high band) |
| `a80k_FM` | V | Ultrasound amplitude 80 kHz (FM calls) |
| `a110k_CF` | V | Ultrasound amplitude 110 kHz (CF calls) |

### Sessions

Each measurement session is stored as a standalone directory under `sessions/`, containing an interactive HTML dashboard and the raw CSV data.

### License

MIT License — see [LICENSE](LICENSE)  
Measurement data and content are additionally licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
