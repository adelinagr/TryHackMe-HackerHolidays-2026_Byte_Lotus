# 🕵️‍♂️ Day 0: OSINT - Byte Lotus Hotel Investigation

## 📋 Prezentare Generală (Overview)
Provocarea a constat într-o investigație de tip Open Source Intelligence (OSINT). Obiectivul a fost analizarea prezenței online a unui hotel fictiv (Byte Lotus Hotel), urmărirea amprentelor digitale lăsate de imagini și descoperirea unei conexiuni ascunse care a dus în final la extragerea flag-ului.

## 🛠️ Metodologie și Pași de Investigație

### 1. Igiena Digitală și Pregătirea
* Pentru a preveni scurgerea de informații personale sau lăsarea de "urme" pe profilurile țintă, investigația a fost realizată folosind un **cont fals (burner account)** dedicat exclusiv operațiunilor de OSINT.

### 2. Reconnaissance (Recunoaștere inițială)
* Am accesat pagina oficială de Instagram a *Byte Lotus Hotel*.
* În loc să mă limitez doar la feed-ul principal (unde eroarea vizuală semnala amprente de tip AI în imaginea de prezentare), am trecut la o analiză structurală a rețelei sociale a paginii (followers, following, interacțiuni, comentarii).

### 3. Pivotarea și Descoperirea (The Pivot)
* Verificând lista de *followers* și conturile asociate, am descoperit un cont secundar care nu era menționat în materialele oficiale de marketing ale hotelului: **Vera** (asistentul virtual).
* Investigarea acestui profil secundar a scos la iveală **3 postări suspecte**.

### 4. Extragerea și Decodarea Datelor (Exploitation)
* Fiecare dintre cele 3 postări conținea un șir de caractere codat în format **Base64**.
* **Procesul de decodare:** Am extras fragmentele, le-am unit în ordinea corectă și le-am trecut prin unealta de decodare **CyberChef**.
* În urma decodării Base64, textul rezultat a dezvăluit flag-ul oficial al provocării (`THM{...}`).

---
## 💡 Lecții Învățate / Concluzii
* **Nu ignora marginile imaginii sau detaliile adiacente:** Detaliile ascunse se află adesea în sub-pagini, conturi secundare sau conexiuni ignorate de marketingul oficial (cum a fost cazul asistentului virtual Vera).
* **Valoarea conturilor burner:** Utilizarea unei identități alternative protejează confidențialitatea investigatorului în scenarii reale de OSINT.
