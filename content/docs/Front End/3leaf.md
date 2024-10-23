---
title: FrontEnd
type: docs
weight: 3
prev: docs/Front End/2leaf
next: docs/Front End
---

# Weather Dashboard with React and TailwindCSS

In this project, we will build a simple weather dashboard using React, TailwindCSS, and the OpenWeatherMap API.

## Features

- Display current weather information based on user input (city name).
- Show temperature, weather condition, humidity, and wind speed.
- Responsive design using TailwindCSS.

## Tech Stack

- React.js
- TailwindCSS
- OpenWeatherMap API

## Prerequisites

- Node.js installed on your system.
- OpenWeatherMap API key. You can sign up for free at https://openweathermap.org/.

## Step-by-Step Implementation

### 1. Create React Application

Start by creating a new React project:

```
npx create-react-app weather-dashboard
cd weather-dashboard
```

### 2.Install TailwindCSS

- **To set up TailwindCSS in your React project**:

```
npm install -D tailwindcss
npx tailwindcss init

```

- **Update tailwind.config.js**:

```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

```

- **In src/index.css, import Tailwind**:

```
@tailwind base;
@tailwind components;
@tailwind utilities;

```

### 3. Get OpenWeatherMap API Key

- **Information**: Sign up at OpenWeatherMap and get your API key.

### 4. Create Weather Component

- **In the src folder, create a new component Weather.js**:
- **Usage**:

```
import React, { useState } from 'react';

const Weather = () => {
  const [city, setCity] = useState('');
  const [weatherData, setWeatherData] = useState(null);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  const apiKey = 'YOUR_API_KEY';  // Replace with your OpenWeatherMap API key

  const fetchWeather = async (e) => {
    e.preventDefault();
    setLoading(true);
    setError(null);

    try {
      const response = await fetch(
        `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`
      );
      const data = await response.json();
      if (data.cod !== 200) {
        throw new Error(data.message);
      }
      setWeatherData(data);
    } catch (error) {
      setError(error.message);
    } finally {
      setLoading(false);
    }
  };

  return (
    <div className="container mx-auto p-4">
      <h1 className="text-3xl font-bold mb-4 text-center">Weather Dashboard</h1>
      <form onSubmit={fetchWeather} className="flex justify-center mb-4">
        <input
          type="text"
          placeholder="Enter city"
          value={city}
          onChange={(e) => setCity(e.target.value)}
          className="p-2 border border-gray-300 rounded mr-2"
        />
        <button
          type="submit"
          className="bg-blue-500 text-white p-2 rounded hover:bg-blue-600"
        >
          Get Weather
        </button>
      </form>

      {loading && <p className="text-center">Loading...</p>}
      {error && <p className="text-center text-red-500">{error}</p>}

      {weatherData && (
        <div className="text-center bg-white p-4 rounded shadow-md">
          <h2 className="text-2xl font-semibold">
            {weatherData.name}, {weatherData.sys.country}
          </h2>
          <p className="text-xl">{weatherData.weather[0].description}</p>
          <p className="text-3xl font-bold">{weatherData.main.temp}°C</p>
          <p>Humidity: {weatherData.main.humidity}%</p>
          <p>Wind Speed: {weatherData.wind.speed} m/s</p>
        </div>
      )}
    </div>
  );
};

export default Weather;

```

### 5. Add the Weather Component to App

- **In the src/App.js file, import and use the Weather component**:
- **Usage**:

```
import React from 'react';
import Weather from './Weather';
import './index.css';

function App() {
  return (
    <div className="App bg-gray-100 min-h-screen flex items-center justify-center">
      <Weather />
    </div>
  );
}

export default App;

```

### 6. Run the Application

- **Start your application by running**: npm start

## Conclusion

This is a basic weather dashboard app using React.js and TailwindCSS, which fetches current weather data from the OpenWeatherMap API. You can extend this app by adding more features such as a 7-day forecast, saving favorite cities, or integrating a map view.

```

```
