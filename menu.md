# proyecto
#ifndef MENU_H_
#define MENU_H_

#include "ArregloDepa.h"
#include "Archis.h"
#include <string.h>
void cliente(NodoDepa *tienda);
void administrador(NodoDepa *tienda);
void inicio(NodoDepa *tienda);
int main(void){

	int opcion=0;
	NodoDepa *tienda=NULL;
	inicio(tienda);
	//leer(tienda);

	 printf("\n\t\t%c=========================================%c",201,187);
     printf("\n\t\t%c Universidad Nacional Aut%cnoma de M%cxico %c",186,162,130,186);
     printf("\n\t\t%c=========================================%c",200,188);
     printf("\n\t\t");
     printf("\n\t%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c",201,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,187);	printf("\t\t %c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c",196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196);
     printf("\n\t%c Fac. de Ingenier%ca %c",186,161,186); 																									printf("\t\t %c Proyecto: Sistema de Ventas %c",179,179);
     printf("\n\t%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c",200,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,188);    printf("\t\t %c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c",196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196,196);

     printf("\n\t\t");
     printf("\n\t\t\t      Integrantes:");
     printf("\n\t\t");
     printf("\n\t L%cpez Vite Erick Misael \n\t Maya Ram%crez Karen \n\t Torres Caballero Bruno",162,161);

     printf("\n\t\t");
     printf("\n\t\t\t%c Profesor: Ing. Fernando Robles Mu%coz %c",195,164,180);
     printf("\n\t\t\t%c---------------------------------------------%c ",193,193);

     printf("\n\n\t Presiona cualquier tecla para pasar a nuestra siguiente pantalla: ");
     getchar();
     system("clear");

	do{
		 system("clear");
		 printf("\n\t\t%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c",201,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,187);
		 printf("\n\t\t%c Inserte nombre de tienda aqui xD %c",186,186);
		 printf("\n\t\t%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c",200,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,188);
		 printf("\n\n");

	   	 printf("\n\t1. Administrador\n");
	   	 printf("\n\t2. Cliente\n\n");
	     printf("\n\t3. Salir\n");
	     printf("\t\t\t %c Seleccione la opci%cn: ",175,162);
	     fflush(stdin);//limpia el buffer del teclado
	     scanf("%d",&opcion);//Switch case del menú principal

	     switch (opcion){
	     		case 1: // Administrador
	     			//contraseña y clave simples
	     			administrador(tienda);
	     			break;
	     		case 2: //Cliente
	     			cliente(tienda);
	     			break;
	     		case 3: //salir
	     			break;
	     		default:
	     			printf("Opcion no valida\n");
	     			getchar();


	     }
	}while(opcion!=3);

	//funciones para volver a escribir todo en los mismos archivos
	//Funciones para liberar toda la memoria

	//escribir(tienda);
	return 0;
}

void administrador(NodoDepa *tienda){
	int opcion,depa,producto;
	do{
		system("clear");
		printf("1. Agregar Departamento\n");
		printf("2. Eliminar Departamento\n");
		printf("3. Agregar Producto a algun Departamento\n");
		printf("4. Eliminar Producto a algun Departamento\n");
		printf("5. Cambiar Precios\n");
		printf("6. Agregar al inventario\n");
		//printf("7. Revertir ultima compra\n");
		printf("7. Salir");

		switch(opcion){
			case 1: 
				system("clear");
				listaDepa_ingresar(tienda);
				break;
			case 2:
				system("clear");
				listaDepa_imprimir(tienda);
				printf("Seleccione una opcion:\t");
				fflush(stdin);
				scanf("%d",&depa);
				listaDepa_remover(tienda,depa);
				break;
			case 3: 
				system("clear");
				listaDepa_imprimir(tienda);
				printf("Seleccione una opcion:\t");
				fflush(stdin);
				scanf("%d",&depa);
				listaDepa_agregarProd(tienda,depa);
				break;
			case 4: 
				system("clear");
				listaDepa_imprimir(tienda);
				printf("Seleccione una opcion:\t");
				fflush(stdin);
				scanf("%d",&depa);
				listaDepa_obtener(tienda,depa);
				printf("Seleccione una opcion:\t");
				fflush(stdin);
				scanf("%d",&producto);
				listaDepa_eliminarProd(tienda,depa,producto);
				break;
			case 5: 
				system("clear");
				listaDepa_imprimir(tienda);
				printf("Seleccione una opcion:\t");
				fflush(stdin);
				scanf("%d",&depa);
				listaDepa_obtener(tienda,depa);
				printf("Seleccione una opcion:\t");
				fflush(stdin);
				scanf("%d",&producto);
				listaDepa_cambiarPrecio(tienda,depa,producto);
				break;
			case 6: 
				system("clear");
				listaDepa_imprimir(tienda);
				printf("Seleccione una opcion:\t");
				fflush(stdin);
				scanf("%d",&depa);
				listaDepa_obtener(tienda,depa);
				printf("Seleccione una opcion:\t");
				fflush(stdin);
				scanf("%d",&producto);
				listaDepa_agregarInventario(tienda,depa,producto);
				break;
			default: 
				printf("Opcion no valida\n");
				getchar();
		}

	}while(opcion != 7);

}

