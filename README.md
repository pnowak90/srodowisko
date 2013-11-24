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
najmniejsza liczba taka ze suma do n >= M
```c
int main(){
	int M, n = 0, suma = 0, wyjscie = 0;
	printf("Podaj liczbe M: ");
  	scanf("%i", &M);
	while(!wyjscie){
    	suma+=n;
       	if(suma>=M) wyjscie = 1;
       	++n;
    }
  	printf("Najmniejsza liczba n = %i", n-1);
  	return 0;
}
```
Program wypisuje wszystkie dzielniki (z wyjatkiem 1 i samej siebie, tylko liczby nie-pierwsze)
```c
int main(){
	int liczba, dzielnik;
  	printf("Podaj liczbe: ");
  	scanf("%i", &liczba);
  	for(dzielnik=2; dzielnik<liczba; ++dzielnik){
      	if(!(liczba%dzielnik)) 
			printf("Liczba %i jest dzielnikiem liczby %i\n", dzielnik, liczba);
    }	
	return 0;
}
```
Konwersja z 10base na inny system (+ konwersja znakow A-F)
```c
main(){
    int liczba, system, i, wynik[16];
	char konwersja[16] = {'0','1','2','3','4','5','6','7','8','9','A','B','C','D','E','F'};
	printf("Podaj liczbe w systemie dziesietnym: ");
    scanf("%d", &liczba);
	while(system<2 || system>16){
		printf("Podaj podstawe systemu na jaki chcesz zmienic(od 2 do 16): ");
		scanf("%d", &system);
    }
    for(liczba; liczba>0; ++i){
        wynik[i]=liczba%system;
        printf("Reszta z dzielenia %d przez %d  = %d\n", liczba, system, wynik[i]);
        liczba=liczba/system;
        printf("Po podzieleniu liczba = %d\n", liczba);
    }
    printf("\nwynik = ");
    for(i--; i>=0; i--) printf(" %c ", konwersja[ wynik[i] ]);
    printf("\n\n");
    return 0;
}
```
Kopiowanie zawartosci jednego pliku do drugiego
```c
int main (int argc, char *argv[]){
	FILE *fin;   /* uchwyt do pliku wejściowego */
  	FILE *fout;  /* uchwyt do pliku wyjściowego */
  	int c;
	if(argc!=3){
    	printf("Użycie: %s SOURCE DEST\n", argv[0]);
    	return 3;
  	}
  	if( !(fin = fopen(argv[1],"r")) ){
    	printf("Nie mogę otworzyć pliku do czytania '%s'\n", argv[1]);
    	return 1;
  	}
  	if ( !(fout = fopen(argv[2],"w"))){
    	printf("Nie mogę otworzyć pliku do zapisu '%s'\n", argv[2]);
    	return 2;
  	}
	printf("Kopiowanie pliku: %s -> %s\n", argv[1], argv[2]);
	while ((c = fgetc(fin)) != EOF){
    	fputc(c, fout);
  	}
  	fclose(fin);
  	fclose(fout);
	return 0;
}
```
Do pliku podanego z linii argumentów zapisywanie trzech kolumn liczb
```c
int main(int argc, char *argv[]){
  	double tab1[11], tab2[11], tab3[11];
  	int i;
  	FILE *FOUT;
	for(i=0; i<=10; i++) tab1[i]=i*0.1;
  	for(i=0; i<=10; i++) tab2[i]=tab1[i]*tab1[i];
  	for(i=0; i<=10; i++){
      	tab3[i]=random() % 100;
      	tab3[i]/=100;
	}
  	FOUT=fopen(argv[1],"w");
  	for(i=0; i<=10; i++) fprintf(FOUT, "%6.2f\t%6.2f\t%6.2f\n", tab1[i],tab2[i],tab3[i]);
	fclose(FOUT);
  	return 0;
}
```
Program generuje 1000 losowych liczb z danego zakresu i na bierząco zapisuje do pliku nowy.txt w dwóch kolumnach wygenerowana liczbe i aktualna srednia
```c
int main(int argc, char *argv[])
{	
	const int rozmiar = 1000;
	double tab[rozmiar];
	int i;
	int suma = 0;
	double srednia = 0;
	FILE *nowy;	
	srand (time(NULL));	
	nowy = fopen("nowy.txt", "w");
	
	for(i = 0; i<rozmiar-1; ++i){
		tab[i] = random() % 1000;
		suma += tab[i];
		srednia = suma/(i+1);
		fprintf(nowy, "%6.2f \t %6.2f\n", tab[i], srednia);
	}
	fclose(nowy);	
	return 0;
}
```
#ROZWIAZANIA LAB 5
Iloczyn skalarny poszczególnych elementów dwóch tablic
```c
int main(){
  	int rozmiar, i;
  	printf("Podaj rozmiar tablicy: ");
  	scanf("%i", &rozmiar);
  	double t1[rozmiar], t2[rozmiar], wynik;
  	for(i=0; i<rozmiar; ++i){
		printf("Podaj parametr tablicy 1 elementu %d: ", i);
    	scanf("%lf", &t1[i]);
    	printf("Podaj parametr tablicy 2 elementu %d: ", i);
    	scanf("%lf", &t2[i]);
    }
	puts("\nZakonczono wczytywanie wszystkich elementow\n");
  	wynik = 0;
  	for(i=0; i<rozmiar; ++i){
    	wynik += t1[i]*t2[i];
    	printf("\nIloczyn skalarny elementow nr %i = %lf:\n ", i, wynik);
  	}
  	return 0;
}
```
Porównanie leksykograficzne dwóch tablic
```c
int main(){

  int rozmiar, i, wyjscie;
  printf("Podaj rozmiar tablicy: ");
  scanf("%i", &rozmiar);

  double t1[rozmiar], t2[rozmiar];
  for(i=0; i<rozmiar; ++i)
    {
    printf("Podaj parametr tablicy 1 elementu %d: ", i);
    scanf("%lf", &t1[i]);
    }
  for(i=0; i<rozmiar; ++i)
    {
    printf("Podaj parametr tablicy 2 elementu %d: ", i);
    scanf("%lf", &t2[i]);
    }
  puts("\nZakonczono wczytywanie wszystkich elementow\n");

  i = 0;
  wyjscie = 0;
  while(i<rozmiar && wyjscie == 0)
    {
      if( t1[i]!=t2[i] )
        {
          puts("Tablice nie sa sobie rowne");
          if( t1[i]<t2[i] ) puts("tablica t1 poprzedza leksykograficznie tablice t2");
          else puts("tablica t2 poprzedza leksykograficznie tablice t1");
          wyjscie = 1;
        }
      ++i;
    }
  if(wyjscie == 0 ) puts("Wszystkie elementy obu tablic sa sobie rowne");

  return 0;
}
```
Porownanie leksykograficzne dowolnej liczby tablic
```c
int main(){
  int ile_tablic, rozmiar, i, j, ostatnia, przerwanie, max;
  puts("Ile tablic chcesz wczytac?");
  scanf("%i", &ile_tablic);
  puts("Jaki ma byc rozmiar tablicy?");
  scanf("%i", &rozmiar);

  double tablica[ ile_tablic ][ rozmiar ];

  puts("Rozpoczyna sie inicjalizacja tablic");
  for(j=0; j<ile_tablic; ++j)
    {
      printf("Inicjowanie tablicy nr %i\n", j);
      for(i=0; i<rozmiar; ++i)
        {
          printf("Element nr %i = ", i);
          scanf("%lf", &tablica[j][i]);
        }
    }
  puts("Inicjalizacja zakonczona sukcesem");

  puts("Rozpoczyna sie porownywanie tablic");
  przerwanie = 0;
  i = 0;
  while( i<=rozmiar && przerwanie == 0)
    {
      printf("Sprawdzanie elementow nr %i\n", i);
      ostatnia = tablica[0][i];
      max = 0;
      for(j=1; j<ile_tablic; ++j)
        {
          if( tablica[j][i] != ostatnia )
            {
              if( tablica[j][i]>ostatnia )
                {
                  ostatnia = tablica[j][i];
                  przerwanie = 1;
                  max = j;
                }
            }

        }
      ++i;
    }
  puts("Porownywanie tablic zakonczone sukcesem");

  if(przerwanie == 0) puts("Wszystkie elementy sa sobie rowne");
  else printf("najwieksza leksykograficznie jest tablica nr %i\n", max);

  return 0;
}
```
Szyfr Cezara. Program jako poprawne traktuje tylko małe i duże litery, inne znaki traktuje jako błąd.
```c
int main(){
   const int max_sz = 100;
   char slowo[ max_sz ];
   int i, przerwanie, blad = 1;

   while( blad == 1){
      puts("Podaj slowo do zaszyfrowania: ");
      scanf("%s", slowo);
      printf("Podane slowo to: %s\n", slowo);
      puts("Rozpoczecie sprawdzania poprawnosci slowa");
      i = 0;
      while( slowo[i] != 0 && blad == 1){
	  if( (slowo[i] < 65) || (slowo[i] > 90 && slowo[i] < 97) || (slowo[i] > 122) )
	    puts("Uzyles niedozwolonych znakow, sprobuj jeszcze raz!");
	  else blad = 0;
	  ++i;
       }
   puts("Zakonczenie sprawdzania poprawnosci slowa");
   }
  puts("Rozpoczecie szyfrowania");
  przerwanie = 0;
  i = 0;
  while( przerwanie == 0){
      if( slowo[i] == 0) przerwanie = 1;
      else{
	  slowo[i] += 1;
	  if( slowo[i] > 122 ) slowo[i] -= 26;
      }
      ++i;
   }
  puts("Zakonczenie szyfrowania");
  printf("Zaszyfrowane slowo wyglada tak: %s\n", slowo);

  return 0;  
}
```
#ROZWIAZANIA LAB 6
Ćwiczenie na instrukcje switch
```c
int main()
{
  int x, i;
  while(1){
    puts("Podaj liczbe: ");
    scanf("%i",&x);
    printf("Podales liczbe: %i\nWYKONANE POLECENIE: ", x);
    switch(x){
        case 1:  puts("A"); break;
        case 2:  puts("C"); break;
        case 3:  puts("F"); break;
        case 4:  puts("ZWLOKA CZASOWA, CZEKAJ!"); 
	         for(i=0; i<10000*10000; ++i)138946546486; break;
        case 0:  puts("WYJSCIE"); return 0; 
	         puts("To sie nie wyswietli"); break;
        default: puts("Nieznana komenda!"); break;
    }
  }
  printf("Wyszedles z programu, podales liczbe 0", x);
  return 0;
}
```
Program wyswietla jaki dzien tygodnia od podanego bedzie za okreslona liczbe dni
```c
#include <stdio.h>
int main(){
  int dzien_tygodnia, za_ile, next;
  while(1){
    puts("Podaj dzisiejszy dzien tygodnia (1-7), 0 wylacza program : ");
    scanf("%i", &dzien_tygodnia);
    printf("Podales dzien tygodnia numer %i\n", dzien_tygodnia);

    if(!dzien_tygodnia){
      puts("KONIEC PRACY PROGRAMU");
      break;
    }

    if(dzien_tygodnia<0 || dzien_tygodnia>7){
       puts("ZLY DZIEN, BLAD!");
       continue;
    }

    puts("Ile dni ma uplynac?");
    scanf("%i", &za_ile);

    next=dzien_tygodnia+za_ile%7;
    while(next>7){
      next=next%7;
    }

    printf("Za %i dni bedzie: ", za_ile);

   switch(next){
     case 1:  puts("Poniedzialek"); break;
     case 2:  puts("Wtorek"); break;
     case 3:  puts("Sroda"); break;
     case 4:  puts("Czwartek"); break;
     case 5:  puts("Piatek"); break;
     case 6:  puts("Sobota"); break;
     case 7:  puts("Niedziela");break;
    default: puts("BLAD!"); break;
   }

   next = 0;
 }
  return 0;
}
```
Modyfikacja poprzedniego programu, wykorzystanie funkcji + czyszczenie bufora dla błędu formatu.
```c
void funkcja(int argument){

  switch(argument){
     case 1:  puts("Poniedzialek"); break;
     case 2:  puts("Wtorek"); break;
     case 3:  puts("Sroda"); break;
     case 4:  puts("Czwartek"); break;
     case 5:  puts("Piatek"); break;
     case 6:  puts("Sobota"); break;
     case 7:  puts("Niedziela");break;
     default: puts("BLAD!"); break;
   }
}

int main(){
  int dzien_tygodnia, za_ile, next;
  while(1){
    puts("Podaj dzisiejszy dzien tygodnia (1-7), 0 wylacza program : ");
    scanf("%i", &dzien_tygodnia);

    if(!dzien_tygodnia){
      puts("KONIEC PRACY PROGRAMU");
      break;
    }
    if(dzien_tygodnia<0 || dzien_tygodnia>7){
       puts("ZLY DZIEN, BLAD!");
       fflush(stdin);
       continue;
    }

    puts("Dzisiaj jest: ");
    funkcja(dzien_tygodnia);

    puts("Ile dni ma uplynac?");
    scanf("%i", &za_ile);

    next=dzien_tygodnia+za_ile%7;
    while(next>7){
      next=next%7;
    }
    printf("Za %i dni bedzie: ", za_ile);
    funkcja(next);
    next = 0;
  }
  return 0;
}

```
Ćwiczenie z wykorzystaniem funkcji
```c
int wprowadz(void){
  int N;
  puts("Podaj ile razy chcesz wypisac \"Dzien Dobry\": ");
  scanf("%i", &N);
  return N;
}
void funkcja(int argument){
  int i;
  for(i=0; i<argument; ++i) puts("Dzien Dobry");
}

int main(){
  funkcja( wprowadz() );
  return 0;
}
```
