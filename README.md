Cerinta proiectului :
Se dorește proiectarea unui automat de tip Mealy pentru băuturi răcoritoare. 
Pentru a simplifica problem, se consideră că se poate elibera un singur tip de băutură răcoritoare.
Aceasta costă 3 lei și se eliberează automat în momentul în care s-au acumulat bani în sumă egală sau mai mare decât prețul prudusului. 
Automatul acceptă bancnote de 1, 5 , respectiv 10 lei și eliberează automat rest de 1 sau 5 lei dacă s-a introdus o sumă mai mare decât prețul băuturii. 
Se presupune că există un mecanism pentru sortarea banilor și care emite trei semnale, câte unul pentru fiecare tip de bancnotă. 
Semnalele determină tranziția automatului dintr-o stare în alta. 
În orice stare când se stă nu se dau ieșiri iar în prima stare se ajunge cu semnalul de Reset de tipul ales de către voi. 
Pe o tranziție se pot da cel mult 2 ieșiri, eliberare un produs și sau eliberare un tip de rest.
Întotdeauna se încearcă eliberarea restului cel mai mare.


Components :

##### -Decodificator
##### -Calculator

##### -Registru 

##### -Frequency Divider

##### -ALU (Sequential unit)

##### -D Flip Flop

#### 4.1 Functionare interna

 Inputul de bancnote este prelucrat de decodificator care trimite in binar catre calculator informatia pentru a se aduna la credit sau a fi respinsa. 
 Pe perioada de acumulare se pot elibera oricat de multe bauturi , fiecare bautura modificand creditul cu pretul ei respectiv.
 La momentul introducerii bancnotelor , o bancnota acceptata va fi adaugat in memorie de bani ce pot fi folositi in eliberare rest. 
 In momentul in care se cere rest calculatorul trimite suma care trebuie sa restituita catre ALU . 
 Divizorul de frecventa si bistabilul functioneaza ca sincronizare intre calculator si ALU pentru situatia de comisionare de 1 leu pt. o suma >= 10 lei.
 O data ce ALU a primit comanda de eliberare rest , acesta intra intr-un proces secvential in care trimite repetat un semnal ( REQUEST) catre registru ,
 in care "cere" bancnote care vor fi trimise catre output. O data ce procesul de eliberare rest s-a incheiat , ALU trimite un semnal de reset catre calculator , 
 acesta resetand creditul. O data ce creditul este resetat , un nou utilizator poate folosi aparatul.
