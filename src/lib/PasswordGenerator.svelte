<script>
    let password = '';
    let length = 12;
    let includeLowercase = true;
    let includeUppercase = true;
    let includeNumbers = true;
    let includeSymbols = false;
  
    function generatePassword() {
      const lowercase = 'abcdefghijklmnopqrstuvwxyz';
      const uppercase = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
      const numbers = '0123456789';
      const symbols = '!@#$%^&*()_+-=[]{}|;:,.<>?';
  
      let chars = '';
      if (includeLowercase) chars += lowercase;
      if (includeUppercase) chars += uppercase;
      if (includeNumbers) chars += numbers;
      if (includeSymbols) chars += symbols;
  
      password = Array(length)
        .fill()
        .map(() => chars[Math.floor(Math.random() * chars.length)])
        .join('');
    }
    //Fun
    function copyToClipboard() {
      navigator.clipboard.writeText(password);
      alert('Contraseña copiada al portapapeles');
    }
  </script>
  
  <div class="password-generator">
    <h2>Generador de Contraseñas</h2>
    
    <div class="options">
      <label>
        <input type="number" bind:value={length} min="4" max="32">
        Longitud
      </label>
      <label>
        <input type="checkbox" bind:checked={includeLowercase}>
        Minúsculas
      </label>
      <label>
        <input type="checkbox" bind:checked={includeUppercase}>
        Mayúsculas
      </label>
      <label>
        <input type="checkbox" bind:checked={includeNumbers}>
        Números
      </label>
      <label>
        <input type="checkbox" bind:checked={includeSymbols}>
        Símbolos
      </label>
    </div>
  
    <button on:click={generatePassword}>Generar Contraseña</button>
    
    <div class="password-display">
      <input type="text" readonly value={password}>
      <button on:click={copyToClipboard}>Copiar</button>
    </div>
  </div>
  
  <style>
    .password-generator {
      max-width: 400px;
      margin: 0 auto;
      padding: 20px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
  
    .options {
      display: flex;
      flex-direction: column;
      margin-bottom: 15px;
    }
  
    .options label {
      margin-bottom: 5px;
    }
  
    .password-display {
      display: flex;
      margin-top: 15px;
    }
  
    .password-display input {
      flex-grow: 1;
      margin-right: 10px;
    }
  </style>