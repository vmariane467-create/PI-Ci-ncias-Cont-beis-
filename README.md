# PI-Ci-ncias-Cont-beis-
Gestão para Microempreendedores
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Gestão de Negócio - MEI</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
      background: #f3f3f3;
    }
    h1 { text-align: center; }
    .container {
      max-width: 600px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 10px;
    }
    label { font-weight: bold; }
    input {
      width: 100%;
      padding: 8px;
      margin: 8px 0 16px;
      box-sizing: border-box;
    }
    button {
      width: 100%;
      padding: 12px;
      background-color: #2c7;
      color: white;
      font-weight: bold;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    .result { margin-top: 20px; font-size: 1.2em; }
  </style>
</head>
<body>
  <div class="container">
    <h1>Precificação e Fluxo de Caixa</h1>
    <label>Custo Fixo (mensal):</label>
    <input type="number" id="fixo" />

    <label>Custo Variável (por unidade):</label>
    <input type="number" id="variavel" />

    <label>Unidades vendidas/mês:</label>
    <input type="number" id="quantidade" />

    <label>Margem de Lucro (%):</label>
    <input type="number" id="lucro" />

    <button onclick="calcular()">Calcular Preço Ideal</button>

    <div class="result" id="resultado"></div>
  </div>

  <script>
    function calcular() {
      const fixo = parseFloat(document.getElementById('fixo').value || 0);
      const variavel = parseFloat(document.getElementById('variavel').value || 0);
      const quantidade = parseFloat(document.getElementById('quantidade').value || 1);
      const lucro = parseFloat(document.getElementById('lucro').value || 0);

      const custoFixoPorUnidade = fixo / quantidade;
      const custoTotal = custoFixoPorUnidade + variavel;
      const precoFinal = custoTotal + (custoTotal * lucro / 100);

      document.getElementById('resultado').innerHTML = `
        <p>💰 Custo real por unidade: R$ ${custoTotal.toFixed(2)}</p>
        <p>🏷️ Preço ideal de venda: R$ ${precoFinal.toFixed(2)}</p>
      `;
    }
  </script>
</body>
</html>
