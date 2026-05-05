# Proiect-BD-farmacie

## 1. Descrierea modelului real, a utilitatii acestuia si regulilor de functionare

O apliceatie pentru gestionarea personalului cat si al stocului si vanzariilor intr-o farmacie, ofera utilizatorilor (farmacistilor) posibilitatea sa gestioneze toate informatiile necesare pentru buna functionare a farmaciei. Fiecare medicament si angajat sunt identificati printr-un numar unic de identificare, pentru medicamente vom cunoaste: numele acestora, substanta activa, vom cunoaste daca este nevoie de prescriptie pentru a fi achitat, pretul si data expirarii. Iar pentru angajati vom stii: numele, cnp-ul, numarul de telefon, salariul si programul acestora.

Farmacia va tine in evidenta un istoric de vanzari, unde vom pastra email-ul, numele si prenumele clinteiilor, pe care se va afla medicamentele cumparate si prescriptia (daca este nevoie), pret-ul achitat si data achitarii.

Suplimentar, vom tine cont de firmele de la care se cumpara stocul, vom sti pretul platit pe marfa.

## 2. Prezentarea constrângerilor (restricții, reguli) impuse asupra modelului
  Aici probabil e destul de optional
## 3. Descrierea entităților, incluzând precizarea cheii primare.
  ### ANGAJAT:
  - persoana care se ocupa de vanzare/stocare
  - cheie primara: angajat_id
  ### CLIENT:
  - persoana care cumpara medicamente 
  - cheie primara: client_id
  ### VANZARE:
  - face legatura intre medicament si client
  - cheie primara: vanzare_id
  ### BON:
  - face suma totala dupa cumpararea medicamentelor, entitate asociativa
  - cheie primara: bon_id
  ### INTRARE_STOC:
  - face legatura intre stoc si fabrica
  - cheie primara: intrare_stoc_id
  ### FABRICA:
  - organizatia care livreaza medicamente la farmacie
  - cheie primara: fabrica_id
  ### MEDICAMENT:
  - produsul vandut de farmacie
  - cheie primara: med_id
  ### RETETA:
  - fisa care o aduce clientul pentru achizitia medicamentelor semi-periculoase
  - cheie primara: reteta_id
## 4. Descrierea relațiilor, incluzând precizarea cardinalității acestora.
| RELATIE  | CARDINALITATE | OBSERVATII |
| ------------- | ------------- | --- |
|||
|||
## 5. Descrierea atributelor, incluzând tipul de date și eventualele constrângeri, valori implicite, valori posibile ale atributelor.
### ANGAJAT
| atribut | tip de date | constrangeri |
| ------------- | ------------- | ------------- |
| angajat_id | NUMBER | PK |
| nume | Varchar(20) |
| prenume | Varchar(20) |
| cnp | NVARCHAR(13) |

### VANZARE
| atribut | tip de date | constrangeri | 
| ------------- | ------------- | ------------- |
| vanzare_id | NUMBER | PK |
| data | DATE |

### MEDICAMENT
| atribut | tip de date | constrangeri |
| ------------- | ------------- | ------------- |
| med_id | NUMBER | PK |
| nume | Varchar(20) | NOT NULL |
| substanta activa | NVarchar(20) | NOT NULL |
| pret | NUMBER | NOT NULL |
| data_expirare | DATE | NOT NULL |
| necesita reteta | BOOLEAN | NOT NULL |

### CLIENT
| atribut | tip de date | constrangeri |
| ------------- | ------------- | ------------- |
| client_id | NUMBER | PK |
| nume | Varchar(20) |
| email | NVarchar(20) |
| nr_tel | NVarchar(20) |

### BON
| atribut | tip de date | constrangeri |
| ------------- | ------------- | ------------- |
| bon_id | NUMBER | PK |
| cantitate | NUMBER | NOT NULL |
| pret vanzare | NUMBER | NOT NULL |
| reducere | NUMBER |

### FABRICA
| atribut | tip de date | constrangeri |
| ------------- | ------------- | ------------- |
| fabrica_id | NUMBER | PK |
| nume | Varchar(20) | NOT NULL |
| produse | NUMBER | NOT NULL |
| nume produs | NVarchar(30) |

### INTRARI_STOC
| atribut | tip de date | constrangeri | 
| ------------- | ------------- | ------------- |
| intrari_stoc_id | NUMBER | PK |
| cantitate | NUMBER |
| cata_intrare | DATE |

### RETETA
| atribut | tip de date | constrangeri |
| ------------- | ------------- | ------------- |
| reteta_id | NUMBER | PK |
| medic_nume | Varchar(20) |
| data emitere | DATE | NOT NULL |
| data expirare | DATE | NOT NULL |
| serie numar | NVarchar(20) |

 ## 6. Realizarea diagramei entitate-relație corespunzătoare descrierii de la punctele 3-5
*Poza cu ce am nevoie*

## 7.ealizarea diagramei conceptuale corespunzătoare diagramei entitate-relație proiectate la punctul 6. Diagrama conceptuală obținută trebuie să conțină minimum 7 tabele (fără considerarea subentităților), dintre care cel puțin un tabel asociativ.
