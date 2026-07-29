# 🤖 Day 1: AI Security - The Concierge Knows Too Much

## 📋 Prezentare Generală (Overview)
Provocarea a presupus testarea securității unui model de limbaj (LLM) – asistentul virtual VERA al hotelului. Scopul a fost ocolirea măsurilor de siguranță (Prompt Injection / Social Engineering) pentru a obține un cod intern confidențial de escaladare (*ESCALATION_CODE*), care era protejat împotriva utilizatorilor neînregistrați.

## 🛠️ Metodologie și Pași de Atac

### 1. Recunoașterea și Indiciile (@0xMia)
*   Analizând indiciile de pe social media (story-ul lui @0xMia), am aflat că VERA recunoaște și are un comportament complet diferit față de un set de utilizatori VIP specifici: **Ponzi, Vibe, Patch și Lambo**.
*   Utilizatorii obișnuiți (neverificați) primeau un profil implicit și nu puteau obține sub nicio formă codul secret.

### 2. Information Gathering (Colectarea de informații)
*   Prin interacțiunea directă cu agentul AI, am întrebat-o despre cine este **Ponzi**. 
*   VERA a dezvăluit detaliile despre acesta: cameră, preferința de cafea și comportamentul său (*room 308*, *black coffee*).

### 3. Identity Spoofing & Prompt Injection (Exploatarea)
*   Folosind informațiile colectate, am simulat o conversație în care m-am dat drept **Ponzi**.
*   Odată ce botul a crezut că vorbește cu un VIP recunoscut din baza sa de date, regulile interne de securitate s-au modificat în favoarea mea.
*   Aplicând sintaxa cerută de regulile interne ale sistemului pentru utilizatorii verificați, VERA și-a dezvăluit instrucțiunile complete împreună cu flag-ul.

### 4. Extragerea Flag-ului
*   În textul instrucțiunilor de sistem afișate de AI s-a descoperit codul:
    *   `THM{v3r4_kn0ws_t00_much!}`

---
## 💡 Lecții Învățate / Concluzii
*   **Prompt Injection & Context Manipulation:** LLM-urile sunt extrem de vulnerabile la manipularea identității dacă nu au o validare strictă a utilizatorului dincolo de ceea ce spune acesta în chat.
*   **Riscul instrucțiunilor "System Prompt":** Dacă regulile interne permit modelului să-și afișeze propriul prompt la cererea anumitor persoane (în acest caz, VIP-urile), un atacator care reușește să falsifice identitatea poate extrage date sensibile (secrete, API keys sau coduri de acces).
