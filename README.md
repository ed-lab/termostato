GREENSTATO
==========

Gestione termostato con sonda analogica con uscita in potenza protetta con fotoaccopiatore per prevenire e combattere gli sprechi dovuti all'inerzia dell'innesco di caldaie nelle mezze stagioni laddove l'accumulo di acqua calda uso termosanitario non sia ottimizato.

LO SCOPO:

Misura di una temperaura. Da questo si imposta una soglia con i pulsanti. La si memorizza. In questo modo anche dopo un black-out la e2prom del sistema restituisce l'ultima impostazione.
Da qui inavanti il relè fornisce l'oppurtuna commutazione, che va a pilotare una caldaia.

THE GREEN VALUE:

Quello che si può fare in più rispetto a uncomune termostato è dovuto alla potenza del software:
Impostare un delay di intervento. 
Può sembrare una banalità.. ma cò non è.
Immaginiamo di avere un volume da scaldare nelle mezze stagioni. E di avere un riscaldamento autonomo.
Gli accumulatori (bollitori) saranno logicamente caricati di energia di solare termico ma ancora molto da energia a pagamento (ovvero en.el/gpl/metano/kerosene etc.).
E' evidente che per raggiungere la temperatura di esercizio (55..60°C) il termostato è spsso in funzione, anche solo per scaldare centinaia di LT di acqua per poche decine di minuti. Solo per mantenerla perfettamente a 60°C.

Nell'ottica di ragionare per consumare meno, ma anche di buon senso, va da se che non è assolutamente necessario garantire una T esatta sui bollitori quando nelle mezze stagioni è sufficiente avere Delta termici più ampi, senza dover far lavorare costantemente la caldaia.
Ma ovviamente manca un sistema che sia in grado di creare questo ritardo che si traduce in una serie di cicli di lavoro in meno.


TECNICO:

Il progetto seguente non è la scoperta dell'acqua calda. 
Ma nemmeno un deja-vu poichè fonde in un unica soluzione l'idea di usare un sistema intelligente (PIC o ARDUINO in questo caso) con un interfaccia molto semplice ovvero un display e 4 bottoni per pilotare un uscita relè.

La particolarità (visto che lo schema è semplice) sta nel fatto che l'uscita di Arduino non va direttamente sul relè ma poichè il contatto del termostato agisce direttamente sulla tensione 220VAC preferiamo proteggere il cervellone da possibili e indesiderati spike o comunque separare fisicamente la logica dall'utilizatore.

Per far questo possiamo semplicemente usare un relè 5V sull'uscta dell'Arduino. 
O pilotare con quell'uscita un transistor, per switchare un carico più esigente (lampadine, relè etc..) 
O pilotare un darlington (max 100V nel ns caso in DC) per un carico (motore in DC o luci)

In questo progetto l'uscita dell'Arduino esce OPTOisolata, pilota un Darlington e infine un relè.

La decisione di avere una tale configurazione è dettata dal voler offrire un sistema scalabile.


