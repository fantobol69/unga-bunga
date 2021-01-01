# unga-bunga

#include <iostream>

#define PALITOS_INICIALES 30
#define MAX_SACADAS 3

using namespace std;

int main() {


  bool salir = false;

int palitos = PALITOS_INICIALES;

int maxSacadas = MAX_SACADAS;

int Jugador1 = 2;

int Jugador0 = 1;

while (salir == false)

{int op;do

{
        cout << "***El Ultimo Palito Pierde***" <<endl;

         cout << "     Menu"<<endl;
         cout << endl;
         cout << "________________________________________" <<endl;
         cout << "|1- juego nuevo.                        |" <<endl;
         cout << "|2- editar cantidad de palitos iniciales|" <<endl;
         cout << "|3- editar cantidad maxima de sacadas.  |" <<endl;
         cout << "|4- estadisticas.                       |" <<endl;
         cout << "|0- salir.                              |" <<endl;
        cin >> op; }
        
        while (op < 0 or op > 4);

    
  int jugadorActual = 1;
  bool jugando = true;


  switch(op) {
    case 1:
    while(jugando) {

    if(jugadorActual == 1) {
      jugadorActual = 2;
    } else {
      jugadorActual = 1;
    }

    cout << "_______________________" << endl;
    cout << "Turno Del Jugador" << jugadorActual << endl;
    cout << "Palos En La Pila ("<< palitos << "):" << endl;
    for(int i=0; i < palitos ; i++) {
      cout << "/";
    }
    cout << endl;

    int saca = 0;
    do {
      cout << "Palos Para Sacar (1 - " << maxSacadas << "): ";
      cin >> saca;
    } while(saca < 1 or saca > maxSacadas);

    palitos = palitos -saca;

    if(palitos == 1) {
      cout << "!Final Del Juego! ";
      jugando = false;
    } else if (palitos <= 3) {

      maxSacadas = palitos - 1;
    }}
  cout << "!El Ganador Es Jugador! " << jugadorActual << "." << endl;

  if (jugadorActual == 0)  {Jugador0++; }
  else { Jugador1++;}
  break;
case 2:
  do { cout << "Elegi El Numero de Palos Iniciales Entre 30 y 100: ";
  cin >> palitos; }
  while (palitos < 30 or palitos > 100);
  break;

  case 3:
  do {
  cout << "Elegi El Numero Maximo De Sacadas: ";
  cin >> maxSacadas;
   if (maxSacadas < 3)
   {cout << "Muy Corto" << endl; } else if (maxSacadas > 30 * palitos / 100) {
   cout << "Muy Largo" << endl;} } while (maxSacadas < 3 or maxSacadas > 30 * palitos / 100);
 break;

  case 4:
  cout << "El Jugador 1 Ha Ganado " << Jugador0 << " Veces";
  cout << endl;
  cout << "El Jugador 2 Ha Ganado " << Jugador1 << " Veces";
  cout << endl;
  break;

  case 0:
  cout << "hasta el proximo juego!";
  salir = true;
  break;
  }
  }
}
