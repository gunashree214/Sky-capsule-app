<!DOCTYPE html>
<html>
<head>
    <title>Smart Ambulance System</title>
    <style>
        body {
            font-family: Arial;
            background: #0b1c2c;
            color: white;
            text-align: center;
        }
        .container {
            margin: 20px auto;
            width: 80%;
        }
        input, select, button {
            padding: 10px;
            margin: 10px;
            border-radius: 8px;
            border: none;
        }
        button {
            background: #00c3ff;
            color: black;
            cursor: pointer;
        }
        .output {
            margin-top: 20px;
            padding: 15px;
            background: #132f4c;
            border-radius: 10px;
        }
    </style>
</head>

<body>

<div class="container">
    <h1>🚑 Smart Ambulance + Sky Capsule</h1>

    <input type="text" id="location" placeholder="Enter Location">

    <br>

    <select id="emergency">
        <option>Accident</option>
        <option>Cardiac</option>
        <option>General</option>
    </select>

    <select id="traffic">
        <option>Low</option>
        <option>Medium</option>
        <option>High</option>
    </select>

    <br>

    <button onclick="findRoute()">Find Best Route</button>

    <div class="output" id="result"></div>
</div>

<script>
function findRoute() {
    let traffic = document.getElementById("traffic").value;
    let result = document.getElementById("result");

    let transport, reason, time;

    if (traffic === "High") {
        transport = "🚡 Sky Capsule";
        reason = "High traffic → Capsule avoids congestion";
        time = "5-8 mins";
    } else {
        transport = "🚑 Ambulance";
        reason = "Traffic is manageable";
        time = "10-15 mins";
    }

    result.innerHTML = `
        <h2>Recommended: ${transport}</h2>
        <p>${reason}</p>
        <p>Estimated Time: ${time}</p>
    `;
}
</script>

</body>
</html>
