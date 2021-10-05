# Manual de uso para Front en la agencia CABEZA

###### documentación basada en las buenas prácticas de CODE CLEAN. ROBERT C. MARTIN

###### > Ærlighed i små ting er ikke nogen lille ting --> "La honestidad por las cosas pequeñas no es algo menor"

## Prologo

Manual de uso que busca **_desarrollar normativas en apoyo a la toma de decisiones_** para la creación de infractura de software. Normando y estableciendo, metodologías entre sus miembros para la mantención y creación de la misma; en plenitud, el entendimiento de patrones para la integración de cada desarrollador en el equipo. Canalizando, una manera de desarrollo sostenible y documentada.

---

### Desarrollo de Landing.

'''Las landing son estructuras visuales simples en su planteamiento''' pero generan complejidades por las composiciones diversas e interacciones que se busca producto del tono de la marca y el cliente. Estableciendo así, verdaderas piezas gráficas interactivas con el usuario que implementan, la atracción perfecta para la conducta y el objetivo que se necesita.

Por ende, se requiere de la creación de un manual y documentación que establezca el patron a seguir dentro del esqueleto adaptativo y objetivo de la optimización y mantención del mismo.

#### Reglas:

1. Etiquetas **MADRES**:

ejemplo: etiquetas ** envolventes (wrap) ** otorgadas por Ripley para el reconocimiento en la plataforma.

_HEAD_

```
<mini-site-styles>

<meta charset="UTF-8" />
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Landing Marketplace</title>

</mini-site-styles>
```

_BODY_

```
<mini-site>

<!-- div envolvente para lograr la especificidad de las etiquetas en style.css -->

<div id="landing-example">
<!-- CONTENIDO -->
</div>

<!-- final de div  -->

</mini-site>
```

_SCRIPT_

```
<mini-site-scripts>

<!-- enlace con carousel libreria min-->
<script src="./assets/js/splide.min.js"></script>

<!-- enlace con JS -->
<script src="./assets/js/main.js"></script>

</mini-site-scripts>
```

---

2. Convención de escritura ARCHIVOS/ID/CLASS/VARIABLES:

A) **SNAKE CASE**

```
mi_archivo_javascript.js

<!-- alternativa diversa a snake case para caso de archivos/carpetas -->

03-soloxhoy
10-octubre

```

B) **UPPER_CASE**

```
const UNA_CONSTANTE (caso de JSE6)

id="LANDING-EXAMPLE"

#LANDING-EXAMBLE (caso de style.css)

```

C) **UpperCamelCase**

alternativa para nombrar `class`

```
class="WrapTextoMarketplace"

```

D) **lowerCamelCase**

alternativa para nombrar `class`

```
class="wrapTextoMarketplace"

```

elementos primitivos.

1.  let
2.  const
3.  boolean
4.  numero

function (funciones)

```
function exampleFunction (name){
    return
}

```

---

### Implementación de orden de código. (caso JS)

1.  Importación de módulos
2.  Declaración de variables
3.  Declaración de funciones
4.  Ejecución de código

---

## MAILING

###### desarrollo rutinario de la celula de ripley.com

Los mailing son estructuras desarrolladas en bases de plantillas traspiladas en webpack para tener una estructura mas rápida. Estableciendo así, un objeto JS que inyecta imagen y url absolutas al html. Enviando a producción y proyectandose el armado secuencial del mailing.
Aspecto a resaltar **_debe ser enviado a testeo como elemento fundamental de entrega al proveedor_**

> _¡Aspectos a considerar!_

Los mailing, como lo descrito anteriormente, se construyen por medio de un JS llamado items, que por medio de un array de objeto, inyecta la imagen previamente cortada y una URl.

```
{
photo: require("../img/images/03-blandosgenericos_01.jpg"),
link: "https://simple.ripley.cl/",
},


```
