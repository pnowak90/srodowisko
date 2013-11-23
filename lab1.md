#ROZWIAZANIA LAB 1
Program wypisuje kolejno kwadraty 50 liczb naturalnych włączając 0
```c
int main(){
	int x[50],i;
  	for(i=0; i<50; i++){
      x[i]=i;
      printf("Kwadrat liczby %d wynosi %d\n", x[i], x[i]*x[i]);
    }
}
```
Wczytanie liczby + zabezpieczenie formatu
```c
int main(){
  	int x, spr=0;
	printf("Podaj liczbe: \n");
	do{
      spr=scanf("%d", &x);
      if(!spr) printf("Blad formatu!\n");
      fflush(stdin);
  	}while( spr == 0 );
	printf("Podana liczba to: %d\n", x);
}
```
#ROZWIAZANIA LAB 2
Wypisywanie tablicy w odwrotnej kolejności
```c
main(){
	int tabela[] = {1,2,4,6,12}, i;
	for(i=sizeof(tabela)/sizeof(int)-1 ; i>=0; --i)
		printf("%i\n", tabela[i]);
	return 0;
}
```
Suma kwadratów + zabezpieczenie formatu
```c
main(){
	int n=0, i, suma=0, spr=0;
	do{
		printf("Podaj liczbe naturalna n: ");
	  	spr=scanf("%d", &n);
	  	if(n<=0) printf ("\nLiczba n musi byc wieksza od 0!\n");
	  	fflush(stdin);
	}while(spr==0 || n<=0);
	for(i=1; i<=n; ++i) suma+=i*i;	
	printf("\nSuma kwadratow = %d\n\n", suma);
} 
```
Potęgi liczby 2, wykorzystanie for i while
```c
int main(){
  	int n;
	for(n=1; n<=2010; n=n*2) printf("%d\n", n);
	n=1;
	while(n<=2010){ 
    	printf("%d\n", n);
    	n *= 2;
  	}
return 0;
}
```
#ROZWIAZANIA LAB 3
Trojkaty. Program wypisuje ile jest trojkatow o niepowtarzajacych sie dlugosciach boku dajacych dany obwod.
```c
int main()
{
  int a, b, c, obwod, spr, suma = 0;
	do{
		puts("Podaj rzadany obwod:");
		spr=scanf("%i", &obwod);
		puts("");
		fflush(stdin);
	}while( spr == 0 || obwod <= 4);
    for(a=1; a<obwod; ++a){
    	for(b=a; b<obwod; ++b){
			for(c=b; c<obwod; ++c){
	  			if(a+b>c && a+c>b && b+c>a && a+b+c==obwod){
	    			printf("bok a = %i\tbok b = %i\tbok c = %i\tobwod = %i\n", a, b, c, a+b+c);
	    			suma++;
	    		}
        	}
      	}
    }
    printf("\n%i", suma);
    return 0;
}
```
Wypisywanie liczb w trzech kolumnach
```c
int main(){
  	int n=-1, i, k;
  	while( n<0 ){
		printf("Podaj liczbe n: ");
        scanf("%i", &n);
  	}
  	double tab[n];
  	for(i=0; i<n; ++i) scanf("%lf", &tab[i]);	
  	printf("\n\n");
  	for(k=0; k<i; k++){
    	if(!(k%3)) printf("\n");
        printf("%6.2lf ", tab[k]); 
  	}
  printf("\n");
 }
 ```
#ROZWIAZANIA LAB 4
Program sprawdza czy liczba jest pierwsza
```c
int main(){
	int liczba, dzielnik, wynik = 0;
	printf("Podaj liczbe (nie mniejsza jak 2): ");
  	scanf("%i", &liczba);
  	for(dzielnik=2; dzielnik<liczba; dzielnik++)
      if(liczba%dzielnik == 0) wynik++;

  	if(!wynik) printf("Liczba %i jest pierwsza\n", liczba);
        else printf("liczba %i nie jest pierwsza\n", liczba);

  return 0;
}
```
