# Firmware per Flyingbear ghost 5 con sensore di livellamento e driver 2226 (o 2209) in modalitàù UART con sensorless homing attivo
Questo firmware è basato sulla versione 2.0.8 di makerbase, basata a sua volta sulla versione 2.0.8 di Marlin.

1. Come buildare (da VSC):
- Aprire il plugin platformIO e selezionare il task `mks_robin_nano_v3_usb_flash_drive`, quindi eseguire il `Clean All` e infine il `Build`;

2. Come aggiornare:
- Copiare la cartella `assets` e il file `Robin_nano_v3.bin`, contenuti nel percorso `.pio\build\mks_robin_nano35`, all'interno di una scheda SD o di una chiavetta USB;
- Inserire la scheda SD o la chiavetta USB nell'apposito slot e riavviare la scheda madre;
- Al termine del flash riavviare nuovamente la stampante, aprire il menù, fare il reset dell'eeprom e infine memorizzare l'eeprom resettata;

3. Come predisporre l'hardware:
- Scollegare i connettori degli endstop dalla scheda madre e, almeno quello dell'asse `Y`, dal telaio;
- Montare un connettore sui due fili della ventolina dell'hotend e collegare quest'ultima al connettore `Fan2` della scheda madre;
- Impostare la modalità UART per i driver ponticellando, sotto ciascuno di essi, i due pin verdi corrispondendi a `M2`;
- Impostare la modalità Sensorless homing ponticellando, dove è scritto `DIAG`, i pin degli assi `X`, `Y`, `Z-` ed `E1`;
- Impostare la tensione dei driver su `3.3V`, ponticellando i due pin a sinistrta del `Drive IC Power`;
- Collegare i fili bianco e nero del sensore di livellamento sul connettore `Z-`;
- Collegare i tre fili rimanenti nel connettore `Bltouch` sulla scheda madre;