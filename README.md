# 💧 Circuitul apei și vremea

Aplicație interactivă și materiale pentru **Lecția 39 — Circuitul apei și vremea** (Fizică Aplicată, Eva, Year 4 UK). Aplicația e un singur fișier `index.html`, fără biblioteci externe și fără internet.

👉 **Live:** https://beldugan.github.io/circuitul-apei-si-vremea/

## Cele trei module și cele două lecții

Modulele se deblochează pe rând: **1 · Circuitul apei → 📖 Lecția A + quiz → 2 · Fabrica de nori → 📖 Lecția B + quiz → 3 · Uragane și vremea**. Fiecare lecție are 5 cartonașe scurte (nivel Year 4 UK, cu cuvintele-cheie în engleză) și un quiz de 5 întrebări alese la întâmplare; trece cu minim **4 din 5 corecte din prima**. Progresul rămâne salvat în browser. Pentru profesor/părinte: în subsol, codul **39** deblochează tot sau resetează progresul.


### 1 · Circuitul apei

O scenă vie cu mare, munte, soare și 300 de picături care se plimbă la nesfârșit: evaporare → condensare → precipitații → scurgere și infiltrare. Fiecare bulină e aceeași cantitate de apă, iar culoarea ei arată unde se află.

| Reglajul | Ce se vede |
|---|---|
| Puterea soarelui | La 0, evaporarea se oprește de tot — soarele e motorul circuitului |
| Temperatura aerului | Sub 0 °C precipitațiile devin zăpadă și rămân pe munte; aerul rece ține mai puțini vapori, deci norul se umple mai repede |
| Vântul | Mută norul de deasupra mării peste munte, unde plouă și apa se întoarce prin râu |

Scenarii gata făcute: **zi de vară, iarnă, deșert, furtună**.

Cartonașul **„total"** nu se schimbă niciodată, orice ar face elevul. Asta e, de fapt, toată lecția: apa nu se pierde și nu se fabrică.

### 2 · Fabrica de nori

Varianta digitală a experimentului cu borcanul, descris pas cu pas în [`FISA-EXPERIMENT.md`](FISA-EXPERIMENT.md). Trei ingrediente — **apă caldă, gheață pe capac, fum** — și norul apare doar când sunt toate trei. Dacă lipsește unul, aplicația spune exact ce lipsește și de ce nu se întâmplă nimic. Capacul se poate ridica, iar norul se destramă.

### 3 · Uragane și taifunuri

Un simulator de furtună tropicală cu condițiile reale de formare:

- **temperatura apei** — sub 26,5 °C furtuna se stinge, la 31 °C ajunge categoria 5
- **forfecarea vântului** — mare, și furtuna nu se poate organiza
- **uscatul** — trage furtuna peste coastă cu mouse-ul și se stinge în câteva secunde
- **ecuatorul** — prea aproape de el, rotația nu pornește (forța Coriolis)
- **bazinul** — aceeași furtună se cheamă **uragan**, **taifun** sau **ciclon**, după locul nașterii
- **emisfera** — se rotește invers la sud de ecuator

Afișează viteza vântului, presiunea în hPa și categoria Saffir–Simpson, iar la peste 63 km/h furtuna primește un nume — exact ca în realitate.

Pe aceeași hartă se poate alege orice fel de vreme — **senin, ploaie, furtună cu fulgere, ninsoare, grindină, ceață, vânt tare, uragan** — și se poate schimba **direcția vântului** (8 direcții) și viteza lui. Norii, ploaia, valurile, copacii și mâneca de vânt de lângă „orașul tău" se schimbă după vânt; ceața se risipește când bate vântul, ploaia devine ninsoare sub 0 °C, iar la furtună se numără secundele dintre fulger și tunet (3 s ≈ 1 km). Harta are **zoom** (＋/－, rotița mouse-ului, două degete pe tabletă), mutare prin tragere, mini-hartă și butonul 🎯 care urmărește furtuna.

## Ce e în repo

```
index.html          aplicația (un singur fișier, fără dependențe)
LECTIE.md           planul de lecție, 50 de minute
FISA-EXPERIMENT.md  „Norul din borcan" — protocolul complet pentru elev
FISA-ELEV.md        fișa de lucru + baremul
materiale/          aceleași materiale, în PDF, gata de tipărit
.github/workflows/  publicarea automată pe GitHub Pages
```

## Cum o rulezi

- **Local:** dublu-click pe `index.html` (orice browser, fără internet).
- **Online:** adresa de mai sus, după publicare.

## Cum îl urci pe GitHub

Creează pe github.com un repository gol numit `circuitul-apei-si-vremea` (public, **fără** README, fără .gitignore, fără licență — sunt deja aici). Apoi, din folderul acesta:

```bash
git init -b main
git add .
git commit -m "Lecția 39 — Circuitul apei și vremea"
git remote add origin https://github.com/Beldugan/circuitul-apei-si-vremea.git
git push -u origin main
```

Apoi în repo: **Settings → Pages → Source: GitHub Actions**. Workflow-ul din `.github/workflows/pages.yml` publică singur la fiecare push, iar pagina apare în 1–2 minute.

> Merge și varianta clasică, **Settings → Pages → Deploy from a branch → main / (root)** — atunci workflow-ul nu mai e necesar.

## Sub capotă

Modulul 1 nu e o animație înregistrată: fiecare picătură își schimbă starea după reguli (rată de evaporare dependentă de soare și temperatură, capacitatea norului dependentă de temperatură, precipitații la depășirea ei), iar numărul total de picături e constant prin construcție.

Modulul 3 folosește condițiile reale de ciclogeneză tropicală: viteza spre care tinde furtuna crește cu temperatura apei peste pragul de 26,5 °C și scade cu forfecarea, cu apropierea de ecuator și cu trecerea peste uscat. Presiunea e calculată din viteza vântului, iar categoriile sunt cele din scara Saffir–Simpson.
