<!DOCTYPE html>
<html>

<head>
    <title>HTML Calculator</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #111;
            margin: 0;
        }

        .calculator {
            border: 2px solid black;
            background-color: #222;
            border-radius: 10px;
            padding: 20px;
            display: inline-block;
            text-align: center;
        }

        table {
            margin: auto;
        }

        input[type="button"] {
            width: 60px;
            height: 60px;
            background-color: #28a745;
            color: white;
            font-size: 24px;
            font-weight: bold;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: 0.3s;
        }

        input[type="button"]:hover {
            background-color: #218838;
        }

        input[type="text"] {
            width: 100%;
            height: 60px;
            font-size: 28px;
            font-weight: bold;
            border: none;
            border-radius: 8px;
            text-align: right;
            background-color: #f8f9fa;
            padding: 10px;
        }

        .clear-btn {
            background-color: red !important;
        }

        .clear-btn:hover {
            background-color: darkred !important;
        }

        .delete-btn {
            background-color: orange !important;
        }

        .delete-btn:hover {
            background-color: darkorange !important;
        }
    </style>
</head>

<body>
    <div class="calculator">
        <table>
            <tr>
                <td colspan="4">
                    <input type="text" id="result" disabled>
                </td>
            </tr>
            <tr>
                <td><input type="button" value="1" onclick="display('1')"></td>
                <td><input type="button" value="2" onclick="display('2')"></td>
                <td><input type="button" value="3" onclick="display('3')"></td>
                <td><input type="button" value="/" onclick="display('/')"></td>
            </tr>
            <tr>
                <td><input type="button" value="4" onclick="display('4')"></td>
                <td><input type="button" value="5" onclick="display('5')"></td>
                <td><input type="button" value="6" onclick="display('6')"></td>
                <td><input type="button" value="*" onclick="display('*')"></td>
            </tr>
            <tr>
                <td><input type="button" value="7" onclick="display('7')"></td>
                <td><input type="button" value="8" onclick="display('8')"></td>
                <td><input type="button" value="9" onclick="display('9')"></td>
                <td><input type="button" value="-" onclick="display('-')"></td>
            </tr>
            <tr>
                <td><input type="button" value="C" class="clear-btn" onclick="clearScreen()"></td>
                <td><input type="button" value="0" onclick="display('0')"></td>
                <td><input type="button" value="Del" class="delete-btn" onclick="deleteLast()"></td>
                <td><input type="button" value="+" onclick="display('+')"></td>
            </tr>
            <tr>
                <td colspan="4"><input type="button" value="=" class="delete-btn" onclick="calculate()"></td>
            </tr>
        </table>
    </div>

    <script>
        function display(value) {
            document.getElementById("result").value += value;
        }

        function clearScreen() {
            document.getElementById("result").value = "";
        }

        function deleteLast() {
            let res = document.getElementById("result").value;
            document.getElementById("result").value = res.slice(0, -1);
        }

        function calculate() {
            try {
                document.getElementById("result").value = eval(document.getElementById("result").value);
            } catch (err) {
                alert("Invalid Input");
            }
        }
    </script>
</body>

</html>
