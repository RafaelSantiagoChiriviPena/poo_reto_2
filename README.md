# poo_reto_2
### Soy Rafael Santiago Chirivi Peña y pertenezco al grupo de "Fenomenoides", adelante se muestra nuestro logo 

<details><summary>Preparense para ver el grandioso logo: </summary><p>
<div align='center'>
<figure> <img src="https://i.postimg.cc/NFbwf57S/logo-def.png" alt="Defensa Civil" width="400" height="auto"/></br>
<figcaption><b> "somos programadores, no diseñadores" </b></figcaption></figure>
</div>
</p></details><br>

Dando inicio al desarrollo de la materia, el primer acercamiento al tema fue el modelado en clases y objetos para una situacion de nuestra elección

## Caso de estudio: Zoologico
A partir de este caso, fueron modelados los siguientes diagramas de UML

### Relacion Zoologico - cliente
```mermaid
classDiagram
Cliente --> Zoologico : pagar_entrada(edad, numero_de_acompañantes)

class Zoologico{
    + ubicación : str
    + capacidad : int
    + precio_de_entrada : float
    + apertura(tiempo)
    + cierre(tiempo)
}

class Cliente{
    + edad
    + numero_de_acompañantes
}
```
### Relacion Zoologico - Componentes
```mermaid
classDiagram
Animales --* Jaulas
Jaulas --* Zoologico
Atracciones --* Zoologico
Personal --* Zoologico

class Zoologico{
    + ubicación : str
    + capacidad : int
    + precio_de_entrada : float
    + apertura(tiempo)
    + cierre(tiempo)
}

class Animales{
    + clasificacion : str
    + peso : float
    + cantidad : int
    + altura : float
    + longitud : float
    + envejecer(tiempo)
}

class Jaulas{
    + estado_abierto/cerrado : bool
}

class Atracciones{
    + precio : float
    + tiempo_de_estancia : float
    + tiempo_de_espera : float
}

class Personal{
    + uniforme : str
    + cargo : str
    + contrato : str
    + jornada : str
    + salario(cargo)
    + actividades(cargo) 
}
```

### Relacion entre personal
```mermaid
classDiagram
Seguridad --|> Personal
Cuidadores --|> Personal
Operarios --|> Personal
Guias_turisticos --|> Personal

class Seguridad{
    + acceso_total : bool
}

class Cuidadores{
    + kit_de_salud_animal : list
}

class Operarios{
    + equipo_de_herramientas : list
}

class Guias_turisticos{
    + ruta : str
}

class Personal{
    + uniforme : str
    + cargo : str
    + contrato : str
    + jornada : str
    + salario(cargo)
    + actividades(cargo) 
}
```

### Relacion personal - zoologico 
```mermaid
classDiagram
Seguridad --> Zoologico : vigilar(jornada)
Cuidadores --> Jaulas : cuidar_jaulas(jornada)
Operarios --> Atracciones : atender_atracciones(jornada)
Guias_turisticos --> Zoologico : guiar_visitantes(jornada)

class Zoologico{
    + ubicación : str
    + capacidad : int
    + precio_de_entrada : float
    + apertura(tiempo)
    + cierre(tiempo)
}

class Jaulas{
    + estado_abierto/cerrado : bool
}

class Atracciones{
    + precio : float
    + tiempo_de_estancia : float
    + tiempo_de_espera : float
}

class Seguridad{
    + acceso_total : bool
}

class Cuidadores{
    + kit_de_salud_animal : list
}

class Operarios{
    + equipo_de_herramientas : list
}

class Guias_turisticos{
    + ruta : str
}
```
###
