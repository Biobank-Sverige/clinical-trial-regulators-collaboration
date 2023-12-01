Interna beroenden
=================


message.json beskriver innehållet i det som skickas med ett paket. Det innehåller dels information om ärendet som berörs med en del strukturerad information och som används för att uppdatera information om vad som hänt i ärendet och dels innehåller den beskrivning av bifogade handlingar.

Det är samma format på message.json för alla typer av meddelanden vilket innebär att det uppstår en mängd underförstådda relationer mellan element i message.json. För att säkerställa att vi har en gemensam bild av vilka dessa är dokumenteras sådana i denna fil.


Relationen Notis: Ny ansökan och elementet CaseType
---------------------------------------------------

Det finns fyra typer av notiser om nya ärenden och där valet av notis indikerar vilken typ av ärende som det handlar om. Samtidigt finns information om ärendets typ i elementet casetype. Det är en form av redundans som skapar ett behov av regler.

Notis                                             Notis: Initial ansökan del I     Notis: Initial ansökan del II     Notis: Initial ansökan del I & II     Notis: Ändringsansökan 
-----                                             ----------------------------     -----------------------------     ---------------------------------     ----------------------

KP-ansökan, multinationell, initialt del I                   OK                                 -                                   -                                 - 
KP-ansökan, multinationell, initialt komplett                 -                                 -                                   OK                                - 
KP-ansökan, mononationell, initialt del I                    OK                                 -                                   -                                 - 
KP-ansökan, mononationell, initialt komplett                  -                                 -                                   OK                                - 
KP-ansökan, Tillägg av SE som MSC                             ?                                 ?                                   ?                                 ?
Ändring, multinationell, del I                                -                                 -                                   -                                 OK
Ändring, multinationell, del I och del II                     -                                 -                                   -                                 OK
Ändring, mononationell, del I                                 -                                 -                                   -                                 OK
Ändring, mononationell, del I och del II                      -                                 -                                   -                                 OK
Ändring, nationell, del II                                    -                                 -                                   -                                 -


I övrigt gäller för CaseType att den sätts av den första notisen om ärendet. För alla efterföljande meddelanden som har samma LV-DiaryNumber antas CaseType vara exakt samma som i den första notisen.

