# ☁️ Day 3: Cloud Security - AWS Credentials & Troubleshooting

## 📋 Prezentare Generală (Overview)
Provocarea a presupus investigarea unui mediu Cloud (AWS), unde a fost necesară configurarea instrumentelor de linie de comandă (`AWS CLI`) pentru a accesa și extrage resurse dintr-un serviciu de tip stocare/bază de date (DynamoDB).

## 🛠️ Provocări și Depanare (Troubleshooting & Adaptation)
### 1. Blocajul Inițial (The Environment Bottleneck)
* În timpul rulării pașilor direct din mașina virtuală furnizată (AttackBox), am întâmpinat limitări tehnice legate de clipboard (copy-paste) și sincronizarea comenzilor, ceea ce îngreuna execuția rapidă a operațiunilor.

### 2. Ruta Alternativă (Adaptabilitatea)
* În loc să mă blochez, am decis să schimb mediul de lucru: am renunțat la VM-ul din browser și am mutat operațiunea local, configurând **AWS CLI direct în PowerShell pe Windows**.
* Pentru a rula comenzile securizat și corect, am definit variabilele de mediu necesare direct în sesiunea de PowerShell folosind sintaxa specifică (`$env:AWS_ACCESS_KEY_ID`, `$env:AWS_SECRET_ACCESS_KEY`).

### 3. Extragerea Datelor și Finalizarea
* Odată configurat mediul local și stabilite credențialele, am interogat serviciul AWS pentru a extrage datele ascunse și a finaliza provocarea, obținând flag-ul aferent.

---
## 💡 Lecții Învățate / Concluzii
* **Flexibilitatea în Infrastructură:** Un analist sau inginer bun nu se blochează atunci când un mediu preconfigurat (cum e un lab VM) nu colaborează. Capacitatea de a muta fluxul de lucru pe propriul sistem (PowerShell / Windows) și de a configura instrumente Cloud din mers este un skill extrem de valoros.
* **Gestionarea Credențialelor Cloud:** Înțelegerea modului în care funcționează variabilele de mediu pentru autentificarea în AWS este esențială atât pentru atac (pentru a exploata chei lăsate neprotejate), cât și pentru apărare (pentru a monitoriza accesul neautorizat).
