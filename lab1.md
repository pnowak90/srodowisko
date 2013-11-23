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
