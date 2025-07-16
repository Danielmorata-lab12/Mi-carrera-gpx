<!DOCTYPE html>
<html>
<head>
  <title>Mi carrera</title>
  <meta charset="utf-8" />
  <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
  <style>
    #map { height: 500px; margin-bottom: 1em; }
  </style>
</head>
<body>
  <h1>Visualizador de Ruta GPX</h1>
  <input type="file" id="gpxFile" accept=".gpx" />
  <div id="map"></div>
  <div id="stats"></div>

  <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
  <script src="https://unpkg.com/togpx/gpxparser.min.js"></script>
  <script>
    const map = L.map('map').setView([0, 0], 13);
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; OpenStreetMap contributors'
    }).addTo(map);

    document.getElementById('gpxFile').addEventListener('change', function (e) {
      const file = e.target.files[0];
      const reader = new FileReader();
      reader.onload = function () {
        const gpx = new GPXParser();
        gpx.parse(reader.result);

        const track = gpx.tracks[0];
        const points = track.points;
        const latlngs = points.map(p => [p.lat, p.lon]);
        const polyline = L.polyline(latlngs, { color: 'blue' }).addTo(map);
        map.fitBounds(polyline.getBounds());

        let totalDistance = 0;
        let totalTime = (new Date(points[points.length - 1].time) - new Date(points[0].time)) / 1000; // en segundos

        for (let i = 1; i < points.length; i++) {
          totalDistance += gpx._haversine(points[i - 1], points[i]);
        }

        const pace = totalTime / (totalDistance / 1000); // segundos por km
        const min = Math.floor(pace / 60);
        const sec = Math.round(pace % 60);

        document.getElementById('stats').innerHTML = `
          <strong>Distancia:</strong> ${(totalDistance / 1000).toFixed(2)} km<br>
          <strong>Tiempo total:</strong> ${(totalTime / 60).toFixed(1)} minutos<br>
          <strong>Ritmo promedio:</strong> ${min}:${sec < 10 ? '0' : ''}${sec} min/km
        `;
      };
      reader.readAsText(file);
    });
  </script>
</body>
</html>
