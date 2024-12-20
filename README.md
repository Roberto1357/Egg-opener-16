# Egg-opener-16
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Egg Opener Simulator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f7f7f7;
            padding: 20px;
            overflow: hidden;
        }
        .button {
            padding: 15px 25px;
            font-size: 20px;
            color: #fff;
            background-color: #007BFF;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 5px;
        }
        .button:hover {
            background-color: #0056b3;
        }
        .output {
            margin-top: 20px;
            font-size: 24px;
            color: #333;
        }
        .animation-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: none;
            z-index: 1000;
            background-color: rgba(255, 255, 255, 0);
        }
        .zoom-effect {
            animation: fullZoomOut 1s forwards, fullZoomIn 1.5s 1s forwards;
        }
        .side-effects {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .side-line {
            position: absolute;
            width: 5px;
            height: 100%;
            background: linear-gradient(to bottom, rgba(0, 0, 255, 0), blue, rgba(0, 0, 255, 0));
            animation: sideLineMove 1.5s infinite ease-in-out alternate;
        }
        .side-line:nth-child(1) {
            left: 5%;
        }
        .side-line:nth-child(2) {
            right: 5%;
        }
        .side-line:nth-child(3) {
            left: 15%;
        }
        .side-line:nth-child(4) {
            right: 15%;
        }
        @keyframes fullZoomOut {
            from {
                transform: scale(1);
            }
            to {
                transform: scale(0.5);
            }
        }
        @keyframes fullZoomIn {
            from {
                transform: scale(0.5);
            }
            to {
                transform: scale(1);
            }
        }
        @keyframes sideLineMove {
            0% {
                transform: rotate(-5deg);
            }
            100% {
                transform: rotate(5deg);
            }
        }
        .pet-popup {
            position: absolute;
            background-color: white;
            border: 2px solid #ccc;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            opacity: 0;
            animation: fadeIn 1s 2s forwards, wobble 1s 2.5s infinite alternate;
            font-size: 36px;
            font-weight: bold;
            color: #333;
        }
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
        @keyframes wobble {
            from {
                transform: translateX(-5px);
            }
            to {
                transform: translateX(5px);
            }
        }
        .inventory {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: white;
            display: none;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            overflow-y: auto;
            z-index: 1000;
        }
        .inventory.active {
            display: flex;
        }
        .pet-box {
            width: 120px;
            height: 150px;
            margin: 10px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            position: relative;
        }
        .pet-box .count {
            position: absolute;
            top: 5px;
            right: 5px;
            background-color: #007BFF;
            color: white;
            font-size: 12px;
            padding: 3px 6px;
            border-radius: 50%;
        }
        .pet-box .name {
            font-size: 14px;
            font-weight: bold;
            margin-top: 10px;
        }
        .close-button {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: #ff0000;
            color: white;
            border: none;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            font-size: 18px;
            cursor: pointer;
        }
        .table-container {
            margin-top: 40px;
        }
        .pet-list {
            text-align: left;
            margin-left: auto;
            margin-right: auto;
            max-width: 600px;
        }
        .pet-list table {
            width: 100%;
            border-collapse: collapse;
        }
        .pet-list th, .pet-list td {
            border: 1px solid #ccc;
            padding: 8px;
            text-align: center;
        }
        .pet-list th {
            background-color: #007BFF;
            color: white;
        }
    </style>
</head>
<body>
    <h1>Egg Opener Simulator</h1>
    <div>
        <button id="inventoryButton" class="button" style="margin-right: auto; float: left;" onclick="toggleInventory()">Inventar</button>
        <button id="openButton" class="button" onclick="openEgg()">Open Egg</button>
    </div>
    <div class="output" id="output">Click the button to open an egg!</div>
    <div id="popupContainer"></div>

    <!-- Animation Container -->
    <div class="animation-container" id="animationContainer">
        <div class="side-effects">
            <div class="side-line"></div>
            <div class="side-line"></div>
            <div class="side-line"></div>
            <div class="side-line"></div>
        </div>
        <div class="pet-popup" id="petPopup">Rare Fox!</div>
    </div>

    <!-- Inventory Overlay -->
    <div class="inventory" id="inventory">
        <button class="close-button" onclick="toggleInventory()">×</button>
    </div>

    <!-- Pet List Table -->
    <div class="table-container">
        <div class="pet-list">
            <h2>Pet Collection</h2>
            <table>
                <thead>
                    <tr>
                        <th>Pet</th>
                        <th>Probability</th>
                        <th>Count</th>
                    </tr>
                </thead>
                <tbody id="petTableBody"></tbody>
            </table>
        </div>
    </div>

    <script>
        // Der vollständige JavaScript-Code wird hier eingefügt. Sag mir Bescheid, wenn du die Logik noch einmal brauchst.
    </script>
</body>
</html>
