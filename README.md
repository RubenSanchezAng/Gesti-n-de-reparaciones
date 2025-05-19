# Servicio de Reparaciones Informáticas  <img src="LogoEmpresa.png" alt="Icono" width="60"/>

## Gestión de reparaciones

## :busts_in_silhouette: Integrantes del Grupo

Este proyecto ha sido desarrollado por estudiantes del **1º DAW - IES Font de Sant Lluís**:

- :bust_in_silhouette: Manuel Rubio
- :bust_in_silhouette: Irma
- :bust_in_silhouette: Ruben
- :bust_in_silhouette: Alejandro

| Nombre     | Rol   | Subsistema             |
|------------|-------|------------------------|
| Manu       | Coordinador   | Gestión de materiales  |
| Ruben      | Facilitador   | Gestión de reparaciones|
| Alejandro  |  Secretario   | Gestión de clientes    |
| Irma       |   Portavoz | Gestión de informes    |

---
### Introducción
El **Subsistema de Gestión de Reparaciones** nos permite controlar y realizar las reparaciones de los ordenadores. Esto tiene distinas funciones:
- :mechanic:	Registro de reparaciones y diagnosticar del problema.
- :heavy_dollar_sign: Estimación de costes
- :hammer_and_wrench: Asignación de reparadores y materiales
- :hourglass_flowing_sand: Estado de la reparación
- :page_with_curl: Generación de reportes de reparaciones

 :bulb: _Este subsistema se integra con los módulos de materiales, personal, clientes y clientes.

 ---

## :package: Funcionalidades

###  :mechanic:	Registro de reparaciones y diagnosticar del problema.

- El técnico registra el equipo
- Se realiza un primer diagnóstico
- Se describe el problema

---
### :heavy_dollar_sign: Estimación de costes

- Se realiza una estimación de materiales
- Se realiza una estimación de mano de obra
- Se pone un tiempo de espera al cliente
- Se entrega al cliente un presupuesto con estos datos
  
> [!IMPORTANT]  
> Si no acepta el presupuesto se le entregaría el ordenador sin reparar

---
###  :hammer_and_wrench: Asignación de reparadores y materiales

- Se visualiza los técnicos disponibles
- Se asigna un técnico a una reparación


---

###  :hourglass_flowing_sand: Estado de la reparación

- El cliente busca su ordenador
- El cliente visualiza el estado

  ---

### - :page_with_curl: Generación de reportes de reparaciones
- Reparaciones realizas
- Tipo de reparaciones
- Frecuencia del problema en ese ordenador
  
> [!NOTE]  
> Este informe se entregará con el ordenador una vez reparado

---

## Estructura de Java
> [!IMPORTANT]  
> Esto solo es una parte del código del subsitema de gestión de reparaciones
``` java
public class prueba{
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<Estimacion> estimacions = new ArrayList<>();
        int x =0;

        do{
            System.out.println("1. Agregar Mano de Obra\n2.Agregar Material\n3. Mostrar todas las estimaciones\n4. Guardar estimaciones en archivo HTML");
            x=scanner.nextInt();
            scanner.nextLine();
            switch (x) {
                case 1:
                    // Agregar Mano de Obra
                    System.out.print("Ingrese el nombre de la mano de obra: ");
                    String nombreManoObra = scanner.nextLine();
                    System.out.print("Ingrese el costo de la mano de obra: ");
                    double costoManoObra = scanner.nextDouble();
                    scanner.nextLine();  
                    estimacions.add(new ManoObra(nombreManoObra, costoManoObra));
                    System.out.println("Mano de obra agregada.");
                    break;

                case 2:
                    // Agregar Material
                    System.out.print("Ingrese el nombre del material: ");
                    String nombreMaterial = scanner.nextLine();
                    System.out.print("Ingrese el costo del material: ");
                    double costoMaterial = scanner.nextDouble();
                    scanner.nextLine();  
                    estimacions.add(new Material(nombreMaterial, costoMaterial));
                    System.out.println("Material agregado.");
                    break;

                case 3:
                    if (estimacions.isEmpty()) {
                        System.out.println("No hay estimaciones.");
                    } else {
                        leerFileReader("./estimacion.html");
                    }
                    break;

                case 4:
                    escribirFileWriter(estimacions, "./estimacion.html");
                    System.out.println("Estimaciones guardadas en estimacion.html");
                    break;
            }
        }while(x!=0);

        
    }
```
