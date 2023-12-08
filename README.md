<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Obtener Hora</title>
</head>
<body>

<h1>La hora actual es:</h1>
<p id="hora"></p>
<button onclick="leerHora()">Leer Hora</button>

<script>
    function mostrarHora() {
        var horaActual = new Date();
        var horas = horaActual.getHours();
        var minutos = horaActual.getMinutes();
        var segundos = horaActual.getSeconds();
        var horaFormateada = horas + ':' + minutos + ':' + segundos;

        document.getElementById('hora').innerText = horaFormateada;

        // Leer la hora en voz alta
        leerHora();
    }

    function leerHora() {
        var horaActual = new Date();
        var horas = horaActual.getHours();
        var minutos = horaActual.getMinutes();
        var segundos = horaActual.getSeconds();
        var horaFormateada = horas + ' horas, ' + minutos + ' minutos y ' + segundos + ' segundos';

        // Utilizar la API de texto a voz del navegador
        var synth = window.speechSynthesis;
        var utterance = new SpeechSynthesisUtterance('La hora actual es ' + horaFormateada);

        // Hablar la hora
        synth.speak(utterance);
    }

    mostrarHora();
    setInterval(mostrarHora, 1000);
</script>

</body>
</html>
