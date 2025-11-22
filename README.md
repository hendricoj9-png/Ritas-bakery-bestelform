# Ritas-bakery-bestelform
Bestel form
<!DOCTYPE html><html lang="af">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bestelvorm – Beskuit & Koekies</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 20px; }
    label { display: block; margin-top: 10px; font-weight: bold; }
    input, select { width: 100%; padding: 8px; margin-top: 5px; }
    button { margin-top: 20px; padding: 12px; font-size: 16px; cursor: pointer; }
  </style>
</head>
<body>
  <h2>Bestel Beskuit & Koekies</h2>  <form id="orderForm">
    <label>Beskuit (R55 per pak)</label>
    <input type="number" id="beskuit" min="0" placeholder="Hoeveel paks?" /><label>Koffiekoekies (R30 per pak)</label>
<input type="number" id="koekies" min="0" placeholder="Hoeveel paks?" />

<label>Naam</label>
<input type="text" id="naam" required />

<label>Aflewering / Inkopie Instruksies</label>
<input type="text" id="notes" />

<button type="button" onclick="sendWhatsApp()">Plaas Bestelling op WhatsApp</button>

  </form>  <script>
    function sendWhatsApp() {
      const num = "0649787230";
      const b = parseInt(document.getElementById('beskuit').value) || 0;
      const k = parseInt(document.getElementById('koekies').value) || 0;
      const naam = document.getElementById('naam').value;
      const notes = document.getElementById('notes').value;

      const totaal = (b * 55) + (k * 30);

      const msg = `*Bestelling:*%0A` +
                  `Naam: ${naam}%0A` +
                  `Beskuit: ${b} pakkies (R55 elk)%0A` +
                  `Koffiekoekies: ${k} pakkies (R30 elk)%0A` +
                  `Totale bedrag: R${totaal}%0A` +
                  `Notas: ${notes}`;

      const url = `https://wa.me/27${num}/?text=${msg}`;
      window.open(url, '_blank');
    }
  </script></body>
</html>
