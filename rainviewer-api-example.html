<!DOCTYPE html>
<html>
<head>
    <title>Rain Viewer Weather Maps API Example (Personal Use)</title>
    <meta charset="utf-8"/>
    <meta content="width=device-width, initial-scale=1.0" name="viewport">
    <link href="https://unpkg.com/leaflet/dist/leaflet.css" rel="stylesheet"/>
    <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
    <style>
        body { margin: 0; font-family: sans-serif; }
        .controls {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 20px;
            background: white;
            z-index: 1000;
            box-sizing: border-box;
        }
        .title {
            font-weight: 400;
            color: #333;
        }
        #timestamp {
            font-size: 18px;
            font-weight: 600;
            color: #333;
        }
        .buttons {
            display: flex;
            gap: 8px;
        }
        .buttons button {
            width: 36px;
            height: 36px;
            border: 1px solid #ddd;
            border-radius: 4px;
            background: #fff;
            cursor: pointer;
            font-size: 16px;
        }
        .buttons button:hover {
            background: #f5f5f5;
        }
        #mapid {
            position: absolute;
            top: 50px;
            left: 0;
            bottom: 0;
            right: 0;
        }
    </style>
</head>
<body>

<div class="controls">
    <span class="title">Weather Radar</span>
    <span id="timestamp">Loading...</span>
    <div class="buttons">
        <button onclick="stop(); showFrame(animationPosition - 1);">‹</button>
        <button id="playBtn" onclick="playStop();">▶</button>
        <button onclick="stop(); showFrame(animationPosition + 1);">›</button>
    </div>
</div>

<div id="mapid"></div>

<script>
// === CONFIGURATION ===
var TILE_SIZE = window.devicePixelRatio >= 2 ? 512 : 256;
var RADAR_OPACITY = 0.8;
var ANIMATION_DELAY_MS = 500;
var API_URL = "https://api.rainviewer.com/public/weather-maps.json";

// === STATE ===
var apiData = {};
var mapFrames = [];
var animationPosition = 0;
var animationTimer = false;
var currentLayer = null;
var isLoading = false;
var layerCache = {};

// === MAP SETUP ===
var map = L.map('mapid', { maxZoom: 12 }).setView([48.8566, 2.3522], 5);

L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; <a href="https://openstreetmap.org">OpenStreetMap</a> contributors'
}).addTo(map);

// === UTILITIES ===
function wrapPosition(position) {
    while (position >= mapFrames.length) {
        position -= mapFrames.length;
    }
    while (position < 0) {
        position += mapFrames.length;
    }
    return position;
}

function formatTime(timestamp) {
    return new Date(timestamp * 1000).toLocaleTimeString([], { hour: '2-digit', minute: '2-digit' });
}

// === LAYER MANAGEMENT ===
function createRadarLayer(frame) {
    return new L.TileLayer(apiData.host + frame.path + '/' + TILE_SIZE + '/{z}/{x}/{y}/2/1_1.png', {
        tileSize: 256,
        opacity: 0.001,
        maxNativeZoom: 7,
        maxZoom: 12
    });
}

function clearLayerCache() {
    stop();
    for (var pos in layerCache) {
        if (parseInt(pos) !== animationPosition) {
            map.removeLayer(layerCache[pos]);
            delete layerCache[pos];
        }
    }
}

// === ANIMATION CONTROL ===
function stop() {
    if (animationTimer) {
        clearTimeout(animationTimer);
        animationTimer = false;
        document.getElementById("playBtn").innerHTML = "▶";
        return true;
    }
    return false;
}

function play() {
    animationTimer = true;
    document.getElementById("playBtn").innerHTML = "⏸";
    showFrame(animationPosition + 1);
}

function playStop() {
    if (!stop()) {
        play();
    }
}

// === DISPLAY ===
function updateTimestamp(frame) {
    document.getElementById("timestamp").innerHTML = formatTime(frame.time);
}

function showFrame(position) {
    if (isLoading) return;

    position = wrapPosition(position);
    var frame = mapFrames[position];

    updateTimestamp(frame);

    var oldLayer = currentLayer;

    if (layerCache[position]) {
        if (oldLayer) {
            oldLayer.setOpacity(0);
        }
        layerCache[position].setOpacity(RADAR_OPACITY);
        currentLayer = layerCache[position];
        animationPosition = position;

        if (animationTimer) {
            animationTimer = setTimeout(play, ANIMATION_DELAY_MS);
        }
        return;
    }

    isLoading = true;

    var newLayer = createRadarLayer(frame);

    newLayer.on('load', function() {
        newLayer.setOpacity(RADAR_OPACITY);
        if (oldLayer) {
            oldLayer.setOpacity(0);
        }
        layerCache[position] = newLayer;
        currentLayer = newLayer;
        animationPosition = position;
        isLoading = false;

        if (animationTimer) {
            animationTimer = setTimeout(play, ANIMATION_DELAY_MS);
        }
    });

    newLayer.addTo(map);
}

// === INITIALIZATION ===
function initialize(api) {
    clearLayerCache();
    currentLayer = null;
    mapFrames = [];
    animationPosition = 0;

    if (!api || !api.radar || !api.radar.past) {
        return;
    }

    mapFrames = api.radar.past;
    showFrame(mapFrames.length - 1);
}

function loadApiData() {
    var apiRequest = new XMLHttpRequest();
    apiRequest.open("GET", API_URL, true);
    apiRequest.onload = function() {
        apiData = JSON.parse(apiRequest.response);
        initialize(apiData);
    };
    apiRequest.send();
}

map.on('movestart', clearLayerCache);
loadApiData();
</script>

</body>
</html>
