<script>
  let display = '';
  
  // Számológép műveletek
  function appendNumber(number) {
    display += number;
  }

  function appendOperator(operator) {
    display += ` ${operator} `;
  }

  function clearDisplay() {
    display = '';
  }

  function calculate() {
    try {
      display = eval(display).toString();
    } catch (error) {
      display = 'Error';
    }
  }
</script>


<main>
  
<div class="calculator">
  <div class="display">{display}</div>
  
  <button class="button" on:click={() => appendNumber('7')}>7</button>
  <button class="button" on:click={() => appendNumber('8')}>8</button>
  <button class="button" on:click={() => appendNumber('9')}>9</button>
  <button class="button" on:click={() => appendOperator('+')}>+</button>
  
  <button class="button" on:click={() => appendNumber('4')}>4</button>
  <button class="button" on:click={() => appendNumber('5')}>5</button>
  <button class="button" on:click={() => appendNumber('6')}>6</button>
  <button class="button" on:click={() => appendOperator('-')}>-</button>
  
  <button class="button" on:click={() => appendNumber('1')}>1</button>
  <button class="button" on:click={() => appendNumber('2')}>2</button>
  <button class="button" on:click={() => appendNumber('3')}>3</button>
  <button class="button" on:click={() => appendOperator('*')}>*</button>
  
  <button class="button" on:click={() => appendNumber('0')}>0</button>
  <button class="button" on:click={clearDisplay}>C</button>
  <button class="button" on:click={() => appendOperator('/')}>/</button>
  <button class="button" on:click={calculate}>=</button>
</div>


</main>


<style>
  .calculator {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
    width: 200px;
    margin: 0 auto;
  }

  .button {
    padding: 20px;
    font-size: 1.5em;
    cursor: pointer;
    text-align: center;
    background-color: #f0f0f0;
    border: 1px solid #ccc;
    border-radius: 5px;
  }

  .button:hover {
    background-color: #ddd;
  }

  .display {
    grid-column: span 4;
    padding: 20px;
    font-size: 2em;
    text-align: right;
    background-color: #eee;
    border-radius: 5px;
    border: 1px solid #ccc;
  }
</style>
