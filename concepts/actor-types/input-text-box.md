---
title: "Interazione | Casella di input "
parent: "Elenco attori"
grand_parent: Concetti
---

{% include links_actor.md apiClass="Actor.Input.TextBox" %}

# Casella di input

L'attore casella di input consente di creare campi di input personalizzabili.

{% include table_of_content.html %}

# Proprietà specifiche

A seconda del tipo selezionato, il campo `Tipo di input' dell'attore Casella di input ne determina il comportamento. 

**Dimensione**

{% include property_size.md %}

**Lunghezza massima**

Consente di limitare la dimensione della stringa `Valore`.

>📌 *NOTA*<br>
>Il carattere "spazio" viene contabilizzato come un qualsiasi altro carattere.

**Modalità di input**

Si utilizza questo campo per determinare il tipo di tastiera visualizzata sui dispositivi mobili e sui tablet.

**Completamento automatico?**

Consente di attivare/disattivare il completamento automatico sui browser.

Questo campo non è richiesto per i seguenti `Tipi di input`: Password / Cursore / Colore.

**Sola lettura?**

Abilita/disabilita l'inserimento di valori nel campo.

Questo campo non è richiesto per i seguenti "tipi di input": Cursore / Colore.

**Stato della convalida**

Permette di attribuire al campo di immissione una formattazione predefinita.

**Attivo?**

Attiva/disattiva il campo di immissione.

## Tipo di input

**TESTO / PASSWORD

*Valore*

La proprietà specifica `Valore` consente di definire il contenuto corrente dell'attore.

- Per `TESTO' il valore atteso è una stringa.

- Per `PASSWORD` il valore previsto è una stringa e non verrà visualizzato in chiaro nel campo di immissione.

*Texte si vide*

La proprietà specifica `Testo se vuoto` consente di definire il testo da visualizzare quando il campo di input dell'attore è vuoto.
Il valore atteso è una stringa.

*Opzioni*

- Solo per  `TESTO`

Permette di suggerire all'utente come complare il campo, quando il cursore viene posizionato nel campo di immissione.

Per suggerire gli elementi, è necessario seguire la sintassi riportata di seguito:

```["Un Testo","un'altro testo","un esempio"]```

**NUMERO**

*Valore*

La proprietà specifica `Value` è utilizzata per definire il contenuto corrente dell'attore.

Il valore atteso è un numero.

*Testo se vuoto*

La proprietà specifica `Testo se vuoto` consente di definire il testo da visualizzare quando il campo di input dell'attore è vuoto.

Il valore richiesto è una stringa.

*Valore minimo*

Limita il valore che il `Numero` può assumere, attribuendogli un limite inferiore.

*Valore massimo*

Limita il valore che il `Numero` può assumere, attribuendogli un limite superiore.

*Passo tra due valori*

Interviene sulla regola di incremento/decremento del `Valore`.

*Options*
Permette di suggerire all'utente come complare il campo, quando il cursore viene posizionato nel campo di immissione. Tuttavia, il valore suggerito deve essere coerente con il valore previsto nel campo `Valore`.

Per suggerire gli elementi, è necessario seguire la sintassi riportata di seguito:

```["45","5000","1337"]```

**CURSORE**

*Valore minimo*

Condiziona il valore che il `Cursore` deve assumere, dandogli un limite inferiore.

*Valore massimo*

Condiziona il valore che il `Cursore` deve assumere, dandogli un limite superiore.

*Passo tra due valori*

Condiziona il passo del `Cursore`.

**DATA**

*Valeur Min*

Conditionne la valeur que doit prendre la `Date` en lui attribuant une borne négative.

Dall'ispettore è possibile aprire la guida alla selezione della data.

*Valore massimo*

Condiziona il valore che la `Data` dovrebbe assumere, dandogli un limite superiore.

Dall'ispettore è possibile aprire la guida alla selezione della data.


**ORA**

*Valore minimo*

Condiziona il valore che deve assumere la variabile `ORA' dandole un limite inferiore.

Dall'ispettore è possibile aprire la guida alla selezione degli orari.

*Valore massimo*

Condiziona il valore che il `Ora' deve assumere, dandogli un limite superiore.

Dall'ispettore è possibile aprire la guida alla selezione degli orari.


**COLORE**

*Valore*

La proprietà specifica `Vallore` è utilizzata per definire il colore dell'attore

Il valore atteso è un codice esadecimale.

Uno strumento per recuperare i codici colore esadecimali è disponibile [a questo indirizzo](https://htmlcolorcodes.com).

Per scegliere un colore è anche possibile fare clic sul pulsante dell'interfaccia.
