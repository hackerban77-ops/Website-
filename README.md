<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Number Information Website</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #1d2671, #c33764);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 0;
            color: #fff;
        }

        .container {
            background: rgba(0, 0, 0, 0.4);
            padding: 25px;
            border-radius: 12px;
            width: 100%;
            max-width: 400px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
        }

        h1 {
            margin-bottom: 20px;
        }

        input {
            width: 100%;
            padding: 12px;
            border-radius: 6px;
            border: none;
            font-size: 16px;
            margin-bottom: 15px;
        }

        button {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 6px;
            background: #ff9800;
            color: #000;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
        }

        button:hover {
            background: #ffc107;
        }

        .result {
            margin-top: 20px;
            text-align: left;
            font-size: 15px;
        }

        .result p {
            margin: 6px 0;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Number Information</h1>

    <input type="number" id="num" placeholder="Enter a number">
    <button onclick="getInfo()">Get Information</button>

    <div class="result" id="output"></div>
</div>

<script>
    function isPrime(n) {
        if (n <= 1) return false;
        for (let i = 2; i <= Math.sqrt(n); i++) {
            if (n % i === 0) return false;
        }
        return true;
    }

    function getInfo() {
        let num = Number(document.getElementById("num").value);
        let output = document.getElementById("output");

        if (isNaN(num)) {
            output.innerHTML = "<p>Please enter a valid number.</p>";
            return;
        }

        let evenOdd = (num % 2 === 0) ? "Even" : "Odd";
        let sign = num > 0 ? "Positive" : num < 0 ? "Negative" : "Zero";
        let prime = isPrime(Math.abs(num)) ? "Yes" : "No";
        let digits = Math.abs(num).toString().length;

        output.innerHTML = `
            <p><b>Number:</b> ${num}</p>
            <p><b>Type:</b> ${evenOdd}</p>
            <p><b>Sign:</b> ${sign}</p>
            <p><b>Prime:</b> ${prime}</p>
            <p><b>Square:</b> ${num * num}</p>
            <p><b>Cube:</b> ${num * num * num}</p>
            <p><b>Total Digits:</b> ${digits}</p>
        `;
    }
</script>

</body>
</html>
