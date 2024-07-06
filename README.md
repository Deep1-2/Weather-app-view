# Weather_webpage
<!DOCTYPE html>
<html>
<head>
    <title>Weather App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        #weather {
            font-size: 2em;
        }
    </style>
</head>
<body>
    <h1>Weather App</h1>
    <button onclick="getWeather()">Get Weather</button>
    <div id="weather"></div>

    <script>
        function getWeather() {
            var apiKey = 'your_api_key_here';
            var city = 'London';
            var url = `http://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}`;

            fetch(url)
            .then(response => response.json())
            .then(data => {
                var temp = data.main.temp;
                document.getElementById('weather').innerHTML = `The temperature in ${city} is ${temp} degrees.`;
            })
            .catch(err => {
                console.error(err);
            });
        }
    </script>
</body>
</html>
