# MEDE IISC · U18 · Wearable: mișcare și efort

**Autor:** Blîndu Delia-Valentina 
**Unitate:** persoană × fereastră de 5 s

**Întrebare:** Cât ajută pulsul, pe lângă accelerometru, să deosebim activitățile și nivelurile de efort, la persoane diferite?

## Surse
- **S1 · IMU** (accelerometru + giroscop, 100 Hz) și **S2 · puls** (~9 Hz): PAMAP2, https://archive.ics.uci.edu/dataset/231 (CC BY 4.0)
- **S3 · valori MET** pe activitate: 2024 Adult Compendium of Physical Activities, https://pacompendium.com

Datele brute nu sunt în repo. Detalii pe sursă: [`datacard_U18.md`](datacard_U18.md). 

## Rulare (Kaggle)
1. Importă `CP1_U18_pipeline.ipynb`.
2. Adaugă ca Input PAMAP2 (`subject101.dat` … `subject109.dat`) și PDF-ul Compendium.
3. Rulează celulele de sus în jos: încărcare S1, S2, S3, aliniere la ferestre de 5 s, raport de acoperire, `datacard_U18.md`.
