# VoiceBox-ITA
voiceBox leggermente modificato al fine di produrre sintesi vocali in italiano.

<< VoiceBox - a package of scripts _mainly_ by Brian Wolven, but with help from
	    Jens Arnold and Joerg. Brian is the one responsible for any
	    mistakes. =) >>
      
VoiceBox è un programma opensource, sviluppato da Brian Wolven, Jens Arnold e Joerg.
VoiceBox generara automaticamente file audio al fine di rendere accessibile RockBox anche ad utenti non vedenti o a chi,
per qualsivoglia necessità, ha bisogno di utilizzare il proprio dispositivo RockBox con l'ausilio di un sintetizzatore vocale.


# ISTRUZIONI:

1. Installare la lingua italiana per il sintetizzatore (file: "MSSpeech_SR_it-IT_TELE.msi")

2. Entrare nella cartella "voiceBox" ed eseguire "voiceBox.hta"

3. Spuntare le seguenti opzioni:
  Speex format (all others)
  Overwrite existing .wav files? (Recommended)
  Remove .wav files after processing? (Recommended)
  Voice folders? (Recommended)
  Voice individual files? (User preference)
  
4. Clicca sul pulsante "Browse" e seleziona l'intera cartella contenente tutta la libreria musicale da inserire nel device.

5. Clicca su "Run VoiceBox" ed attendi che il processo finisca (terminerà con un messaggio di errore, è normale)

6. Chiudi il programma e sposta la cartella contenente la tua libreria musicale all'interno del device.






P.S.
  Ricorda di abilitare la lettura dei file e delle cartelle nelle impostazioni di rockBox! 
  Solitamente queste opzioni si trovano in: SETTINGS -> GENERAL SETTINGS -> VOICE
  
  le impostazioni corrette sono le seguenti:
    
    talk dir: spell
    talk dir clip: on
    talk file: spell
    talk file clip: on
    Announce Battery Level: on
