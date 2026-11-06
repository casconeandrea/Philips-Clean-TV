# Philips Clean TV

Pulizia del televisore **Philips 55PUS7956/12** (Android TV 11, scheda PH0M_EA_T32): disattiva
telemetria, promo e app inutili per renderlo più leggero, senza root e senza cancellare niente.

Basato su [CleanYourTV](https://github.com/Gathin23/cleanyourtv) di Gathin (licenza MIT): da lì
vengono gli strumenti in `tools/` e la lista di partenza. Il fork completo è in
[casconeandrea/cleanyourtv](https://github.com/casconeandrea/cleanyourtv/tree/philips-55pus7956).

## Cosa resta intatto

- Ambilight
- Screensaver automatico di Google
- Chromecast e trasmissione dal telefono
- Icone Sorgenti e Wi-Fi nella Home
- Netflix, Prime Video, HBO Max, Crunchyroll, YouTube, RaiPlay, Witty TV
- Google Play Store e aggiornamenti del televisore

La lista completa, con il motivo di ogni voce, è in
[`examples/philips-55pus7956/debloat.txt`](examples/philips-55pus7956/debloat.txt).

## Come si usa (Windows)

Serve un PC Windows sulla stessa rete del televisore e Python 3 installato
(da [python.org](https://www.python.org/downloads/), spuntando "Add python.exe to PATH").
Scarica questo repository con **Code → Download ZIP**, estrailo e avvia i file con un doppio clic:

1. Sul televisore: Impostazioni → Preferenze dispositivo → Info, premi OK sette volte su **Build**;
   poi in **Opzioni sviluppatore** attiva il **Debug USB**. Annota l'IP del televisore.
2. `1_PREPARA.bat` — installa ciò che serve e salva l'IP.
3. `2_VERIFICA.bat` — deve mostrare `PH0M_EA_T32` e `11`. Sul televisore premi "Consenti sempre".
   Se i valori sono diversi, fermati.
4. `3_APPLICA.bat` — applica la lista dopo che scrivi SI.
5. `4_CONTROLLA_HOME.bat` — riavvia la Home. Controlla icone, HDMI, canali, Ambilight, app e cast.
6. Sul televisore: **Revoca autorizzazioni debug USB**, spegni il **Debug USB**, riavvia.
7. `5_CHIUDI_ACCESSO.bat` — verifica che l'accesso al televisore sia chiuso.

## Tornare indietro

Riattiva il Debug USB e avvia `RIPRISTINA.bat`, poi richiudi come ai passi 6 e 7.

Lo stato originale del televisore viene salvato in `C:\Users\<nome utente>\.cleanyourtv\` ed è
legato al percorso della cartella: per un ripristino preciso usa lo stesso PC e la stessa cartella.
Altrove il ripristino funziona comunque, ma riattiva tutte le app della lista.
Senza PC si possono riattivare le singole app da Impostazioni → App → mostra app di sistema.

## Dopo

- Un aggiornamento firmware può riattivare alcune app: ripeti i passi 1, 4, 6 e 7.
- Righe dei consigli e anteprime video si spengono dal telecomando in
  Impostazioni → Preferenze dispositivo → Schermata Home → Personalizza canali.
- Dopo un riavvio completo il televisore si apre sulla TV in diretta: è il firmware, non un errore.

Nessuna garanzia: usalo a tuo rischio, come indicato nella [licenza](LICENSE).
