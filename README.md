# IBM-Capstone-project-2023

# SpaceX Launch Records Dashboard

A interactive web dashboard built with Plotly Dash for visualizing SpaceX launch data, including success rates and payload correlations.

## Features

- **Launch Site Selection**: Dropdown menu to filter data by specific launch sites or view all sites
- **Success Rate Visualization**: Pie chart showing launch success rates
  - All sites: Distribution of successful launches across different sites
  - Individual site: Success vs Failed launches for the selected site
- **Payload Analysis**: Interactive scatter plot showing correlation between payload mass and launch success
  - Color-coded by booster version category
  - Adjustable payload range using slider control

## Data Source

The dashboard uses `spacex_launch_dash.csv` which contains historical SpaceX launch data including:
- Launch site information
- Payload mass
- Launch success/failure status (class)
- Booster version categories

## Dashboard Components

### 1. Site Selection Dropdown
- Located at the top of the dashboard
- Options: All Sites, CCAFS LC-40, CCAFS SLC-40, KSC LC-39A, VAFB SLC-4E
- Default selection: "ALL"

### 2. Success Pie Chart
- Displays launch success statistics
- Updates based on site selection
- For "ALL" sites: Shows distribution of successful launches across different sites
- For specific sites: Shows success vs failure ratio for that site

### 3. Payload Range Slider
- Interactive slider to filter payload mass range
- Range: 0 to 10,000 kg
- Step size: 1,000 kg
- Default range: Minimum to maximum payload in dataset

### 4. Payload Success Scatter Plot
- Shows relationship between payload mass and launch success
- Points colored by booster version category
- Updates based on both site selection and payload range

## Code Structure

### Main Components:
- **Data Loading**: Reads SpaceX launch data from CSV
- **Dash App Initialization**: Creates the web application framework
- **Layout Definition**: Organizes the dashboard components
- **Callbacks**: Handles interactive updates:
  - `get_pie_chart()`: Updates pie chart based on site selection
  - `get_scatter_chart()`: Updates scatter plot based on site selection and payload range

### Key Functions:
- `get_pie_chart(entered_site)`: Generates appropriate pie chart visualization
- `get_scatter_chart(entered_site, slider)`: Creates scatter plot with filtering

## Installation & Usage

1. **Prerequisites**:
   ```bash
   pip install pandas dash plotly

