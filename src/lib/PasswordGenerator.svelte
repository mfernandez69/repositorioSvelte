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
        <span>Longitud:</span>
        <input type="number" bind:value={length} min="4" max="32">
      </label>
      <label>
        <input type="checkbox" bind:checked={includeLowercase}>
        <span>Minúsculas</span>
      </label>
      <label>
        <input type="checkbox" bind:checked={includeUppercase}>
        <span>Mayúsculas</span>
      </label>
      <label>
        <input type="checkbox" bind:checked={includeNumbers}>
        <span>Números</span>
      </label>
      <label>
        <input type="checkbox" bind:checked={includeSymbols}>
        <span>Símbolos</span>
      </label>
    </div>
  
    <button class="generate-btn" on:click={generatePassword}>Generar Contraseña</button>
    
    <div class="password-display">
      <input type="text" value={password} readonly>
      <button class="copy-btn" on:click={copyToClipboard}>Copiar</button>
    </div>
  </div>
  
  <style>
    :root {
      --background-color: #121212;
      --card-background: #1e1e1e;
      --primary-color: #bb86fc;
      --secondary-color: #3700b3;
      --text-color: #e0e0e0;
      --input-background: #2c2c2c;
      --input-border: #444;
    }
  
    body {
      background-color: var(--background-color);
      color: var(--text-color);
    }
  
    .password-generator {
      max-width: 400px;
      margin: 2rem auto;
      padding: 2rem;
      background-color: var(--card-background);
      border-radius: 10px;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
    }
  
    h2 {
      color: var(--primary-color);
      text-align: center;
      margin-bottom: 1.5rem;
    }
  
    .options {
      display: grid;
      gap: 1rem;
      margin-bottom: 1.5rem;
    }
  
    label {
      display: flex;
      align-items: center;
      font-size: 0.9rem;
      color: var(--text-color);
    }
  
    input[type="number"] {
      width: 60px;
      padding: 0.3rem;
      margin-left: 0.5rem;
      background-color: var(--input-background);
      border: 1px solid var(--input-border);
      border-radius: 4px;
      color: var(--text-color);
    }
  
    input[type="checkbox"] {
      margin-right: 0.5rem;
    }
  
    .generate-btn, .copy-btn {
      width: 100%;
      padding: 0.8rem;
      background-color: var(--primary-color);
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
  
    .generate-btn:hover, .copy-btn:hover {
      background-color: var(--secondary-color);
    }
  
    .password-display {
      display: flex;
      gap: 0.5rem;
      margin-top: 1.5rem;
    }
  
    .password-display input {
      flex-grow: 1;
      padding: 0.8rem;
      background-color: var(--input-background);
      border: 1px solid var(--input-border);
      border-radius: 5px;
      font-size: 1rem;
      color: var(--text-color);
    }
  
    
  
     @media (max-width: 480px) {
       .password-generator {
         padding: 1.5rem; 
       }
  
       .password-display {
         flex-direction: column; 
       }
  
       .copy-btn {
         margin-top: 0.5rem; 
       }
     }
  </style>