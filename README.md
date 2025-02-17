# Power-Skils
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Encuesta de Liderazgo y Habilidades Blandas</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 20px;
            background-color: #f4f4f4;
        }
        .container {
            max-width: 600px;
            margin: auto;
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px 0px #aaa;
        }
        h2 {
            text-align: center;
        }
        .question {
            margin-bottom: 15px;
        }
        button {
            display: block;
            width: 100%;
            padding: 10px;
            background: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background: #218838;
        }
        .result {
            margin-top: 20px;
            font-weight: bold;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Encuesta de Liderazgo y Habilidades Blandas</h2>
        <form id="surveyForm">
            <div class="question">
                <label>1. Me siento seguro/a expresando mis ideas en reuniones de equipo.</label><br>
                <input type="radio" name="q1" value="1"> 1
                <input type="radio" name="q1" value="2"> 2
                <input type="radio" name="q1" value="3"> 3
                <input type="radio" name="q1" value="4"> 4
                <input type="radio" name="q1" value="5"> 5
            </div>
            
            <div class="question">
                <label>2. Escucho activamente a mis compañeros antes de dar mi opinión.</label><br>
                <input type="radio" name="q2" value="1"> 1
                <input type="radio" name="q2" value="2"> 2
                <input type="radio" name="q2" value="3"> 3
                <input type="radio" name="q2" value="4"> 4
                <input type="radio" name="q2" value="5"> 5
            </div>
            
            <button type="button" onclick="calculateResults()">Calcular Resultados</button>
        </form>
        <div id="result" class="result"></div>
    </div>

    <script>
        function calculateResults() {
            let total = 0;
            let count = 0;
            let questions = document.querySelectorAll('input[type="radio"]:checked');
            
            questions.forEach((q) => {
                total += parseInt(q.value);
                count++;
            });
            
            let average = total / count;
            let resultText = "";
            
            if (average >= 4) {
                resultText = "¡Excelente! Tienes una gran fortaleza en liderazgo y habilidades blandas.";
            } else if (average >= 3) {
                resultText = "Bien, pero hay áreas de mejora en tu liderazgo.";
            } else {
                resultText = "Necesitas trabajar en tus habilidades blandas para mejorar tu liderazgo.";
            }
            
            document.getElementById("result").innerText = resultText;
        }
    </script>
</body>
</html>
