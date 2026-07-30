# 🔍 Day 4: Digital Forensics - Network Packet Analysis & Data Exfiltration

## 📋 Prezentare Generală (Overview)
Provocarea de astăzi a simulat un incident de securitate de tip **Data Exfiltration** (scurgere de date). Analizând traficul de rețea, am descoperit un comportament suspect: o cerere repetată la fiecare secundă către un port specific (`8080`), care ascundea un canal de comunicare mascat.

## 🛠️ Investigarea și Depanarea (Troubleshooting & Analysis)
### 1. Ocolirea Blocajelor de Mediu
* Din cauza unor limitări și restricții tehnice întâlnite în mediul preconfigurat (AttackBox), am decis să mut imediat investigația local, pe propriul sistem, folosind **Wireshark** pentru a analiza fișierul de captură `traffic.pcapng`.

### 2. Analiza Traficului de Rețea (Wireshark)
* Aplicând un filtru pe portul TCP `8080`, am identificat descărcarea unui fișier suspect de tip script Python (`updates.py`) și o serie lungă de cereri HTTP repetate care trimiteau date.
* Urmărind fluxul TCP (**TCP Stream**), am extras codul sursă al programului malware care rula în fundal: un keylogger bazat pe librăria `pynput` care capta tastele pe care le apăsa utilizatorul.

### 3. Decriptarea și Reasamblarea Datelor
* **Mecanismul descoperit:** Scriptul cripta fiecare caracter tastat folosind o operație **XOR** (cu o cheie hardcodată: `H0t3lSt@ff0NlyK3epS3cr3t!`), transforma rezultatul în **Base64** și îl expedia prin intermediul antetului HTTP de tip Cookie (`hotel_sess_state`).
* Pentru a recupera mesajul complet fără muncă manuală, am scris un script rapid în Python folosind librăria `scapy` ca să parsez pachetele, să decodific Base64 și să aplic cheia XOR inversă.
* În urma rulării scriptului, am extras cu succes mesajul complet și flag-ul corespunzător: `THM{V3r4_1s_w4tch1ng_0veR_y0u}`.

---
## 💡 Lecții Învățate / Concluzii
* **Analiza Traficului (PCAP):** Am înțeles cum își ascund atacatorii datele în canale apparent legitime (cum ar fi antetele HTTP/Cookies), o abilitate esențială pentru zona de securitate și investigații.
* **Automatizarea cu Python:** Când metodele manuale devin ineficiente din cauza volumului mare de date, scrierea unui script de decodare salvează timp prețios și rezolvă problema eficient.
