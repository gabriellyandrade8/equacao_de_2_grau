<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    valor a
    <input type="number" id="valor-a" value="1"><br>
    valor b
    <input type="number" id="valor-b" value="0"><br>
    valor c
    <input type="number" id="valor-c" value="4"><br>
    <button type="submit" id="calcular">calcular</button>
    <div id="resultado"></div>
    <script src="script.js"></script>
</body>

</html>
let valorA = document.getElementById('valor-a');
let valorB = document.getElementById('valor-b');
let valorC = document.getElementById('valor-c');

let botao = document.getElementById('calcular');

let resultado = document.getElementById('resultado');

function calcularValores() {
    resultado.innerHTML = '';
    const a = Number(valorA.value);
    const b = Number(valorB.value);
    const c = Number(valorC.value);

    const delta = b * b - 4 * a * c;

    resultado.innerHTML += `delta = ${delta}`

    if (delta > 0) {
        resultado.innerHTML += '<p>tem duas raizes distintas</p>';
        const x1 = (-b + Math.sqrt(delta)) / (2 * a);
        const x2 = (-b - Math.sqrt(delta)) / (2 * a);

        resultado.innerHTML += `x1 = ${x1.toFixed(4)}<br>`;
        resultado.innerHTML += `x2 = ${x2.toFixed(4)}<br>`;
    } else if (delta == 0) {
        resultado.innerHTML += '<p>tem duas raizes iguais</p>';
        const x1 = -b / (2 * a);
        resultado.innerHTML += `x1 = x2 = ${x1.toFixed(4)}<br>`;
    } else {
        resultado.innerHTML += '<p>não existem raizes reais</p>';
    }

}

botao.addEventListener('click', calcularValores, false);
