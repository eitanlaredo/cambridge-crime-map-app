# Cambridge Crime Map

An interactive visualization of 95,000+ Cambridge, MA police reports featuring geocoded crime data, neighborhood analysis, and a Plotly Dash web application.

## Overview

This project takes the publicly available Cambridge Police Department crime report dataset (2009–2024), cleans and geocodes the location data, and presents it through an interactive map and statistical visualizations. The goal is to explore spatial and categorical crime patterns across Cambridge's neighborhoods.

## Features

- **Interactive Crime Map** — Plotly Dash app displaying geocoded crime locations with clickable markers
- **Geocoding Pipeline** — Batch geocoding of 5,000+ unique addresses to latitude/longitude using Geopy and the Nominatim API
- **Neighborhood Analysis** — Crime frequency breakdowns by neighborhood and crime type
- **Data Visualizations** — Seaborn and Matplotlib charts comparing crime distributions

## Dataset

- **Source:** Cambridge Police Department public crime reports
- **Records:** ~95,000 incidents (2009–2024)
- **Features:** File Number, Date of Report, Crime Date Time, Crime Type, Reporting Area, Neighborhood, Location
- **54 unique crime types** across 13 neighborhoods

## Project Structure

```
├── app.py                        # Plotly Dash interactive map application
├── EDA.ipynb                     # Exploratory data analysis and cleaning
├── visualization.ipynb           # Seaborn/Matplotlib crime analysis charts
├── map.ipynb                     # Folium map prototype
├── Crime.csv                     # Original dataset
├── Crime_with_coordinates.csv    # Geocoded unique locations
├── Merged_Crime_Data.csv         # Full dataset with lat/long joined
└── merged.csv                    # Final merged output
```

## Process

1. **Cleaning** — Removed admin errors, handled null values in Crime Date Time, Reporting Area, and Neighborhood columns
2. **Geocoding** — Extracted unique addresses, geocoded via Nominatim with rate limiting, then merged coordinates back to the full dataset
3. **Analysis** — Crime frequency by neighborhood (highest: Cambridgeport at 14,496; lowest: Strawberry Hill at 1,586) and by crime type
4. **Visualization** — Built interactive Dash map and static charts for neighborhood/crime comparisons

## Tools & Libraries

- **Pandas** — data manipulation
- **Plotly / Dash** — interactive web map
- **Folium** — map prototyping
- **Geopy** — geocoding addresses to coordinates
- **Seaborn / Matplotlib** — statistical visualizations
