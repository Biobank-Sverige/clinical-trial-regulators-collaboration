Meddelandehantering Läkemedelsverket - Biobank Sverige
======================================================

Terminologi
-----------

Meddelande:

Paket av information skickat vid en tidpunkt

Ansökan:

En ansökan är samma sak som *case* och defineras av alla meddelanden med samma diarienummer hos Läkemedelsverket.
En ansökan har en orsak (*caseType*) som defineras vid första meddelandet.

Bedömning:

En bedömning är samma sak som *asessment* och görs inom ramen för en ansökan. Kan innehålla
del I, del II eller del I och II.

Meddelandetyper
---------------

Kommunikationen bygger på fasta meddelandetyper som defineras av *messageReasonType* och *caseType*

Följande kombinationer av dessa accepteras när LV skickar meddelanden till BBS:

- Notis: Initial ansökan del I
    - KP-ansökan, multinationell, initialt del I
    - KP-ansökan, mononationell, initialt del I
    - KP-ansökan, Tillägg av SE som MSC
- Notis: Initial ansökan del I och II
    - KP-ansökan, multinationell, initialt komplett
    - KP-ansökan, mononationell, initialt komplett
    - KP-ansökan, Tillägg av SE som MSC
- Notis: Ändringsansökan
    - Ändring, multinationell, del I
    - Ändring, multinationell, del I och del II
    - Ändring, mononationell, del I
    - Ändring, mononationell, del I och del II
    - Ändring, nationell, del II
    - KP-ansökan, Tillägg av SE som MSC
- Notis: Beslut för överflyttad prövning
    - KP-ansökan, multinationell, transitional
- Notis: Initial ansökan del II
    - Samma som första meddelandet i ansökan
- Notis: Valid ansökan
    - Samma som första meddelandet i ansökan
- Notis: Validerings-RFI till sponsor
    - Samma som första meddelandet i ansökan
- Begäran: Preliminär granskning del I
    - Samma som första meddelandet i ansökan
- Begäran: Preliminär granskning del II
    - Samma som första meddelandet i ansökan
- Notis: Bedömnings-RFI del I till sponsor
    - Samma som första meddelandet i ansökan
- Notis: Bedömnings-RFI del II till sponsor
    - Samma som första meddelandet i ansökan
- Notis: Komplettering från sponsor del I
    - Samma som första meddelandet i ansökan
- Notis: Komplettering från sponsor del II
    - Samma som första meddelandet i ansökan
- Notis: AR och slutsats del I
    - Samma som första meddelandet i ansökan
- Notis: AR och slutsats del II
    - Samma som första meddelandet i ansökan
- Notis: Ansökan dragits tillbaka
    - Samma som första meddelandet i ansökan
- Notis: Ansökan förfallen
    - Samma som första meddelandet i ansökan
- Notis: Ansökan tyst godkännande
    - Samma som första meddelandet i ansökan
- Notis: Beslut för ansökan
    - Samma som första meddelandet i ansökan
- Notis: Informell RFI
    - Samma som första meddelandet i ansökan

Följande kombinationer av dessa accepteras när BBS skickar meddelanden till LV:

Dokumettyper
------------

Följande dokumenttyper accepteras när LV skickar meddelanden till BBS:

- SAMVERK_1 (Meddelandemetadata samarbetspartner)
- SAMVERK_2 (Strukturerad data från ansökan)
- SAMVERK_10 (RFI/RFI-svar)
- 2 (Följebrev (ej för publicering))
- 5 (Protokoll (ej för publicering))
- 7 (Sammanfattning av protokoll (för publicering))
- 14 (Rekryteringsförfarande (för publicering))
- 15 (Försökspersonsinformation och informerat samtycke (för publicering))
- 41 (Final utredningsrapport del II (ej för publicering))
- 42 (Final utredningsrapport del II (för publicering))
- 49 (Följebrev (för publicering))
- 52 (Ändringsbeskrivning (för publicering)) *Denna ska diskuteras*
- 104 (Protokoll (för publicering))
- 251 (Lista över ändringar (för publicering))
- 273 (Part I assessment report quality - Final) *Vad heter denna på svenska?*
- 274 (Final utredningsrapport del I exklusive kvalitet (för publicering)) *Denna ska diskuteras*
- 278 (Följsamhet med regler för användning av biologiska prover (för publicering))
- 308 (Sammanfattning av protokoll (ej för publicering))
- 322 (Rekryteringsförfarande (ej för publicering))
- 323 (Försökspersonsinformation och informerat samtycke (ej för publicering))
- 324 (Ändringsbeskrivning (ej för publicering)) *Denna ska diskuteras*
- 328 (Följsamhet med regler för användning av biologiska prover (ej för publicering))
- 366 (Final utredningsrapport del I exklusive kvalitet (ej för publicering))
- 373 (Lista över ändringar (ej för publicering))
- 9001 (Beslutshandling)