void cliente(NodoDepa *tienda){
	 int depa,opcion,articulo,cantidad;
	 char seguir;
	 do{
		 system("clear");
		 printf("1. Comprar\n");
		 printf("2. Mostrar todo en la tienda\n");
		 printf("3. Salir\n");
		 scanf("%d",&opcion);
		 switch(opcion){
		 		case 1:
		 		 	 listaDepa_imprimir(tienda);
					 printf("\n\tSeleccione un Departamento\n\n");
					 scanf("%d",&depa);
					 listaDepa_obtener(tienda,depa);
					 printf("\nArticulo:\t");
					 scanf("%d",&articulo);
					 printf("\nCantidad:\t");
					 scanf("%d",&cantidad);
					 listaDepa_comprar(tienda,depa,articulo,cantidad);
					 
					 //hacer algo para los tikets
					 
					 printf("¿Desea seguir comprando?(S/N)\n");
					 scanf("%c",&seguir);

					 if((seguir=='n') || (seguir=='N')){
					 	opcion = 3;
					 }

					 break;
				case 2:
					listaDepa_imprimirTodo(tienda);
					break;
				default:
					printf("Opcion no valida\n");
		}
	}while(opcion!=3);

}

void inicio(NodoDepa *tienda){
	tienda = malloc(sizeof(NodoDepa));
	NodoDepa *nodoDepaAct = tienda;


		//nodoDepaAct->Depa = "Electronica";

		strcpy(nodoDepaAct->Depa,"Electronica");
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		
		NodoProducto *nodoActual = nodoDepaAct->inicio;

		strcpy(nodoActual->producto,"TVSony40");
		nodoActual->precio = 8500;
		nodoActual->cantidad = 20;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto,"TVSamsung32");
		nodoActual->precio = 4900;
		nodoActual->cantidad= 20;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
 		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto, "XperiaM4");
		nodoActual->precio = 4500;
		nodoActual->cantidad= 20;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto ,"Iphone6S");
		nodoActual->precio = 16300;
		nodoActual->cantidad= 20;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "MinicomponenteLG230W");
		nodoActual->precio = 1800;
		nodoActual->cantidad= 20;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoDepa));
		nodoDepaAct = nodoDepaAct->sigDepa;



		strcpy(nodoDepaAct->Depa,"Hogar");
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoDepaAct->inicio;

		strcpy(nodoActual->producto , "MantelFino");
		nodoActual->precio = 350;
		nodoActual->cantidad = 50;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "VajillaClasica16");
		nodoActual->precio = 790;
		nodoActual->cantidad= 80;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
 		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "BuroChocolate");
		nodoActual->precio = 1650;
		nodoActual->cantidad= 30;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "ComodaChocolate");
		nodoActual->precio = 950;
		nodoActual->cantidad= 50;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "MaletaIpack");
		nodoActual->precio = 630;
		nodoActual->cantidad= 60;

		
		nodoDepaAct->inicio = malloc(sizeof(NodoDepa));
		nodoDepaAct = nodoDepaAct->sigDepa;

		strcpy(nodoDepaAct->Depa,"Electrodomesticos");
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoDepaAct->inicio;

		strcpy(nodoActual->producto , "RefrigeradorLG9");
		nodoActual->precio = 10900;
		nodoActual->cantidad = 20;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "RefrigeradorMabe11");
		nodoActual->precio = 4900;
		nodoActual->cantidad= 15;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
 		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "EstufeWH30");
		nodoActual->precio = 5190;
		nodoActual->cantidad= 30;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "MicroondasLG2");
		nodoActual->precio = 3100;
		nodoActual->cantidad= 50;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "MicroondasLG1.1");
		nodoActual->precio = 2100;
		nodoActual->cantidad= 60;


		
		nodoDepaAct->inicio = malloc(sizeof(NodoDepa));
		nodoDepaAct = nodoDepaAct->sigDepa;

		strcpy(nodoDepaAct->Depa,"Videojuegos");
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoDepaAct->inicio;

		strcpy(nodoActual->producto , "Halo5Xbox");
		nodoActual->precio = 950;
		nodoActual->cantidad = 50;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "FIFA16XBOX");
		nodoActual->precio = 950;
		nodoActual->cantidad= 80;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
 		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "SuperSmashBros10");
		nodoActual->precio = 950;
		nodoActual->cantidad= 30;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "CODBO3PS4");
		nodoActual->precio = 950;
		nodoActual->cantidad= 50;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "MarioKart8");
		nodoActual->precio = 630;
		nodoActual->cantidad= 60;



		
		nodoDepaAct->inicio = malloc(sizeof(NodoDepa));
		nodoDepaAct = nodoDepaAct->sigDepa;


		strcpy(nodoDepaAct->Depa,"Alimentos");
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoDepaAct->inicio;

		strcpy(nodoActual->producto , "Manzana1Kg");
		nodoActual->precio = 28;
		nodoActual->cantidad = 500;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "Fresa1Kg");
		nodoActual->precio = 28;
		nodoActual->cantidad= 500;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
 		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "Brocoli");
		nodoActual->precio = 12;
		nodoActual->cantidad= 500;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "Cebolla");
		nodoActual->precio = 3;
		nodoActual->cantidad= 500;
		
		nodoDepaAct->inicio = malloc(sizeof(NodoProducto));
		nodoActual = nodoActual->sigProducto;

		strcpy(nodoActual->producto , "MilkyWay60gr");
		nodoActual->precio = 12;
		nodoActual->cantidad= 600;
}
#endif
