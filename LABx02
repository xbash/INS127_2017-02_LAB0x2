#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <stdbool.h>

/*
Laboratorio 2 | INS127 Estructuras de datos
Alumnos: Rodrigo Gonzalez, Jorge Sepulveda
Fecha: 01/09/2017
*/

//Pregunta 1

typedef struct{
    int **md;
    int filas;
    int columnas;

}Matrix;

void iniciarMatriz (Matrix *pm,int filas, int columnas);
void llenarMatriz(Matrix *pm);
void mostrarMatriz (Matrix *pm);
bool esPrimo(int n);
void primoFobico(Matrix *pm);

int main() {
    Matrix M;
    Matrix *pm=&M;

    iniciarMatriz(pm,3,3);
    mostrarMatriz(pm);

    printf ("Matriz re-generada: \n");
    llenarMatriz(pm);
    mostrarMatriz(pm);

    printf ("Revision de primos: \n");
    primoFobico(pm);
    mostrarMatriz(pm);

    return 0;
}

void iniciarMatriz (Matrix *pm,int filas, int columnas){
    pm->filas=filas;
    pm->columnas=columnas;
    pm->md  = (int**) malloc(filas * sizeof(float *));

    for (int i = 0; i < filas; i++){
        pm->md[i] = (int*) malloc(columnas*sizeof(int));
    }
    for (int i=0;i<pm->filas;i++) {
        for (int j = 0; j < pm->columnas; j++) {
            pm->md[i][j]= 0;
        }
    }
}

void llenarMatriz(Matrix *pm){
    int filas =pm->filas;
    int columnas = pm->columnas;
    srand(time(NULL));
    for (int i = 0; i < filas; i++){
        pm->md[i] = (int*) malloc(columnas*sizeof(int));
    }
    for (int i=0;i<pm->filas;i++) {
        for (int j = 0; j < pm->columnas; j++) {
            pm->md[i][j]= rand()%50;
        }
    }
}

void mostrarMatriz (Matrix *pm){
    for (int i=0;i<pm->filas;i++) {
        for (int j = 0; j < pm->columnas; j++) {
            printf ("%d \t",pm->md[i][j]);
        }
        printf ("\n");
    }
    printf("\n-------------------------\n");
}

void primoFobico(Matrix *pm){
    for (int i=0;i<pm->filas;i++) {
        for (int j = 0; j < pm->columnas; j++) {
            if (esPrimo(pm->md[i][j])){
                pm->md[i][j] = 0;
            }
        }
    }
}

bool esPrimo(int n){
    {
        int i, flag = 0;
        for(i=2; i<=n/2; ++i) {
            if(n%i==0){
                flag=1;
                break;
            }
        }

        if (flag==0)
            return true;
        else
            return false;
    }
}

// Pregunta 2
void PreguntaDosUno(int *A, int n){
    *A  = (int*) malloc(n * sizeof(int *));
    srand(time(NULL));
    for (int i=0;i<n;i++) A[i]= rand()%50;
}

void PreguntaDosDos(int *A,int n){
    int mayor, pmay, menor,pmen,aux = 0;
    for (int i=0;i<n;i++){
        if(A[i] > mayor){
            mayor = A[i];
            pmay=i;
        }
        if (A[i]< menor){
            menor = A[i];
            pmen=i;
        }
    }
    //Intercambio de posiciones
    aux = A[pmay];
    A[pmay]=A[pmen];
    A[pmen]=aux;
}
