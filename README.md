<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Color Matching Tool</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1rem;
        }
        .container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            padding: 1rem;
        }
        .color-box {
            width: 150px;
            height: 150px;
            margin: 10px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            position: relative;
            cursor: pointer;
            overflow: hidden;
        }
        .color-info {
            position: absolute;
            bottom: 0;
            background: rgba(0, 0, 0, 0.7);
            color: white;
            width: 100%;
            text-align: center;
            padding: 0.5rem;
            font-size: 14px;
        }
        .picker {
            margin: 20px auto;
            text-align: center;
        }
        input[type="color"] {
            width: 100px;
            height: 50px;
            border: none;
            cursor: pointer;
        }
        input[type="color"]::-webkit-color-swatch {
            border: none;
        }
    </style>
</head>
<body>
    <header>
        <h1>Color Matching Tool</h1>
        <p>اختبر وقارن بين الألوان بسهولة</p>
    </header>
    <div class="picker">
        <label for="colorPicker">اختر لون:</label>
        <input type="color" id="colorPicker">
        <button onclick="addColor()">أضف اللون</button>
    </div>
    <div class="container" id="colorContainer">
        <!-- سيتم إضافة الألوان هنا -->
    </div>

    <script>
        function addColor() {
            const colorPicker = document.getElementById('colorPicker');
            const colorContainer = document.getElementById('colorContainer');
            const colorValue = colorPicker.value;

            // إنشاء عنصر للون
            const colorBox = document.createElement('div');
            colorBox.className = 'color-box';
            colorBox.style.backgroundColor = colorValue;

            // إضافة معلومات اللون
            const colorInfo = document.createElement('div');
            colorInfo.className = 'color-info';
            colorInfo.textContent = colorValue;

            // إرفاق المعلومات للعنصر
            colorBox.appendChild(colorInfo);
            colorContainer.appendChild(colorBox);
        }
    </script>
</body>
</html>
