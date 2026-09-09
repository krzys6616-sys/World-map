# World-map
<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Mapa Świata</title>

  <!-- Leaflet CSS -->
  <link
    rel="stylesheet"
    href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
  />

  <style>
    * {
      box-sizing: border-box;
    }

    html, body {
      margin: 0;
      padding: 0;
      width: 100%;
      height: 100%;
      font-family: Arial, sans-serif;
      background: #111;
    }

    #map {
      width: 100%;
      height: 100vh;
    }

    .panel {
      position: absolute;
      top: 20px;
      left: 20px;
      z-index: 1000;
      background: rgba(255, 255, 255, 0.95);
      padding: 15px;
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.25);
      width: 260px;
    }

    .panel h1 {
      margin: 0 0 10px;
      font-size: 20px;
    }

    .panel p {
      margin: 0 0 12px;
      color: #555;
      font-size: 14px;
    }

    button {
      width: 100%;
      border: none;
      padding: 10px;
      border-radius: 8px;
      background: #1976d2;
      color: white;
      font-size: 14px;
      cursor: pointer;
    }

    button:hover {
      background: #125ca3;
    }
  </style>
</head>

<body>

  <div class="panel">
    <h1>🌍 Mapa Świata</h1>
    <p>Przesuwaj mapę i używaj przybliżenia.</p>
    <button onclick="resetMap()">Pokaż cały świat</button>
  </div>

  <div id="map"></div>

  <!-- Leaflet JS -->
  <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

  <script>
    // Utworzenie mapy
    const map = L.map("map", {
      worldCopyJump: true
    }).setView([20, 0], 2);

    // Mapa OpenStreetMap
    L.tileLayer(
      "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
      {
        maxZoom: 19,
        attribution:
          '&copy; <a href="https://www.openstreetmap.org/copyright" target="_blank">OpenStreetMap</a> contributors'
      }
    ).addTo(map);

    // Powrót do widoku całego świata
    function resetMap() {
      map.setView([20, 0], 2);
    }
  </script>

</body>
</html>
