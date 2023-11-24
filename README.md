# Desafio1-Escribo
<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8">
  <title>Somatório de Múltiplos de 3 ou 5</title>
  
  <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #343a40; 
      color: #fff; 
    }

    .container {
      background-color: #454d54; 
      padding: 100px;
      border-radius: 15px;
      box-shadow: 0px 0px 20px rgba(285, 285, 285, 0.1);
      width: 550px;
    }

    .form-group label {
      color: #fff;
    }

    input.form-control {
      background-color: #6c757d; /* Cor do campo de entrada */
      color: #fff; /* Cor do texto no campo de entrada */
    }

    .btn-primary {
      background-color: #007bff; /* Cor do botão */
      border-color: #007bff;
  
    }

    .btn-primary:hover {
      background-color: #0056b3; /*Para escurecer a cor do botão calcular quando passar o mouse*/
      border-color: #0056b3;
    }

    .footer {
      position: absolute;
      bottom: 10px;
      left: 0;
      right: 0;
      text-align: center;
      font-size: 14px;
      color:#778899;
    }
  
  </style>
</head>
<body>
  <div class="container">
    <h1 class="text-center">Somatório de Múltiplos de <br> 3 ou 5</h1>
    <div class="form-group">
      <label for="inputNumber" >Insira um número inteiro positivo:</label>
      <input type="number" class="form-control" id="inputNumber" min="1" placeholder="Digite aqui...">
    </div>
    <button class="btn btn-primary btn-block" onclick="calcularSomatorio()">Calcular</button>
    <p id="resultado" class="result"></p>
  </div>
  <div class="footer">
      <p>© 2023 - Eduardo de Mello</p>
      <p>Agradeço a <strong>Escribo</strong> pela oportunidade</p>
      <p>Entrem em contato pelo e-mail: edumello1001@gmail.com</p>
    </div>
  </div>
 
  <script> // Criando a função Somatório dos multiplos de 3 ou 5: 
    function somatorioMultiplosDe3e5(numero) {
      let soma = 0;

      for (let i = 3; i < numero; i++) {
        if (i % 3 === 0 || i % 5 === 0) {
          soma += i;
        }
      }

      return soma;
    }

    function calcularSomatorio() {
      const inputNumero = document.getElementById("inputNumber");
      const numero = parseInt(inputNumero.value);

      if (!isNaN(numero) && numero > 0) {
        const resultado = somatorioMultiplosDe3e5(numero);
        document.getElementById("resultado").innerHTML = `<strong>O somatório dos múltiplos de 3 ou 5 menores que ${numero} é:</strong>  ${resultado}`;
      } else {
        document.getElementById("resultado").innerHTML = "<strong>Insira um número inteiro positivo!</strong>";
      }
    }
  </script>
</body>
</html>
