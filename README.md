# Servicio de Reparaciones Informáticas  <img src="LogoEmpresa.png" alt="Icono" width="60"/>

## Gestión de reparaciones
[Enlace al GitHub principal]((https://github.com/RubenSanchezAng/Reparacion-de-ordenadores))
[Enlace al GitHub principal] ()
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

##  :bar_chart: Estructura de Java
> [!IMPORTANT]  
> Esto solo es una parte del código del subsitema de gestión de reparaciones
``` java
 abstract class Estimacion {
    protected String descripcion;
    protected double costo;

    public Estimacion(String descripcion, double costo) {
        this.descripcion = descripcion;
        this.costo = costo;
    }

    public abstract String getTipo();

    public String getDescripcion() {
        return descripcion;
    }

    public double getCosto() {
        return costo;
    }
}

```
