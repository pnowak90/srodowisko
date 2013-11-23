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
