2025-01-06 10:36

Tags : [[Crittografia]]

# DES (Data Encryption Standard)

Il capostipite dei moderni algoritmi di cifratura a chiavi simmetrica è il **DES**, creato nel 1976 dagli Stati Uniti. 

Claude Shannon, ingegnere e matematico statunitense, mostrò che per ottenere il risultato sperato (*garantire la sicurezza del messaggio*), serve che l'algoritmo di cifratura abbia almeno due caratteristiche : 

1. **Confusion** (*confusione*) : renda confusa la relazione tra i caratteri del testo in chiaro e quelli del testo cifrato, tipicamente tramite la sostituzione dei caratteri in chiaro con caratteri diversi.
2. **Diffusion** (*diffusione*) : alteri la struttura del testo in chiaro spargendo i caratteri su tutto il testo cifrato, tipicamente permutando (*trasponendo*) i caratteri del testo in chiaro.

L'Idea quindi alla base del DES è di ripetere molte volte una serie di operazioni di confusione e diffusione.

## Funzionamento 

In input all'algoritmo viene dato :
- il testo in chiaro suddiviso in blocchi di dimensione fissa pari a 64 bit.
- chiave a 56 bit.

Successivamente alla divisione del testo, l'algoritmo esegue i seguenti passaggi : 
1. **Divisione** del blocco iniziale, due blocchi da 32 bit.
2. **Permutazione** iniziale dei blocchi (*le posizioni dei blocchi vengono invertite*)
3. **Generazione di 16 chiavi**, partendo da un'unica chiave a 56 bit. La chiave infatti viene rimescolata e compressa per ottenere una chiave a 48 bit. **Ciascuna chiave sarà utilizzata per ogni round.**
4. Il blocco di destra diventerà sia **il nuovo blocco di sinistra** sia l'input della **funzione di Feistel**. A questa funzione è assegnato il compiti di combinare i 32 bit del blocco con i 48 della chiave.
	1. La funzione prima di tutto espande il blocco di 32 bit, facendolo arrivare alle stesse dimensioni della chiave (*48 bit*), questo è possibile semplicemente ripetendo alcuni bit del blocco.
	2. Sul nuovo blocco viene effettuato lo XOR con la chiave a 48 bit.
	3. Il nuovo testo di 48 bit viene suddiviso in 8 blocchi dai bit.
	4. Ogni blocco entra in un S-BOX
	5. S-BOX comprime ogni blocco da 6 in 4 bit
	6. Tutte e 8 le S-BOX eseguono la stessa operazione sugli 8 blocchi di bit, facendo ritornare il blocco 32 bit.
5. Il nuovo blocco uscito dalla funzione di feistel, viene messo a XOR con il blocco di sinistra. In questo modo si va a creare il **nuovo blocco di destra**.
6. Tali operazioni (*punti 4-5*), **vengono ripetute per 16 volte**.
7. **Permutazione finale**, inversa da quella iniziale utilizzando un altra matrice di permutazione.
8. **Inverte le posizioni dei blocchi** al fine di predisporre il blocco cifrato alla sua decifratura.

Utilizzando le chiavi nell'ordine inverso, possiamo risalire al messaggio originale.

## References

- [[Crittografia a chiave simmetrica]]
- [[Evoluzione del  DES (3DES, AES)]]