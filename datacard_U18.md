# Data card · U18 (persoană × fereastră de 5 s)

## S1 · IMU (accelerometru + giroscop)
- **Proveniență:** PAMAP2 Physical Activity Monitoring, UCI Machine Learning Repository (Reiss & Stricker, 2012), https://archive.ics.uci.edu/dataset/231
- **Perioadă:** 1 subiecți, 1.0 h în total; timp relativ în secunde de la începutul înregistrării (setul nu conține date calendaristice).
- **Rezoluție spațială:** 3 poziții pe corp (mână, piept, gleznă); fără componentă geografică.
- **Rezoluție temporală:** ~100 Hz. După aliniere: ferestre de 5 s.
- **Unități:** accelerație m/s² (±16g și ±6g), giroscop rad/s, magnetometru µT, temperatură °C.
- **Goluri:** 0.4% valori lipsă la accelerometrul de la mână; activitatea 0 (tranziții) exclusă din analiză; orientarea e invalidă și nu se folosește.
- **Licență:** CC BY 4.0.
- **n × d:** 376,417 rânduri × 42 coloane. Activități folosite: 1 lying, 2 sitting, 3 standing, 4 walking, 5 running, 6 cycling, 7 Nordic walking, 12 ascending stairs, 13 descending stairs, 16 vacuum cleaning, 17 ironing, 24 rope jumping.

## S2 · Puls (monitor separat)
- **Proveniență:** același set PAMAP2, dar măsurat de un monitor de puls separat de senzorii IMU.
- **Perioadă:** aceeași ca la S1.
- **Rezoluție spațială:** nu se aplică (un singur punct de măsură, la persoană).
- **Rezoluție temporală:** ~9.1 Hz efectiv (34,389 valori de puls). După aliniere: media pe fereastră de 5 s.
- **Unități:** bătăi pe minut (bpm).
- **Goluri:** 90.9% din rândurile fișierelor nu au puls, dar asta se datorează frecvenței (~9 Hz față de 100 Hz), nu unor date lipsă. La nivel de fereastră de 5 s, 100.0% dintre ferestre au cel puțin o valoare de puls; cel mai lung interval fără puls este 0.5 s; 0.00% dintre valori sunt în afara intervalului 30–220 bpm.
- **Licență:** CC BY 4.0.
- **n × d:** 34,389 rânduri × 1 variabilă de puls.

## S3 · Valori MET pe activitate (referință de efort)
- **Proveniență:** 2024 Adult Compendium of Physical Activities (Herrmann et al., 2024), https://pacompendium.com; fiecare activitate din PAMAP2 e legată de un rând al Compendium (cod în `S3`).
- **Perioadă:** tabel de referință, fără dimensiune temporală (versiunea 2024).
- **Rezoluție spațială / temporală:** nu se aplică; o valoare pe tip de activitate.
- **Unități:** MET (multipli ai consumului de energie în repaus).
- **Goluri:** 12 din 12 activități au valoare MET asociată; alegerea rândului Compendium este o decizie de aliniere semantică (PAMAP2 nu are viteze).
- **Licență:** de verificat pe pacompendium.com înainte de predare.
- **n × d:** 12 rânduri (activități) × 3 coloane utile (cod, MET, descriere).

## Aliniere
492 ferestre de 5 s (persoană × fereastră), păstrate doar cele cu activitate dominantă (≥ 80% din rânduri). Acoperire: puls 100.0%, MET 100.0%, toate trei 100.0%.
