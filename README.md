#ROZWIAZANIA

SRODOWISKO LAB1 ZADANIE 1 - kwadrat liczby

```c
int main()
{
  int x[50] = {0};
  int i     = 0;

  for(x[i]; i<50; i++)
    {
      x[i]=i;
      printf("Kwadrat liczby %d wynosi %d\n", x[i], x[i]*x[i]);
    }
}
```
SRODOWISKO LAB1 ZADANIE 2 - kwadrat

```c
int main()
{
  int i=1;
  
  for(i; i<= 1000; i++)
    {
      printf("%d ", i*i);
    }
}
```

SRODOWISKO LAB1 ZADANIE 3 - wczytywanie liczby + obliczenia

```c
int main()
{
  int x   = 0;
  int spr = 0;

  do
  {
    printf("Podaj liczbe: ");
    spr = scanf("%d", &x);

    fflush(stdin);
  }
  while( (spr = getchar()) != '\n' && spr != EOF) );

  printf("\nliczba = %d", x);
  printf("\nkwadrat = %d", x*x);
  printf("\nszescian = %d", x*x*x);

  printf("\n");

}
```
SRODOWISKO LAB1 ZADANIE 4 - wczytanie liczby + zabezpieczenie formatu

```c
int main()
{
  int x;
  int spr = 0;

  printf("Podaj liczbe: \n");

  do
  {
      spr  =  scanf("%d", &x);
      if(!spr) printf ("Blad formatu!\n");
      fflush(stdin);
  }
  while( spr == 0 );
    

  printf("Podana liczba to: %d\n", x);

}
```

SRODOWISKO LAB2 ZADANIE 1 - odwracanie tablicy

```c

main() {
int i;
int tabela[] = {1,2,4,6,12};
for(i = 4; i<=0; i = i-1)
printf("%i", tabela[i]
return 0;
}
```

SRODOWISKO LAB 2 ZADANIE 2 - suma kwadratow

```c

main()
{
	int n	  = 0;
	int i	  = 1;
	int suma  = 0;

	int n1, n2, n3;

	while( n <= 0 )
        {
	  printf("Podaj liczbe naturalna n: ");
	  scanf("%d", &n);
	  if( n <= 0 ) printf ("\nLiczba n musi byc wieksza od 0!\n");
	}

	for(i; i<=n; ++i)
	{
		suma = suma + i*i;
	}
	
	printf("\nSuma kwadratow = %d\n\n", suma);

	n1 = 5+3*8/2-3;
	n2 = 2%2+2*2-2/2;
	n3 = 2*4*(5+9/2);

	printf("n1 = %d\n", n1);
	printf("n2 = %d\n", n2);
	printf("n3 = %d\n", n3);		
}
```

SRODOWISKO LAB2 ZADANIE 3 - odwracanie tabeli + uzupelnianie tabeli

```c
int main()
{
	int tabela[] = {1,2,4,6,12};
	int i = 4;

	int tabela2[10];
	int j     = 0;
	int wpisz = 0;

	for(i; i>=0; i--)
	{
	  printf("indeks %d = %d\n", i, tabela[i]);
	}
	
	for(j; j<10; j++)
	{
	  printf("Podaj wartosc tabela2[ %d ]", j);
	  scanf("%d", &wpisz);
	  tablica2[j] = wpisz;
	}

	return 0;
}
```

SRODOWISKO LAB2 ZADANIE 4 - potegi liczby 2, petla for i while

```c
int main()
{
  int n = 1;

  for(n; n <=2010; n = n*2)
    {
      printf("%d\n", n);
    }

  n = 1;

  while( n <= 2010 )
  { 
    printf("%d\n", n);
    n *= 2;
  }


}
```

SRODOWISKO LAB2 ZADANIE 4 - dziesietny na binarny z for

```c

main()
{
	int liczba 	  =  0;
	int i 		  =  0;
	int wynik[16];

	printf ("Podaj liczbe w systemie dziesietnym: ");
	scanf  ("%d", &liczba);

	for(liczba; liczba > 0; i++)
	{
		wynik[i] = liczba%2;
		printf("Reszta z dzielenia %d przez 2 = %d\n", liczba, wynik[i]);
		liczba   = liczba/2;
		printf("Po podzieleniu liczba = %d\n", liczba);
	}

	printf("\nwynik = ");
	for(i--; i >= 0; i--) printf(" %d ", wynik[i]);

}
```

SRODOWISKO LAB3 ZADANIE 1 - porownywanie liczb

