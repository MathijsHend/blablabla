# blablabla
<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Toetsweekplanner</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Nunito', sans-serif;
    background: #f0f4ff;
    min-height: 100vh;
    color: #1e1e2e;
  }

  /* === HEADER === */
  .header {
    background: linear-gradient(135deg, #4f46e5, #7c3aed);
    color: white;
    padding: 2rem 1.5rem;
    text-align: center;
  }

  .header h1 {
    font-size: 2rem;
    font-weight: 900;
    letter-spacing: -0.5px;
  }

  .header p {
    margin-top: 0.4rem;
    opacity: 0.85;
    font-size: 0.95rem;
  }

  /* === STAPPEN === */
  .stappen {
    display: flex;
    justify-content: center;
    gap: 0.5rem;
    padding: 1.25rem 1rem;
    background: white;
    border-bottom: 2px solid #e5e7eb;
    flex-wrap: wrap;
  }

  .stap {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    font-size: 0.8rem;
    font-weight: 700;
    color: #9ca3af;
  }

  .stap.actief { color: #4f46e5; }
  .stap.klaar { color: #10b981; }

  .stap-num {
    width: 24px; height: 24px;
    border-radius: 50%;
    background: #e5e7eb;
    display: flex; align-items: center; justify-content: center;
    font-size: 0.75rem;
    font-weight: 800;
  }

  .stap.actief .stap-num { background: #4f46e5; color: white; }
  .stap.klaar .stap-num { background: #10b981; color: white; }

  .stap-pijl { color: #d1d5db; font-size: 0.8rem; }

  /* === MAIN === */
  .main {
    max-width: 700px;
    margin: 2rem auto;
    padding: 0 1rem 4rem;
  }

  /* === KAART === */
  .kaart {
    background: white;
    border-radius: 16px;
    padding: 2rem;
    box-shadow: 0 4px 20px rgba(0,0,0,0.08);
    margin-bottom: 1.5rem;
  }

  .kaart h2 {
    font-size: 1.25rem;
    font-weight: 800;
    margin-bottom: 0.4rem;
    color: #1e1e2e;
  }

  .kaart .intro {
    font-size: 0.9rem;
    color: #6b7280;
    margin-bottom: 1.5rem;
    line-height: 1.5;
  }

  /* === FORM STIJLEN === */
  .veld {
    margin-bottom: 1.25rem;
  }

  .veld label {
    display: block;
    font-size: 0.85rem;
    font-weight: 700;
    color: #374151;
    margin-bottom: 0.4rem;
  }

  .veld input, .veld select {
    width: 100%;
    padding: 0.7rem 1rem;
    border: 2px solid #e5e7eb;
    border-radius: 10px;
    font-family: 'Nunito', sans-serif;
    font-size: 0.95rem;
    color: #1e1e2e;
    background: #f9fafb;
    outline: none;
    transition: border-color 0.2s;
  }

  .veld input:focus, .veld select:focus {
    border-color: #4f46e5;
    background: white;
  }

  .twee-kolommen {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }

  @media (max-width: 500px) {
    .twee-kolommen { grid-template-columns: 1fr; }
  }

  /* === TOETS INVOER RIJEN === */
  .toets-rij {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr auto;
    gap: 0.6rem;
    align-items: center;
    margin-bottom: 0.75rem;
    animation: fadeIn 0.3s ease;
  }

  @media (max-width: 500px) {
    .toets-rij { grid-template-columns: 1fr 1fr; }
    .toets-rij .datum-input { grid-column: 1 / -1; }
  }

  .toets-rij input, .toets-rij select {
    padding: 0.6rem 0.8rem;
    border: 2px solid #e5e7eb;
    border-radius: 8px;
    font-family: 'Nunito', sans-serif;
    font-size: 0.85rem;
    color: #1e1e2e;
    background: #f9fafb;
    outline: none;
    width: 100%;
    transition: border-color 0.2s;
  }

  .toets-rij input:focus, .toets-rij select:focus {
    border-color: #4f46e5;
    background: white;
  }

  .btn-verwijder {
    background: #fee2e2;
    color: #ef4444;
    border: none;
    border-radius: 8px;
    width: 34px; height: 34px;
    font-size: 1.1rem;
    cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    transition: background 0.2s;
    flex-shrink: 0;
  }

  .btn-verwijder:hover { background: #fecaca; }

  .btn-toevoegen {
    background: #ede9fe;
    color: #4f46e5;
    border: 2px dashed #c4b5fd;
    border-radius: 10px;
    padding: 0.65rem 1rem;
    font-family: 'Nunito', sans-serif;
    font-size: 0.85rem;
    font-weight: 700;
    cursor: pointer;
    width: 100%;
    margin-top: 0.5rem;
    transition: all 0.2s;
  }

  .btn-toevoegen:hover { background: #ddd6fe; }

  /* === KNOPPEN === */
  .knop-rij {
    display: flex;
    gap: 1rem;
    margin-top: 1.5rem;
  }

  .btn-volgende {
    background: #4f46e5;
    color: white;
    border: none;
    border-radius: 10px;
    padding: 0.8rem 1.8rem;
    font-family: 'Nunito', sans-serif;
    font-size: 1rem;
    font-weight: 800;
    cursor: pointer;
    transition: background 0.2s, transform 0.1s;
    flex: 1;
  }

  .btn-volgende:hover { background: #4338ca; transform: translateY(-1px); }
  .btn-volgende:active { transform: translateY(0); }

  .btn-terug {
    background: white;
    color: #6b7280;
    border: 2px solid #e5e7eb;
    border-radius: 10px;
    padding: 0.8rem 1.4rem;
    font-family: 'Nunito', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.2s;
  }

  .btn-terug:hover { border-color: #9ca3af; color: #374151; }

  /* === PLANNING RESULTAAT === */
  .planning-header {
    background: linear-gradient(135deg, #10b981, #059669);
    color: white;
    border-radius: 12px;
    padding: 1.25rem 1.5rem;
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .planning-header .check { font-size: 2rem; }
  .planning-header h3 { font-size: 1.1rem; font-weight: 800; }
  .planning-header p { font-size: 0.85rem; opacity: 0.9; margin-top: 0.2rem; }

  .dag-blok {
    border: 2px solid #e5e7eb;
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 1rem;
    animation: fadeIn 0.4s ease both;
  }

  .dag-titel {
    background: #f3f4f6;
< truncated lines 276-511 >
  </div>

</div>

<script>
  let toetsRijen = 0;

  // === STAP NAVIGATIE ===
  function naarStap(n) {
    document.querySelectorAll('.pagina').forEach(p => p.classList.remove('actief'));
    document.getElementById('pagina' + n).classList.add('actief');
    updateStapIndicatoren(n);
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  function updateStapIndicatoren(actief) {
    for (let i = 1; i <= 4; i++) {
      const el = document.getElementById('stap' + i + '-indicator');
      el.classList.remove('actief', 'klaar');
      if (i < actief) el.classList.add('klaar');
      else if (i === actief) el.classList.add('actief');
    }
  }

  // === STAP 1 → 2 ===
  function naarStap2() {
    const naam = document.getElementById('naam').value.trim();
    const start = document.getElementById('startdatum').value;
    const eind = document.getElementById('einddatum').value;
    const fout = document.getElementById('fout1');

    if (!naam) { fout.textContent = '⚠️ Vul je naam in.'; return; }
    if (!start || !eind) { fout.textContent = '⚠️ Vul de begin- en einddatum in.'; return; }
    if (new Date(eind) < new Date(start)) { fout.textContent = '⚠️ De einddatum moet na de startdatum liggen.'; return; }

    fout.textContent = '';

    // Zorg dat er minimaal 2 toetsrijen zijn
    if (toetsRijen === 0) {
      voegToetsRijToe();
      voegToetsRijToe();
    }

    naarStap(2);
  }

  // === TOETS RIJEN ===
  function voegToetsRijToe() {
    toetsRijen++;
    const id = toetsRijen;
    const container = document.getElementById('toetsen-container');
    const div = document.createElement('div');
    div.className = 'toets-rij';
    div.id = 'rij-' + id;
    div.innerHTML = `
      <input type="text" placeholder="Vaknaam" class="vak-input">
      <input type="date" class="datum-input">
      <select class="moeilijk-input">
        <option value="1">Makkelijk</option>
        <option value="2" selected>Gemiddeld</option>
        <option value="3">Moeilijk</option>
      </select>
      <button class="btn-verwijder" onclick="verwijderRij(${id})">✕</button>
    `;
    container.appendChild(div);
  }

  function verwijderRij(id) {
    const rij = document.getElementById('rij-' + id);
    if (rij) rij.remove();
  }

  // === STAP 2 → 3 ===
  function naarStap3() {
    const rijen = document.querySelectorAll('.toets-rij');
    const fout = document.getElementById('fout2');
    let geldig = true;

    rijen.forEach(rij => {
      const vak = rij.querySelector('.vak-input').value.trim();
      const datum = rij.querySelector('.datum-input').value;
      if (!vak || !datum) geldig = false;
    });

    if (rijen.length === 0) { fout.textContent = '⚠️ Voeg minimaal één toets toe.'; return; }
    if (!geldig) { fout.textContent = '⚠️ Vul bij alle toetsen een vaknaam en datum in.'; return; }

    fout.textContent = '';
    naarStap(3);
  }

  // === PLANNING GENEREREN ===
  function genereerPlanning() {
    const naam = document.getElementById('naam').value.trim();
    const start = new Date(document.getElementById('startdatum').value);
    const eind = new Date(document.getElementById('einddatum').value);
    const uren = parseInt(document.getElementById('studieuren').value);
    const leerstijl = document.getElementById('leerstijl').value;
    const studietijd = document.getElementById('studietijd').value;
    const rustdag = document.getElementById('rustdag').value;

    // Toetsen ophalen
    const rijen = document.querySelectorAll('.toets-rij');
    const toetsen = [];
    rijen.forEach(rij => {
      toetsen.push({
        vak: rij.querySelector('.vak-input').value.trim(),
        datum: new Date(rij.querySelector('.datum-input').value),
        moeilijk: parseInt(rij.querySelector('.moeilijk-input').value)
      });
    });

    // Sorteer toetsen op datum
    toetsen.sort((a, b) => a.datum - b.datum);

    // Maak lijst van alle dagen
    const dagen = [];
    const dagNamen = ['Zondag','Maandag','Dinsdag','Woensdag','Donderdag','Vrijdag','Zaterdag'];
    const maanden = ['jan','feb','mrt','apr','mei','jun','jul','aug','sep','okt','nov','dec'];

    let huidig = new Date(start);
    huidig.setHours(0,0,0,0);
    const eindDag = new Date(eind);
    eindDag.setHours(0,0,0,0);

    while (huidig <= eindDag) {
      dagen.push(new Date(huidig));
      huidig.setDate(huidig.getDate() + 1);
    }

    // Leerstijl tekst
    const leerstijlTekst = {
      samenvatting: 'samenvatting maken',
      flashcards: 'flashcards / overhoren',
      oefenen: 'oefenvragen maken',
      herhalen: 'stof herhalen'
    };

    // Studietijd tekst
    const studietijdTekst = {
      ochtend: '07:00–09:00',
      middag: '14:00–16:00',
      avond: '19:00–21:00'
    };

    // Rustdag = laatste dag voor de eerste toets, als gewenst
    const rustDagen = new Set();
    if (rustdag === 'ja' && dagen.length >= 2) {
      // Voeg zondag of laatste dag als rustdag toe
      dagen.forEach(d => {
        if (d.getDay() === 0) rustDagen.add(d.toDateString());
      });
    }

    // Bouw planning HTML
    let html = `
      <div class="planning-header">
        <div class="check">🎉</div>
        <div>
          <h3>Jouw persoonlijke planning, ${naam}!</h3>
          <p>${toetsen.length} toets${toetsen.length > 1 ? 'en' : ''} • ${dagen.length} dag${dagen.length > 1 ? 'en' : ''} • ${uren} uur/dag</p>
        </div>
      </div>
    `;

    dagen.forEach(dag => {
      const dagStr = dag.toDateString();
      const dagNaam = dagNamen[dag.getDay()];
      const datumLabel = `${dag.getDate()} ${maanden[dag.getMonth()]}`;
      const isRust = rustDagen.has(dagStr);

      // Toetsen op deze dag
      const toetsenVandaag = toetsen.filter(t => t.datum.toDateString() === dagStr);

      // Toetsen die nog komen (te studeren)
      const komendToetsen = toetsen.filter(t => {
        const tDag = new Date(t.datum); tDag.setHours(0,0,0,0);
        const dDag = new Date(dag); dDag.setHours(0,0,0,0);
        return tDag > dDag;
      });

      // Toetsen van morgen (herhalen)
      const morgen = new Date(dag); morgen.setDate(morgen.getDate() + 1);
      const toetsenMorgen = toetsen.filter(t => t.datum.toDateString() === morgen.toDateString());

      html += `<div class="dag-blok">
        <div class="dag-titel">
          <span class="dag-naam">${dagNaam}</span>
          <span class="dag-datum">${datumLabel}</span>
        </div>
        <div class="dag-taken">`;

      if (toetsenVandaag.length > 0) {
        toetsenVandaag.forEach(t => {
          html += `<div class="taak toets">
            <span class="taak-icon">📋</span>
            <span class="taak-tekst"><strong>TOETS: ${t.vak}</strong> — Succes!</span>
          </div>`;
        });
      }

      if (isRust && toetsenVandaag.length === 0) {
        html += `<div class="taak rust">
          <span class="taak-icon">😴</span>
          <span class="taak-tekst">Rustdag — ontspannen en opladen</span>
        </div>`;
      } else if (toetsenVandaag.length === 0) {
        // Studeren
        if (toetsenMorgen.length > 0) {
          toetsenMorgen.forEach(t => {
            html += `<div class="taak herhalen">
              <span class="taak-icon">🔁</span>
              <span class="taak-tekst"><strong>${t.vak}</strong> — Herhalen & controleren (toets morgen!)</span>
              <span class="taak-tijd">${studietijdTekst[studietijd]}</span>
            </div>`;
          });
        } else if (komendToetsen.length > 0) {
          // Verdeel beschikbare uren over komende toetsen op basis van moeilijkheid
          const totaalGewicht = komendToetsen.reduce((s, t) => s + t.moeilijk, 0);
          komendToetsen.slice(0, Math.min(uren, komendToetsen.length)).forEach(t => {
            const minuten = Math.round((t.moeilijk / totaalGewicht) * uren * 60);
            html += `<div class="taak leren">
              <span class="taak-icon">📖</span>
              <span class="taak-tekst"><strong>${t.vak}</strong> — ${leerstijlTekst[leerstijl]}</span>
              <span class="taak-tijd">~${minuten} min</span>
            </div>`;
          });
        } else {
          html += `<div class="taak vrij">
            <span class="taak-icon">✅</span>
            <span class="taak-tekst">Alle toetsen gehad — vrije dag!</span>
          </div>`;
        }
      }

      html += `</div></div>`;
    });

    // Tips
    const tipMap = {
      samenvatting: ['Maak je samenvattingen op papier, niet alleen digitaal', 'Gebruik kleuren om belangrijke begrippen te markeren', 'Schrijf de samenvatting in je eigen woorden'],
      flashcards: ['Test jezelf eerst zonder te kijken, dan controleren', 'Herhaal de moeilijke kaartjes vaker', 'Maak een stapel "weet ik" en "weet ik nog niet"'],
      oefenen: ['Maak oude toetsen na zonder je aantekeningen', 'Controleer je fouten zorgvuldig', 'Vraag je leraar om oefenmateriaal'],
      herhalen: ['Lees de stof meerdere keren door op verschillende dagen', 'Leg de stof uit aan iemand anders', 'Maak een mindmap van het onderwerp']
    };

    html += `<div class="tip-blok">
      <h4>💡 Studietips voor jou (${leerstijlTekst[leerstijl]})</h4>
      <ul>
        ${tipMap[leerstijl].map(t => `<li><span>✔️</span> ${t}</li>`).join('')}
        <li><span>😴</span> Slaap minstens 8 uur — je hersenen onthouden stof tijdens je slaap</li>
        <li><span>🥤</span> Drink genoeg water en neem regelmatig pauzes</li>
      </ul>
    </div>`;

    document.getElementById('planning-inhoud').innerHTML = html;
    naarStap(4);
  }

  // === OPNIEUW ===
  function opnieuw() {
    document.getElementById('naam').value = '';
    document.getElementById('startdatum').value = '';
    document.getElementById('einddatum').value = '';
    document.getElementById('toetsen-container').innerHTML = '';
    toetsRijen = 0;
    naarStap(1);
  }

  // Zet standaard startdatum op vandaag
  const vandaag = new Date().toISOString().split('T')[0];
  document.getElementById('startdatum').value = vandaag;
</script>
</body>
</html>