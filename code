<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Jogo adivinhe o número</title>
    <style>
        html {
            font-family: sans-serif;
        }
        
        body {
            width: 50%;
            max-width: 800px;
            min-width: 480px;
            margin: 0 auto;
        }
        
        .lastResult {
            color: white;
            padding: 3px;
        }
        
        h1 {font-family: Impact;
            letter-spacing:2px;
        }
        
        p {font-family: Tahoma;}
    </style>
</head>

<body>
<center>    <h1>advinhe o número</h1>
    <p>selecionamos um número aleatório entre 1 e 100. veja se consegue adivinhar. você tem 10 chances. </p>
    <div class="form"> <input type="text" id="guessField" class="guessField" placeholder="seu palpite"> <input type="submit" value="enviar" class="guessSubmit"> </div>
    <div class="resultParas">
        <p class="guesses"></p>
        <p class="lastResult"></p>
        <p class="lowOrHi"></p>
    </div>
</body>
<script>
    // Seu JavaScipt vem aqui
    var randomNumber = Math.floor(Math.random() * 100) + 1;
    var guesses = document.querySelector('.guesses');
    var lastResult = document.querySelector('.lastResult');
    var lowOrHi = document.querySelector('.lowOrHi');
    var guessSubmit = document.querySelector('.guessSubmit');
    var guessField = document.querySelector('.guessField');
    var guessCount = 1;
    var resetButton;

    function checkGuess() {
      var userGuess = Number(guessField.value);
      if (guessCount === 1) {
        guesses.textContent = 'palpites anteriores: ';
      }

      guesses.textContent += userGuess + ' ';

      if (userGuess === randomNumber) {
        lastResult.textContent = 'parabéns! você acertou o número!';
        lastResult.style.backgroundColor = 'green';
        lowOrHi.textContent = '';
        setGameOver();
      } else if (guessCount === 10) {
        lastResult.textContent = '!!!FIM DE JOGO!!!';
        lowOrHi.textContent = '';
        setGameOver();
      } else {
        lastResult.textContent = 'errado!';
        lastResult.style.backgroundColor = 'red';
        if(userGuess < randomNumber) {
          lowOrHi.textContent='tente um número maior!' ;
        } else if(userGuess > randomNumber) {
          lowOrHi.textContent = 'tente um número menor!';
        }
      }

      guessCount++;
      guessField.value = '';
    }

    guessSubmit.addEventListener('click', checkGuess);

    function setGameOver() {
      guessField.disabled = true;
      guessSubmit.disabled = true;
      resetButton = document.createElement('button');
      resetButton.textContent = 'iniciar novo jogo';
      document.body.appendChild(resetButton);
      resetButton.addEventListener('click', resetGame);
    }

    function resetGame() {
      guessCount = 1;
      var resetParas = document.querySelectorAll('.resultParas p');
      for(var i = 0 ; i < resetParas.length ; i++) {
        resetParas[i].textContent='';
      }

      resetButton.parentNode.removeChild(resetButton);
      guessField.disabled = false;
      guessSubmit.disabled = false;
      guessField.value='';
      guessField.focus();
      lastResult.style.backgroundColor='white';
      randomNumber=Math.floor(Math.random() * 100) + 1;
    }
</script>

</html>