```c

main()
{
  int x = 0;
  int y = 0;
  int suma = 0;
  int i = 1;
  int a = 0;
  int b = 0;
  int c = 0;
  int obwod = 0;

  printf("Podaj pierwsa liczbe: ");
  scanf("%i", &x);
  if(x>5){printf("Liczba %i jest wieksza od 5\n", x);}
    else {printf("Liczba %i jest mniejsze od 5\n", x);}

  if(x>0){printf("Liczba %i jest wieksza od 0\n", x);}
    else if(x<0){printf("Liczba %i jest mniejsza od 0\n", x);}
       else{ printf("Liczba %i jest rowna 0\n", x);}

  if(x%2==0){printf("Liczba %i jest parzysta\n", x);}
     else{printf("Liczba %i jest nieparzysta\n", x);}

  printf("Podaj druga liczbe: ");
  scanf("%i", &y);
  if(x == y){printf("\nLiczby sa sobie rowne");}
    else{printf("\nLiczby %i i %i nie sa sobie rowne\n", x, y);}

  if(x>y){printf("Liczba x = %i jest wieksza\n", x);}
  else if(x<y){("Liczba y = %i jest wieksza\n", y);}
  else{("Liczby sa rowne\n");}

    while(i<=20)
      {
	suma += i*i;
	i++;
        printf("\nsuma kwadratow  = %i\n", suma);
      }

   getchar();
}
```

SRODOWISKO LAB3 ZADANIE 2 - trojkaty

```c

int main()
{
  int a = 1; int b = 1; int c = 1;
  int obwod = 10;
  int suma = 0;

    for(a = 1; a < obwod; a++)
    {
      for(b = a; b < obwod; b++)
      {
	for(c = b; c < obwod; c++)
	{
	  if(a+b>c && a+c>b && b+c>a && a+b+c <= obwod)
	    {
	    printf("bok a = %i\tbok b = %i\tbok c = %i\tobwod = %i\n", a, b, c, a+b+c);
	    suma++;
	    }
        }
      }
    }
    printf("\n%i", suma);
}
```

SRODOWISKO LAB3 ZADANIE 3 - kolumny

```c
int main()
{
  int n = -1;
  int i;
  int k = 0;
  while( n<0 ){
                  printf("Podaj liczbe n: ");
                  scanf("%i", &n);
  }
  double tab[n];
  for(i = 0; i<n; i++)  scanf("%lf", &tab[i]);	
  // for(i = 0; i<n; i++)  printf("%2.5lf", tab[i]);
  printf("\n\n");
  for(k; k<i; k++){
                   if( (k)%3==0) printf("\n");
                   printf("%6.2lf ", tab[k]); 
  }
  printf("\n");
 }
```

SRODOWISKO LAB4 ZADANIE 1 - liczba pierwsza
```c

int main()
{
  int liczba = 0;
  int dzielnik = 0;
  int wynik = 0;

  printf("Podaj liczbe: ");
  scanf("%i", &liczba);
  
  for(dzielnik = 2; dzielnik <= liczba - 1; dzielnik++)
    {
      if(liczba%dzielnik == 0) wynik++;
    }

  if(wynik == 0) printf("Liczba %i jest pierwsza\n", liczba);
        else     printf("liczba %i nie jest pierwsza\n", liczba);

  return 0;
}
```

SRODOWISKO LAB4 ZADANIE 2 - M, n najmniejsza liczba taka ze suma do n >= M

```c
int main()
{
  int M = 0;
  int n = 0;
  int suma = 0;
  int wyjscie = 0;

  printf("Podaj liczbe M: ");
  scanf("%i", &M);

  while(wyjscie == 0)
    {
       suma = suma + n;
       if(suma >= M) wyjscie = 1;
       n++;
    }
  
  printf("Najmniejsza liczba n = %i", n-1);
  
  return 0;
}
```

SRODOWISKO LAB4 ZADANIE 3 - wypisuje wszystkie dzielniki (z wyjatkiem 1 i samej siebie, tylko liczby nie-pierwsze)

```c
int main()
{
  int liczba = 0;
  int dzielnik = 0;

  printf("Podaj liczbe: ");
  scanf("%i", &liczba);
  
  for(dzielnik = 2; dzielnik <= liczba - 1; dzielnik++)
    {
      if(liczba%dzielnik == 0) 
	printf("Liczba %i jest dzielnikiem liczby %i\n", dzielnik, liczba);
    }

  return 0;
}
```

SRODOWISKO LAB3 ZADANIE 4 - konwersja z 10base na inny system (+ konwersja znakow A-F)
```c
main()
{
    int liczba    =  0;
    int i         =  0;
    int system    =  0;
    int wynik[16];

    char konwersja[16] = {'0','1','2','3','4','5','6','7','8','9','A','B','C','D','E','F'};

    printf ("Podaj liczbe w systemie dziesietnym: ");
    scanf  ("%d", &liczba);

    while(system < 2 || system > 16)
      {
	printf("Podaj podstawe systemu na jaki chcesz zmienic(od 2 do 16): ");
	scanf("%d", &system);
      }

    for(liczba; liczba > 0; i++)
    {
        wynik[i] = liczba%system;
        printf("Reszta z dzielenia %d przez %d  = %d\n", liczba, system, wynik[i]);
        liczba   = liczba/system;
        printf("Po podzieleniu liczba = %d\n", liczba);
    }

    printf("\nwynik = ");
    for(i--; i >= 0; i--) printf(" %c ", konwersja[ wynik[i] ]);

    printf("\n\n");
    return 0;
}
```
