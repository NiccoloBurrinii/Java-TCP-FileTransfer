# Java TCP File Transfer: Evolution Project

Un percorso evolutivo in tre step che mostra come sviluppare un sistema di trasferimento file binari (PNG) via TCP, passando da un prototipo single-thread a un server multi-thread professionale.

## Panoramica
Il progetto implementa un sistema di download file Client-Server. L'obiettivo è dimostrare la gestione dei flussi di byte (byte streams) attraverso le Socket di Java e l'ottimizzazione delle performance tramite il multithreading.



---

## Le 3 Fasi dello Sviluppo

### STEP #1: Prototipo Single-Thread
La base del sistema. Un server semplice che accetta una connessione, invia un file predefinito e si chiude.
* **Focus**: Gestione dei flussi `FileInputStream` e `FileOutputStream`.
* **Caratteristica**: Trasferimento dati tramite buffer di 1024 byte per garantire stabilità.

### STEP #2: Menu Interattivo & Multi-Thread
Introduzione della logica di scelta e della gestione parallela.
* **Focus**: Interazione utente e scalabilità.
* **Caratteristica**: Il server utilizza i `Thread` per gestire più client. Viene implementato un menu testuale che permette al client di scegliere tra diverse risorse (es. "IlFra" o "IlBro").

### STEP #3: Multi-Thread Server Ottimizzato (Versione Finale)
La versione definitiva, pulita e focalizzata sulle performance di rete.
* **Focus**: Efficienza e robustezza.
* **Caratteristica**: Architettura a thread separati (`ServerThread`) che isola completamente ogni sessione di download. Ottimizzazione della chiusura degli stream per evitare memory leak.



---

## Tecnologie e Competenze
* **Networking**: Utilizzo avanzato di `ServerSocket` e `Socket` (TCP/IP).
* **Multithreading**: Implementazione del pattern *Thread-per-Client* per gestire connessioni simultanee.
* **Binary I/O**: Manipolazione di file binari tramite `ObjectOutputStream` e buffer di byte.
* **Error Handling**: Gestione delle eccezioni di rete e validazione dei dati.

## Struttura del Progetto
Il server si aspetta di trovare i file da inviare nella cartella:
`src/main/resources/in/`

Il client salverà i file ricevuti nella cartella:
`src/main/resources/out/`

## Come utilizzarlo
1.  Assicurarsi di avere i file `.png` nelle cartelle sorgente.
2.  Avviare `ServerMain`.
3.  Avviare uno o più `ClientMain`.
4.  Monitorare il log della console per confermare l'avvenuto trasferimento.

---
*Progetto realizzato per approfondire l'architettura dei sistemi distribuiti e il trasferimento dati concorrente in Java.*