- 371 (Bilaga till synpunkt (ej för publicering))
- 279 (Bilaga till synpunkt (för publicering))
- 370 (Bilaga(id370))
- 215 (Bilaga (för publicering) (id215))

Meddelanden som innehåller dokument av typ som inte är listad ovan kommer att betraktas som felaktiga (alltså inte tas emot och generera ett felmeddelande)


Processbeskrivning
------------------

För detaljer kring vad som utgör ett korrekt meddelande, se [verifications](rbc/verifications.md).

### Livscykel studie

Som första meddelande för en ny studie från LV till BBS accepteras:

- Notis: Initial ansökan del I
    - KP-ansökan, multinationell, initialt del I
    - KP-ansökan, mononationell, initialt del I
    - KP-ansökan, Tillägg av SE som MSC
- Notis: Initial ansökan del I och II
    - KP-ansökan, multinationell, initialt komplett
    - KP-ansökan, mononationell, initialt komplett
    - KP-ansökan, Tillägg av SE som MSC
- Notis: Beslut för överflyttad prövning
    - KP-ansökan, multinationell, transitional
- Notis: Ansökan tyst godkännande
    - KP-ansökan, multinationell, initialt del I
    - KP-ansökan, multinationell, initialt komplett
    - KP-ansökan, mononationell, initialt del I
    - KP-ansökan, mononationell, initialt komplett
    - KP-ansökan, Tillägg av SE som MSC
    - Ändring, multinationell, del I
    - Ändring, multinationell, del I och del II
    - Ändring, mononationell, del I
    - Ändring, monongodkännandeationell, del I och del II
    - Ändring, nationell, del II

När ett sådant meddelande är mottaget startas en studie och en ansökan (*case*) och en eller två bedömning(ar) (
*asessment(s)*)

En studie kan inte avslutas.

### Livscykel ansökan

Ansökan skapas i samband med att studien startar (se ovan).

En ansökan kan också skapas med

- Notis: Ändringsansökan
    - Ändring, multinationell, del I
    - Ändring, multinationell, del I och del II
    - Ändring, mononationell, del I
    - Ändring, mononationell, del I och del II
    - KP-ansökan, Tillägg av SE som MSC

Detta förutsätter att det inte finns någon pågående ansökan för studien.

En ansökan kan innehålla noll eller en bedömning del I och noll eller en bedömning del II.

När ett sådant meddelande är mottaget startas en (ändrings)ansökan (*case*) och en eller två bedömning (ar) (
*assessment(s)*)

Ansökan avslutas med något av:

- Notis: Ansökan dragits tillbaka
- Notis: Ansökan förfallen
- Notis: Ansökan tyst godkännande
- Notis: Beslut för ansökan

### Livscykel bedömning del I

Bedömning del I startar alltid i samband med

- Notis: Initial ansökan del I
- Notis: Initial ansökan del I och II
- Notis: Ändringsansökan
    - Ändring, multinationell, del I
    - Ändring, multinationell, del I och del II
    - Ändring, mononationell, del I
    - Ändring, mononationell, del I och del II
    - KP-ansökan, Tillägg av SE som MSC

Bedömning del I avslutas vid meddelande:

- Notis: AR och slutsats del I
- Notis: Beslut för ansökan *Ska detta vara tillåtet?*
- Notis: Ansökan dragits tillbaka *Ska detta vara tillåtet?*
- Notis: Ansökan förfallen *Ska detta vara tillåtet?*
- Notis: Ansökan tyst godkännande *Ska detta vara tillåtet?*

Övriga meddelanden rörande en bedömning kan bara tas emot när ansökan är aktiv (startad men inte avslutad)

Dessa är:

- Notis: Valid ansökan
- Notis: Validerings-RFI till sponsor
- Begäran: Preliminär granskning del I
- Notis: Bedömnings-RFI del I till sponsor
- Notis: Komplettering från sponsor del I
- Notis: Informell RFI

### Livscykel bedömning del II

Bedömning del II startar alltid i samband med

- Notis: Initial ansökan del II
- Notis: Initial ansökan del I och II
- Notis: Ändringsansökan
    - Ändring, multinationell, del I och del II
    - Ändring, mononationell, del I och del II
    - Ändring, nationell, del II
    - KP-ansökan, Tillägg av SE som MSC

Bedömning del II avslutas vid meddelande:

- Notis: AR och slutsats del II
- Notis: Beslut för ansökan *Ska detta vara tillåtet?*
- Notis: Ansökan dragits tillbaka *Ska detta vara tillåtet?*
- Notis: Ansökan förfallen *Ska detta vara tillåtet?*
- Notis: Ansökan tyst godkännande *Ska detta vara tillåtet?*

Övriga meddelanden rörande en bedömning kan bara tas emot när ansökan är aktiv (startad men inte avslutad)

Dessa är:

- Notis: Valid ansökan
- Notis: Validerings-RFI till sponsor
- Begäran: Preliminär granskning del II
- Notis: Bedömnings-RFI del II till sponsor
- Notis: Komplettering från sponsor del II
- Notis: Informell RFI
