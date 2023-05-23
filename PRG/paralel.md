# Paralelní programování

`Asynchronní a paralelní programování`

## Asynchronní programování

- asynchronní volání neblokují chod volajícího
- cílem je responzivita aplikace

## Paralelní programování

- cílem je výkon aplikace
- velké množství navzájem nezávislých dat

## Vlákno

- běží v něm aplikace (proces)
- aplikace může běžet v několika vláknech (→ vícevláknová aplikace)
- synchronizace:
  - přístup ke sdíleným prostředkům
  - při zpracovávání dat vláknem by ostatní neměly mít přístup
    - zámek (lock)

### Lock

- zámek
- má ho jakýkoli objekt
- tímto objektem se daná část kódu zamkne
- zamknutá část se vždy musí dokončit, pokud se začne vykonávat

## C#

### Thread

- vlákno
- v C# jde o třídu
- nízkoúrovňové řízení
- vytvoření instance této třídy vytvoří nové vlákno v procesoru
- lze s ní pracovat (metody Sleep(), Join(), Start(), Abort())

### Task

- vysokoúrovňové řízení
- asyncronní úloha
- v C# jde o třídu
- vytvoření instance této třídy vytvoří novou úlohu

### Async

- klíčová slova v C# která umožňují vytváření asynchronních funkcí
- **async** určuje metodu jako asynchronní
- aby byla metoda asynchronní, musí zároveň v jejím těle obsahovat **await**
  - při použití **await** se vyčká na dokončení metody

### Parallel.For

- paralelní průchody cyklem
