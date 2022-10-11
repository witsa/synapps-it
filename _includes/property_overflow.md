Le proprietà *Superamento vericale* e *Superamento orizzontale* sono utilizzate per gestire il comportamento dell'attore rispetto a un possibile debordamento del suo contenuto.

Se l'attore ha una dimensione fissa *O* è vincolato da un altro elemento (ad esempio, l'attore genitore), è possibile applicare le proprietà *Superamento orizzontale* e *Superamento verticale*.

Per ciascuna di queste proprietà sono disponibili quattro opzioni:
- **Nascosto**

Il contenuto che non ha spazio sufficiente per essere visualizzato non sarà visibile e i suoi elementi non saranno accessibili.

- **Visibile**

Il contenuto che non ha spazio sufficiente viene visualizzato al di fuori dello spazio previsto per l'attore..

Si noti che se un altro attore si sovrappone a questo sconfinamento, la parte che eccede sarà nascosta da quell'attore.

> Si noti che entrambe le proprietà devono essere `Visibili` per ottenere il comportamento desiderato.

- **Scorrimento**

Permette di aggiungere una *barra di scorrimento* all'attore, che fornisce un mezzo per accedere al contenuto visualizzato.

- **Automatico**

Visualizza una *barra di scorrimento* solo se c'è un superamento.

> ⚠️ **ATTENZIONE**<br>
> Le opzioni `Visibile` e `Nascosto` non sono compatibili tra loro.
