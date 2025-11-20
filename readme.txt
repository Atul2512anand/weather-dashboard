# 🌤️ Weather Dashboard - Public API Demo

A modern, responsive weather dashboard that demonstrates real-time data collection from public APIs using vanilla JavaScript. Features a clean glassmorphism UI design with interactive charts and live weather data.

![Weather Dashboard](https://img.shields.io/badge/Status-Live-brightgreen) ![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-yellow) ![License](https://img.shields.io/badge/License-MIT-blue)

## 🎯 Project Overview

This project showcases:
- **Real-time API Integration** - Fetches live weather data from Open-Meteo API
- **Modern UI/UX Design** - Glassmorphism effects, smooth animations, responsive layout
- **Data Visualization** - Interactive Chart.js graphs showing 24-hour temperature trends
- **Vanilla JavaScript** - No frameworks, pure client-side implementation
- **GitHub Pages Ready** - Static site, deployable in minutes

## 🚀 Live Demo

👉 **[View Live Dashboard](https://yourusername.github.io/weather-dashboard/)**

*Replace `yourusername` with your actual GitHub username*

## 📸 Screenshots

![Dashboard Preview](screenshot.png)
*Add your screenshot here*

## ✨ Features

### Core Functionality
- 🌍 **Multi-City Support** - Pre-configured cities (Delhi, Mumbai, Chennai, Kolkata, Bangalore, Hubli, Siwan)
- 📍 **Custom Coordinates** - Enter any latitude/longitude for global weather data
- 📊 **Live Statistics** - Current, average, max, and min temperatures
- 📈 **Interactive Charts** - 24-hour temperature trend visualization
- 📋 **Data Table** - Detailed hourly breakdown with weather status icons

### Technical Features
- ⚡ **100% Client-Side** - No server required, runs entirely in browser
- 🎨 **Responsive Design** - Works on desktop, tablet, and mobile
- 🌙 **Dark Mode UI** - Modern gradient background with glassmorphism
- ♿ **Accessible** - Semantic HTML, ARIA labels, keyboard navigation
- 🔒 **Secure** - HTTPS API calls, no data storage

## 🛠️ Technologies Used

| Technology | Purpose |
|-----------|---------|
| **HTML5** | Structure and semantic markup |
| **CSS3** | Styling, animations, glassmorphism effects |
| **Vanilla JavaScript** | API calls, DOM manipulation, event handling |
| **Chart.js** | Interactive temperature trend visualization |
| **Open-Meteo API** | Real-time weather data source (free, no API key) |

## 📦 Installation & Setup

### Quick Start (GitHub Pages)

1. **Fork/Clone this repository**
   git clone https://github.com/yourusername/weather-dashboard.git
   cd weather-dashboard

2. **Upload to GitHub**
   git add .
   git commit -m "Initial commit: Weather Dashboard"
   git push origin main

3. **Enable GitHub Pages**
   - Go to repository **Settings** → **Pages**
   - Source: `main` branch, `/ (root)` folder
   - Click **Save**
   - Your site will be live at `https://yourusername.github.io/weather-dashboard/`

### Local Development

1. **Clone the repository**
   git clone https://github.com/yourusername/weather-dashboard.git

2. **Open in browser**
   - Simply open `index.html` in any modern browser
   - Or use a local server:
   # Python 3
   python -m http.server 8000
   
   # Or use VS Code Live Server extension

3. **Access locally**
   - Open `http://localhost:8000` in your browser

## 📖 How to Use

### Using the Dashboard

1. **Select a City**
   - Choose from dropdown: Delhi, Mumbai, Chennai, etc.
   - Coordinates auto-populate

2. **Custom Location**
   - Enter any latitude/longitude manually
   - Example: `51.5074, -0.1278` (London)

3. **Fetch Weather Data**
   - Click "📡 Fetch Weather Data" button
   - Real-time data loads in 1-2 seconds

4. **View Results**
   - **Cards**: Current, Average, Max, Min temperatures
   - **Chart**: 24-hour temperature trend graph
   - **Table**: Hourly breakdown with status icons

### City Coordinates Reference

| City | Latitude | Longitude |
|------|----------|-----------|
| Delhi | 28.6139 | 77.2090 |
| Mumbai | 19.0760 | 72.8777 |
| Bangalore | 12.9716 | 77.5946 |
| Hubli, Karnataka | 15.3647 | 75.1240 |
| Siwan, Bihar | 26.2196 | 84.3567 |

## 🔍 How It Works (Technical Deep Dive)

### Why the Data is REAL

This dashboard fetches **100% authentic, real-time weather data** from the Open-Meteo API:

1. **API Endpoint**: `https://api.open-meteo.com/v1/forecast`
2. **Request Parameters**:
   - `latitude`: Geographic coordinate
   - `longitude`: Geographic coordinate  
   - `hourly`: `temperature_2m` (2-meter height temperature)
   - `forecast_days`: `1` (24-hour forecast)

3. **Response Format**: JSON with timestamps and temperature arrays

**Example API Call:**
const response = await fetch(
  'https://api.open-meteo.com/v1/forecast?latitude=28.6139&longitude=77.2090&hourly=temperature_2m&forecast_days=1'
);
const data = await response.json();
// data.hourly.temperature_2m = [22.5, 23.1, 24.3, ...] (real temperatures)

### Data Flow Architecture

User Input (City/Coords)
    ↓
JavaScript fetchWeatherData()
    ↓
Fetch API → Open-Meteo Server
    ↓
JSON Response (Real Weather Data)
    ↓
Parse & Calculate Statistics
    ↓
Update DOM (Cards, Chart, Table)
    ↓
Display to User

### Key JavaScript Concepts Demonstrated

| Concept | Implementation |
|---------|----------------|
| **API Calls** | `fetch()` with async/await |
| **DOM Manipulation** | `getElementById()`, `innerHTML` |
| **Event Handling** | `addEventListener()`, `onclick` |
| **Arrays & Functions** | `.map()`, `.reduce()`, `Math.max()` |
| **Conditions & Loops** | `if/else`, `.forEach()` |
| **Objects** | JSON parsing, data structures |
| **Callbacks** | Async operations, promises |
| **Error Handling** | `try/catch` blocks |
| **Data Validation** | Input checking before API call |

### Vanilla JavaScript vs Frameworks

**This project uses Vanilla JavaScript**, meaning:
- ✅ **No React/Vue/Angular** - Direct browser APIs
- ✅ **No jQuery** - Native DOM methods
- ✅ **No Build Tools** - Works instantly, no compilation
- ✅ **Pure ES6+** - Modern JavaScript features

**All these vanilla JS topics are demonstrated:**
- Client-side scripting (browser-based execution)
- JavaScript syntax (const, let, arrow functions)
- Variables, arrays, functions (data structures)
- Conditions, loops (control flow)
- Objects & DOM (data + HTML manipulation)
- Built-in functions (Math, Date, Array methods)
- Validations (input checking)
- Event handling (button clicks, dropdown changes)
- Callbacks (async/await, promises)

## 🎨 Customization Guide

### Change Cities

Edit the `cityCoordinates` object in JavaScript:
const cityCoordinates = {
    '28.6139,77.2090': 'Delhi',
    '40.7128,-74.0060': 'New York', // Add your city
};

Update the HTML dropdown:
<option value="40.7128,-74.0060">New York</option>

### Modify Colors

Edit CSS variables in `:root`:
:root {
    --color-bg-primary: #0f172a;    /* Dark blue background */
    --color-accent: #3b82f6;         /* Blue accent */
    --color-text-primary: #f1f5f9;   /* White text */
}

### Change Chart Style

Modify Chart.js options in `updateChart()` function:
borderColor: 'rgba(255, 255, 255, 0.6)',  // Line color
backgroundColor: 'rgba(255, 255, 255, 0.05)', // Fill color
tension: 0.4,  // Curve smoothness

## 📊 API Information

### Open-Meteo API

- **Provider**: Open-Meteo
- **Documentation**: https://open-meteo.com/
- **Cost**: FREE (no API key required)
- **Rate Limit**: 10,000 requests/day
- **Data Source**: Global weather models (NOAA, DWD, MeteoFrance)
- **Update Frequency**: Hourly

### Why It's Reliable

1. **Official Weather Models** - Uses government meteorological data
2. **No Authentication** - Public API, no registration needed
3. **High Availability** - 99.9% uptime
4. **Global Coverage** - Works for any coordinates worldwide

## 🐛 Troubleshooting

### Issue: "Failed to fetch weather data"

**Solution:**
- Check internet connection
- Verify latitude/longitude are valid numbers
- Ensure coordinates are within range (-90 to 90, -180 to 180)

### Issue: Chart not displaying

**Solution:**
- Check browser console for errors
- Ensure Chart.js CDN is loading
- Try clearing browser cache

### Issue: Wrong city showing

**Solution:**
- Manually update latitude/longitude fields
- Check city dropdown selection matches coordinates

## 📝 Project Structure

weather-dashboard/
│
├── index.html          # Main HTML file (complete single-file app)
├── README.md           # This file
├── screenshot.png      # Dashboard preview image (add yours)
└── LICENSE             # MIT License (optional)

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**Atul Anand**  
B.Tech-M.Tech in Computer Science (Cybersecurity)  
National Forensic Sciences University (NFSU), Dharwad

- GitHub: [@yourusername](https://github.com/yourusername)
- Email: atul.btmtcs10232807@nfsu.ac.in

## 🙏 Acknowledgments

- **Open-Meteo** - Free weather API
- **Chart.js** - Interactive charting library
- **GitHub Pages** - Free hosting platform

## 🔗 Useful Links

- [Open-Meteo API Docs](https://open-meteo.com/en/docs)
- [Chart.js Documentation](https://www.chartjs.org/docs/)
- [MDN Web Docs - Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- [GitHub Pages Guide](https://pages.github.com/)

---

**⭐ If you found this project helpful, please star the repository!**

*Last Updated: November 2025*