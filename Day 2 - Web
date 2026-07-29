# 🌐 Day 2: Web Security - Room 404 & Exposed Git Repository

## 📋 Prezentare Generală (Overview)
Provocarea a presupus investigarea unei aplicații web rulate pe portul `8080`. Dezvoltatorul aplicației a lăsat din greșeală directorul de configurare Git pe serverul de producție, permițând scurgerea codului sursă.

## 🛠️ Metodologie și Pași de Investigație

### 1. Enumerare și Detectare
* Accesând mașina țintă pe portul `8080`, am navigat în directorul aplicației expuse.
* Folosind comanda `ls -la`, am descoperit prezența unui folder ascuns `.git`, o vulnerabilitate critică de tip **Git Directory Exposure**.

### 2. Recuperarea Codului Sursă (Reconstruction)
* Deoarece directorul `.git` conținea istoricul și fișierele proiectului, am folosit comanda `git checkout -- .` pentru a restabili și extrage fișierele sursă direct în directorul curent.
* O listare ulterioară (`ls`) a scos la iveală fișierele proiectului: `README.md`, `app.js` și `index.html`.

### 3. Analiza Fișierelor și Extragerea Flag-ului
* Luând fișierele la rând pentru analiză (folosind comenzi precum `cat` sau editorul `vim`), am verificat conținutul acestora.
* În interiorul fișierului `README.md`, descrierea menționa că acesta este un repository intern de staging lăsat din greșeală în producție.
* Acolo am găsit și flag-ul oficial:
    * `THM{byt3_l0tus_n3v3r_f0rg3ts}`

---
## 💡 Lecții Învățate / Concluzii
* **Riscul fișierelor `.git` în producție:** Lăsarea folderului `.git` expus pe un server web este o eroare gravă de configurare (misconfiguration). Oricine poate descărca întregul istoric al codului sursă, parolele sau comentariile ascunse din commit-uri.
* **Importanța enumerării:** Verificarea fișierelor ascunse (cu `-la`) este un pas obligatoriu în evaluarea securității oricărei aplicații web (Web Reconnaissance).
