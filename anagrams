#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void removerCaracteres(char *cadena, char *caracteres);

int comparar(const void *a, const void *b);

int esAnagrama(char *cadena, char *otraCadena);

int main() {
  int opcion = 0;
  int i = 0;
  char palabra[255];
  char palabra2[255];

  while (opcion != 2) {
    printf("\nPresione 1 para ejecutar, 2 para salir del programa.\n");
    scanf("%d", &opcion);

    switch (opcion) {
    case 1: {
      printf("Ingrese la primer cadena: ");
      scanf("%s", palabra);

      printf("Ingrese la segunda cadena: ");
      scanf("%s", palabra2);

      printf("\n\nLas cadenas '%s' y '%s'\n", palabra, palabra2);

      int resultado = esAnagrama(palabra, palabra2);

      if (resultado) {
        printf("Son anagramas");
      } else {
        printf("No son anagramas");
      }
      break;
    }
    }
  }
}

int comparar(const void *a, const void *b) {
  return strcmp((char *)a, (char *)b);
}

void removerCaracteres(char *cadena, char *caracteres) {
  int indiceCadena = 0, indiceCadenaLimpia = 0;
  int deberiaAgregarCaracter = 1;

  while (cadena[indiceCadena]) {
    deberiaAgregarCaracter = 1;
    int indiceCaracteres = 0;

    while (caracteres[indiceCaracteres]) {
      if (cadena[indiceCadena] == caracteres[indiceCaracteres]) {
        deberiaAgregarCaracter = 0;
      }
      indiceCaracteres++;
    }

    if (deberiaAgregarCaracter) {
      cadena[indiceCadenaLimpia] = cadena[indiceCadena];
      indiceCadenaLimpia++;
    }
    indiceCadena++;
  }

  cadena[indiceCadenaLimpia] = 0;
}

int esAnagrama(char *palabra, char *otraPalabra) {

  removerCaracteres(palabra, " ,.!");
  removerCaracteres(otraPalabra, " ,.!");

  int i = 0;

  while (palabra[i] != '\0') {
    if (palabra[i] >= 'A' && palabra[i] <= 'Z') {
      palabra[i] = palabra[i] + 'a' - 'A';
    }
    i = i + 1;
  }

  i = 0;
  while (otraPalabra[i] != '\0') {
    if (otraPalabra[i] >= 'A' && otraPalabra[i] <= 'Z') {
      otraPalabra[i] = otraPalabra[i] + 'a' - 'A';
    }
    i = i + 1;
  }

  qsort(otraPalabra, strlen(otraPalabra), sizeof(char), comparar);
  qsort(palabra, strlen(palabra), sizeof(char), comparar);

  return strcmp(palabra, otraPalabra) == 0;
}
