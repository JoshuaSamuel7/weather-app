# 🌦️ Weather Forecast Application

The Weather Forecast Application is a dynamic and visually engaging full-stack web application designed to deliver real-time and forecasted weather data using multiple third-party APIs. Built using the MERN architecture (MongoDB not used in this case, but Express + React), it showcases practical integration of RESTful APIs, user interface engineering, and efficient state management. The project is a robust demonstration of front-end UI/UX skills along with backend API orchestration.

## 🔧 Tech Stack

| Layer       | Technology         | Purpose                              |
|-------------|--------------------|--------------------------------------|
| Frontend    | React.js           | UI and component rendering           |
| Backend     | Express.js         | API routing and middleware           |
| Styling     | Plain CSS          | Custom styles for each component     |
| HTTP Calls  | Fetch API          | Fetch weather data from third-party |
| Icons       | React-Icons        | Display weather & AQI symbols        |
| Hosting     | Localhost          | Frontend (3000), Backend (8000)      |

![weather](https://github.com/user-attachments/assets/c24604f6-77c7-4f0f-adac-b1cbe03f942e)

## 📁 Project Folder Structure
```
weatherapp-local/
│
├── back/ # Backend (Node.js + Express)
│ ├── node_modules/
│ ├── index.js # Main Express server with API endpoints
│ ├── package.json # Backend dependencies
│ └── package-lock.json
│
├── front/ # Frontend (React.js)
│ ├── node_modules/
│ ├── public/ # Static files (HTML, favicon, etc.)
│ └── src/
│ ├── App.js # Root component
│ ├── App.css # Global styles
│ ├── index.js # Entry point
│ └── components/ # UI Components
│ ├── Cities.jsx
│ ├── LastSection.jsx
│ ├── Major.jsx
│ ├── MiddleSection.jsx
│ ├── Navbar.jsx
│ ├── Search.jsx
│ ├── Sidebar.jsx
│ ├── cityList.js # City data array
│ └── css/ # Component-level CSS files
│ ├── citylist.css
│ ├── major.css
│ ├── navbar.css
│ └── search.css
```

---


---

## ☁️ Integrated APIs

| API Provider        | Endpoint Type       | Purpose                                |
|---------------------|---------------------|----------------------------------------|
| OpenWeatherMap      | `/`                 | Fetch current weather for a city       |
| WeatherAPI          | `/forecast`         | 7-day forecast + air quality + hourly  |
| Weatherbit          | `/dayforecast`      | Weekly forecast for sidebar display    |

---

## ⚛️ Key React Components

| Component           | Description                                                  |
|---------------------|--------------------------------------------------------------|
| `Cities.jsx`        | Displays city list with filterable search and navigation     |
| `Search.jsx`        | Search bar with dynamic suggestions                          |
| `Major.jsx`         | Displays current city weather, coordinates, and image icon   |
| `MiddleSection.jsx` | Shows 7-hour rolling forecast with icons and temps           |
| `LastSection.jsx`   | Air conditions (wind, humidity, UV) and AQI with icons       |
| `Sidebar.jsx`       | Weekly forecast summary with date and temp breakdown         |
| `Navbar.jsx`        | (Optional) Navigation or layout management                   |

---
![image](https://github.com/user-attachments/assets/0e87fb5a-d720-4d6b-bc4e-7b35a90738f1)

## 🎯 Key Features

| Feature                      | Description                                                                 |
|------------------------------|-----------------------------------------------------------------------------|
| Real-Time Weather            | Displays current temperature, condition, and location coordinates            |
| Hourly Forecast              | 7-hour weather forecast starting from local time                           |
| Weekly Forecast              | 7-day weather overview with dynamic weekday formatting                     |
| Air Conditions Display       | Wind speed, humidity, UV index, and rainfall                               |
| Air Quality Metrics          | Pollutants (CO, SO2, NO2) and EPA index with icons                         |
| City Search & Navigation     | City-based search with auto-suggestions and navigation                     |
| Responsive Dark UI           | Clean, modern design with intuitive layout                                 |
| Multi-API Integration        | Fetches weather from 3 different providers using asynchronous fetch         |

---

## 🛠️ Backend API Structure

```js
router.post('/', async (req, res) => { ... });               // OpenWeatherMap: Current weather
router.post('/forecast', async (req, res) => { ... });       // WeatherAPI: Forecast + AQI
router.post('/dayforecast', async (req, res) => { ... });    // Weatherbit: Weekly forecast
Uses cors, body-parser, and node-fetch
```
## JSON-based data delivery to frontend components

🧠 Notable Design Considerations
🔄 Reusable Components: Clean structure with scoped CSS (/css/) for modular design

⚙️ Dynamic API Handling: Based on query param ?city=... across all routes

🕒 Local Time Logic: MiddleSection.jsx intelligently handles hour mapping

📉 Fallback Handling: Uses optional chaining (?.) to prevent crash on API latency

🎨 UX Optimization: Forecast tiles and sidebars for both daily and weekly views
