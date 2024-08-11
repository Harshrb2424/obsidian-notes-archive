**AIM:** Explore ES6 features (arrow functions, callbacks, promises, async/await) by building a simple weather application. Display weather information from openweathermap.org as a graph using JavaScript, axios for HTTP requests, and Chart.js for graph creation.

**Project Structure:**
1. `index.html`: Main HTML file.
2. `script.js`: JavaScript file for weather data and graph.
3. `styles.css`: CSS file for styling.
4. `node_modules/`: Folder for library dependencies.

**index.html:**
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="stylesheet" href="styles.css" />
    <title>Weather Graph</title>
  </head>
  <body>
    <div class="container">
      <h1>Weather Graph</h1>
      <canvas id="weatherGraph" width="400" height="200"></canvas>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="script.js"></script>
  </body>
</html>
```

**styles.css:**
```css
  body {
	font-family: "Arial", sans-serif;
	background-color: lightgray;
  }
  .container {
	max-width: 600px;
	margin: 50px auto;
	background-color: white;
	padding: 40px;
	border-radius: 8px;
	box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  h1 {
	text-align: center;
  }
```

**script.js:**
```javascript
  document.addEventListener("DOMContentLoaded", async () => {
	const apiKey = "YOUR_OPENWEATHERMAP_API_KEY";
	const city = "Hyderabad";
	const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`;

	const response = await axios.get(apiUrl);
	const weatherData = response.data;
	updateGraph(weatherData.main.temp);

	function updateGraph(temperature) {
	  const ctx = document.getElementById("weatherGraph").getContext("2d");
	  new Chart(ctx, {
		type: "bar",
		data: {
		  labels: ["Temperature"],
		  datasets: [{
			  label: "Temperature (°C)",
			  data: [temperature],
			  backgroundColor: ["lightblue"],
			}],
		},
	  });
	}
	
  });

```

**Explanation:**
1. HTML Structure: We have a simple HTML structure with a container for the 
graph canvas.
2. CSS Styling: Basic styling to make the application look presentable.
3. JavaScript (script.js):
	- The fetchData function uses axios to make an asynchronous HTTP request to OpenWeatherMap API.
	- The retrieved weather data is used to update the graph using the updateGraph function.
	- The graph is created using the Chart.js library.
4. API key:
	- Sign up at https://openweathermap.org/.
	- Log in to your OpenWeatherMap account.
	- Generate a new API key in the "API keys" section.
	- Copy the generated API key.
	- Replace `YOUR_OPENWEATHERMAP_API_KEY` in `script.js` with the copied key.

 **Output:**
When you open index.html in a web browser, the application fetches the current weather information for the specified city from OpenWeatherMap API and displays the temperature on a bar graph. Please note that you need to replace 'YOUR_OPENWEATHERMAP_API_KEY' with your actual API key. Additionally, the responsiveness and appearance can be further enhanced based on your design preferences

![[Pasted image 20240110175622.png]]