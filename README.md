# Progetti di domotica con Raspberry Pi

Un laboratorio domestico per imparare la domotica costruendo progetti piccoli, documentati e facili da ampliare. L'obiettivo iniziale e' usare il Raspberry Pi 5 come centro del sistema e un ESP32 per leggere sensori e controllare dispositivi a bassa tensione.

## Direzione consigliata

- **Raspberry Pi 5:** Home Assistant OS, installato su un SSD, per gestire dispositivi, automazioni e dashboard.
- **ESP32:** ESPHome per iniziare a collegare sensori e integrarli in Home Assistant senza scrivere subito firmware da zero.
- **Python:** prossimo linguaggio da imparare per script, API e integrazioni personalizzate.
- **PHP e MySQL:** competenze gia' utili per eventuali siti o servizi personali; non servono per avviare Home Assistant.
- **MQTT e Mosquitto:** da aggiungere quando sara' utile far comunicare servizi o dispositivi in modo disaccoppiato.
- **C++ con Arduino IDE o PlatformIO:** per approfondire il firmware dei microcontrollori.
- **Rust:** possibile esperimento futuro, non necessario per i primi risultati.

Home Assistant OS e' la scelta piu' semplice se il Raspberry deve essere soprattutto il centro domotico. Docker Compose su Raspberry Pi OS e' una valida alternativa se si vuole anche amministrare un piccolo server Linux; comporta pero' piu' manutenzione e Home Assistant Container non include Supervisor e il catalogo degli add-on.

## Roadmap

1. Preparare il Raspberry Pi 5 con alimentazione adeguata, raffreddamento e SSD; installare Home Assistant OS e configurare i backup.
2. Aggiungere un ESP32 e un sensore ambientale, per esempio un BME280, usando ESPHome.
3. Visualizzare le misure in Home Assistant e creare una prima automazione, come una notifica al superamento di una soglia.
4. Aggiungere altri sensori o un attuatore a bassa tensione.
5. Provare MQTT, poi realizzare un piccolo servizio Python o una pagina PHP se serve una funzione personalizzata.

### Primo progetto: sensore ambientale

**Risultato atteso:** temperatura, umidita' e pressione visibili in Home Assistant, lette da un BME280 collegato a un ESP32 con ESPHome.

**Materiale iniziale:** Raspberry Pi 5 con SSD e alimentatore adeguato, scheda ESP32, modulo BME280, cavetti e breadboard. Verificare il pinout e la tensione supportata dal modulo specifico prima di collegarlo.

**Completato quando:** il sensore compare in Home Assistant, i valori si aggiornano e il progetto include schema dei collegamenti e istruzioni per ripeterlo.

## Container e database

Non servono container per il primo progetto. Se in seguito si sceglie Raspberry Pi OS, Docker Compose puo' ospitare Home Assistant Container e servizi aggiuntivi come Mosquitto o una propria applicazione. Conviene aggiungerli uno alla volta e documentare aggiornamenti e backup.

Home Assistant usa il proprio database per la cronologia: non occorre installare MySQL per iniziare. Un database separato ha senso solo quando un progetto personale ne ha davvero bisogno.

## Sicurezza e manutenzione

- Fare backup prima di aggiornamenti importanti e conservarne una copia fuori dal Raspberry.
- Non esporre Home Assistant direttamente a Internet senza una soluzione di accesso remoto configurata e protetta.
- Non inserire password Wi-Fi, token, credenziali o altri segreti nel repository; usare file locali esclusi dal controllo versione.
- Iniziare con sensori e circuiti a bassa tensione. Non collegare la rete elettrica a una breadboard o a un ESP32; per carichi di rete usare dispositivi certificati e installazione adeguata.

## Come documentare i progetti

Per ogni progetto aggiungere una cartella con un README che descriva:

- obiettivo e componenti;
- schema dei collegamenti e tensioni;
- installazione e configurazione;
- risultato atteso e prove effettuate;
- problemi incontrati e possibili miglioramenti.