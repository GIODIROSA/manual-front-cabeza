# Manual de uso para Front en la agencia CABEZA

###### documentación basada en las buenas prácticas de CODE CLEAN. ROBERT C. MARTIN

###### > Ærlighed i små ting er ikke nogen lille ting --> "La honestidad por las cosas pequeñas no es algo menor"

## Prologo

Manual de uso que busca **_desarrollar normativas en apoyo a la toma de decisiones_** para la creación de infraestructura de software. Normando y estableciendo, metodologías entre sus miembros para la mantención y creación de la misma; en plenitud, el entendimiento de patrones para la integración de cada desarrollador en el equipo. Canalizando, una manera de desarrollo sostenible y documentada.

---

El manual tiene como destino y funcionalidad estar siempre actualizado y reformulado a medida que se presentan experiencias de uso que determinen un patron de diseño a seguir dentro del software. A su vez, este manual tiene características orgánicas e híbridas, para que su relación con la praxis sea lo más fiel a la realidad de productividad. Busca la unificación de criterios y metologías aplicadas para que las fuerzas ejercidas en el remo sea bajo una dirección clara y precisa.

## Preceptos

# ORDEN/ RENDIMIENTO/ OPTIMIZACIÓN/ REFACTORIZACIÓN

---

### Desarrollo de Landing.

`Las landing son estructuras visuales simples en su planteamiento` pero generan complejidades por las composiciones diversas e interacciones que se busca producto del tono de la marca y el cliente. Estableciendo así, verdaderas piezas gráficas interactivas con el usuario que implementan, la atracción perfecta para la conducta y el objetivo que se necesita.

Por ende, se requiere de la creación de un manual y documentación que establezca el patron a seguir dentro del esqueleto adaptativo y objetivo de la optimización y mantención del mismo.

#### Reglas madres:

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

2. Normas de escritura ARCHIVOS/ID/CLASS/VARIABLES:

A) **Nombrar archivos**

```
<!-- numero del día, seguido de un guión medio, nombre declarativo de la actividad -->

03-soloxhoy
10-octubre

```

B) **UPPER_CASE**

```
const UNA_CONSTANTE (caso de JSE6)

id="LANDING-EXAMPLE"

#LANDING-EXAMBLE (caso de style.css)

```

C) **lowerCamelCase**

para nombrar clases: `class`

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

# Implementación de media queries.

principio filosofico para conllevar a la praxis. Mobile first

> ¿Qué hacer si el diseño de desktop se encuentra entregado en la tarea y no se ha desarrollado el mobile?

Para efectos de rapidez y productividad, se establece el desarrollo de desktop dentro de la
sentencia de media queries. Reservando su espacio y bajo la tonica de cascada de CSS. Se encuentre en las primeras lineas de código el mobile y encapsulado en su media querie, el desktop.

> ¿Qué medida de breackpoint se usa para el cambio de adaptabilidad de pantalla de mobile a desktop?

Dentro de los manuales de webmaster del cliente, se ha establecido 768px > hacia adelante se plantea el layout de desktop < a esa medida se concentra mobile.

## Syntax de media queries

Usar bajo todo sentido dicha sentencia para todos los elementos a desarrollar de layout.
Se podrá usar una medida más pequeña particularmente sea el caso de uso que amerite el layout.

```
<!-- ejemplo de encapsulamiento de sentencia de media querie -->

<!-- MOBILE -->

#landing-marketplace .wrapPreguntaUno,
#landing-marketplace .wrapPreguntaTres,
#landing-marketplace .wrapPreguntaDos,
#landing-marketplace .wrapPreguntaCuatro {
  width: 100%;
  background-color: #b2b2b2;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #fff;
}

@media (min-width: 768px) {

<!-- DESKTOP -->

  #landing-marketplace #wrapCarouselMarcas {
    display: block;
  }

  #landing-marketplace #wrapCarouselMarcasMobile {
    display: none;
  }

}

```

### Configuración de layout, estipulado por Ripley.

bloque de código CSS que debe estar enmarcado cada layout que se desarrolle.

```
#LANDING-MARKETPLACE {
    max-width: 1140px;
    margin: auto;
    font-family: "Montserrat", sans-serif;
    box-sizing: border-box;
  }
```

> _Nota_: el total de width y el marco que lo encierra el layout de la landing es de 1140px pero hay elementos internos que van a requerir de un `max-width: 1000px; / max-width: 900px` todo va a depender del diseño de la maqueta.

### Norma de cliente Ripley para el uso de la tipografía general.

CDN- HEAD- HTML:

```
    <link rel="preconnect" href="https://fonts.googleapis.com" />
      <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
      <link
        href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;900&display=swap"
        rel="stylesheet"
      />
```

Uso en style.css

```
    font-family: "Montserrat", sans-serif;
```

### CDN autorizado para el uso de icono.

```
  <link
        rel="stylesheet"
        href="https://pro.fontawesome.com/releases/v5.10.0/css/all.css"
        integrity="sha384-AYmEC3Yw5cVb3ZcuHtOA93w35dYTsvhLPVnYs9eStHfGJvOvKxVfELGroGkvsg+p"
        crossorigin="anonymous"
      />

```

**ADVERTENCIA**: etiquetas HTML que no deben ser usadas. Producto del choque contra la estructura el cliente.

etiqueta HTML o atributo:

1. footer
2. class container
3. main
4. header
5. navbar

> _Nota:_ cualquier etiqueta generica o semántica produce un choque eminente en la estructura del cliente. Solo está permitido `<section></section>` , `<div></div>`; section como elemento mayor y jerarca. div como separador interno de bloques y padre de elemento directo.

### Manera de nombrar class.

Se determinó que los id serán establecidos en **UPPER_CASE** mientras que las clases serán en **lowerCamelCase** pero con la facultad de ser declarativos y preciso para su interpretación. Coincidiendo con su funcionalidad o rol dentro del layout.

ejemplo:

1. parrafoQueEsElMarktplace
2. wrapTextoComorSerParteMarketplace
3. parrafoComoserParteMarketplace

> Código Limpio, determina que el uso de clases declarativas sin importar el largo del mismo potencia su actuar a la hora del mantenimiento del código y de su lectura 6 meses posterior a su realización facilitando su rápida compresión y ubicación de la misma. El nombramiento de las clases, es vital para su rapida localización y actuar en su modificación.

### Etiquetas HTML excepcional

###### uso de imagenes para la flexibilidad y la adaptabilidad en las distintas resoluciones.

**ADVERTENCIA**: atributo importante

````

type="image/webp"

```

```

 <picture>
                <!-- DESKTP -->
                <source
                  media="(min-width: 700px)"
                  type="image/webp"
                  srcset=""
                  alt=""
                />
                <!-- DESKTP -->
                <source
                  media="(min-width: 700px)"
                  srcset="./assets/img/desk/box4.jpg"
                />
                <!-- DESKTP -->
                <source type="image/webp" srcset="" alt="" />
                <!-- MOBILE -->
                <img src="./assets/img/mob/box4-mb.jpg" />
              </picture>

```

### Uso de librería de native JS. carousel SPLITE

revisar documentación de dicha librería

<https://splidejs.com/>

instalación y linkeado de la librería.

> capturar los minificados de la librería.

**HEAD** con el siguiente orden de carga.

```

<link rel="stylesheet" href="./assets/css/style.css" />
      <link rel="stylesheet" href="./assets/css/splide.min.css" />

```

**BODY** ----> SCRIPT

```

  <!-- SPLIDE -->

      <script src="./assets/js/splide.min.js"></script>
      <!-- MAIN JS -->
      <script src="./assets/js/main.js"></script>

```

#### Estructura JS del carousel para la manipulación del carousel

##### Se plantea con una instancia.

> En el html se establece el contenedor _DIV_ que va a contener el id para la activación del carousel

```

new Splide("#carouselMarcas", {
perPage: 5,
breakpoints: {
768: {
perPage: 2,
},
},

rewind: true,
type: "loop",
autoplay: true,
pagination: false,
}).mount();

```

##### Arrow de carousel, para su manipulación por medio de CSS.

se determina la especificidad del mismo.

```

#carouselMarcas .splide\_\_arrow--prev {
left: -3rem;
}

#carouselMarcas .splide\_\_arrow--next {
right: -2rem;
}

```

## No permitido

##### Uso de procesador.

> El énfasis del desarrollo, se establece en el crecimiento como profesional en el dominio ontologico y purista de los elementos que contituyen el origen de cada tecnología. Producto de las diferentes adversidades de la estructura de cliente. Conlleva, a reformarnos y volver a las raices ontologicas del desarrollo. Manejar la triada nos establece la comunión entre los desarrolladores y la unificación del producto a entregar. Ayudando con rapidez y eficacia la especificidad de los elementos al momento del montaje en el marco del cliente y su plataforma.

Se determina que **no se usará un procesador** producto de los elementos de actualización del mismo y de la mantención del código en el tiempo. Establenciendo así, los elementos del lenguaje conocidos como la triada nativa: html/ css/ js. El planteamiento yace, para la unificación de estructura de codificación y establecer los similes entre los programadores para que sea entendible por cada miembro y reducir los tiempos de lectura y comprensión del código.

1. Sass
2. Less
3. Stylus

# SEMÁNTICA

## La importancia en comentar el código.

> La estructura y metodología del código, yace en la semántica utilizada y el orden jerárquico en la ejecución del mismo. Estableciendo en sí, la sincronía de la lectura y carga del mismo en el navegador.

Por ende, es muy importante delimitar las fracciones y section, explicando de una manera corta y declarativa a que conlleva dicho bloque o que guarda dicho fragmento.
La fragmentación de la estructura, es de vital importancia para la segmentación visual y el accionar de correcciones al momento de modificar o re construir section completas. Es decir, construir el layout por section como contenedores de padres supremos; dentro del mismo contenedores que fraccionan la section superior dentro de la jerarquia.

ejemplo:

```

 <!-- CASO DE EXITO -->

        <section id="wrapCasosExito">
          <!-- TITULO HEADER -->
          <div class="wrapTituloCasoExito">
            <h1 id="prueba" class="tituloCasoExito">
              conoce la experiencia de nuestros clientes
            </h1>
          </div>
          <!-- SUPERIOR -->
          <div class="wrapSuperior">
            <div class="unoSuperior">
              <picture>
                <!-- DESKTP -->
                <source
                  media="(min-width: 700px)"
                  type="image/webp"
                  srcset=""
                  alt=""
                />
                <!-- DESKTP -->
                <source
                  media="(min-width: 700px)"
                  srcset="./assets/img/desk/box1.jpg"
                />
                <!-- DESKTP -->
                <source type="image/webp" srcset="" alt="" />
                <!-- MOBILE -->
                <img src="./assets/img/mob/box1-mb.jpg" />
              </picture>
            </div>
            <div class="dosSuperior">
              <picture>
                <!-- DESKTP -->
                <source
                  media="(min-width: 700px)"
                  type="image/webp"
                  srcset=""
                  alt=""
                />
                <!-- DESKTP -->
                <source
                  media="(min-width: 700px)"
                  srcset="./assets/img/desk/box2.jpg"
                />
                <!-- DESKTP -->
                <source type="image/webp" srcset="" alt="" />
                <!-- MOBILE -->
                <img src="./assets/img/mob/box2-mb.jpg" />
              </picture>
            </div>
          </div>
          <!-- INFERIOR -->
          <div class="wrapInferior">
            <div class="unoInferior">
              <picture>
                <!-- DESKTP -->
                <source
                  media="(min-width: 700px)"
                  type="image/webp"
                  srcset=""
                  alt=""
                />
                <!-- DESKTP -->
                <source
                  media="(min-width: 700px)"
                  srcset="./assets/img/desk/box3.jpg"
                />
                <!-- DESKTP -->
                <source type="image/webp" srcset="" alt="" />
                <!-- MOBILE -->
                <img src="./assets/img/mob/box3-mb.jpg" />
              </picture>
            </div>
            <div class="dosInferior">
              <picture>
                <!-- DESKTP -->
                <source
                  media="(min-width: 700px)"
                  type="image/webp"
                  srcset=""
                  alt=""
                />
                <!-- DESKTP -->
                <source
                  media="(min-width: 700px)"
                  srcset="./assets/img/desk/box4.jpg"
                />
                <!-- DESKTP -->
                <source type="image/webp" srcset="" alt="" />
                <!-- MOBILE -->
                <img src="./assets/img/mob/box4-mb.jpg" />
              </picture>
            </div>
          </div>
        </section>
        <!--FINAL CASO DE EXITO -->

```

### En el caso de CSS.

De igual forma comentar el código en cascada CSS con el mismo orden jerarquico que se tiene en el html. Es decir, ser consecuente entre el despliegue secuencia de html sea el mismo orden secuencial y consecuente en css. Lo mismo se aplica en JS.

Dicho orden, determina visualmente una rapidez de conseguir el elemento que este afectando o este determinado por medio de etiquetas.

###### uso de imagenes para la flexibilidad y la adaptabilidad en las distintas resoluciones.

### Implementación de orden de código. (caso JS)

1.  Importación de módulos
2.  Declaración de variables
3.  Declaración de funciones
4.  Ejecución de código

---

### Manipulación del DOM

_ADVERTENCIA_: no usar variable de corte global como _var_ sino la convención local,
const: cuando sea una constante el valor y no va a cambiar. Let: si va ser un dato a guardar que tienen a mutar en el flujo del desarrollo de la aplicación.

1.  Las variable _Let_ por convención, se le establece el signo $ al principio de dicho nombre de variable, como norma para determinar que dicha variable guarda elementos del DOM, distinta de otras variable dentro de la aplicación:

```

<!-- variable let que guarda un elemento del DOM -->

let $btnVerMas= document.getElemenetById("VER-MAS");

<!-- variable let que NO guarda un elemento del DOM -->

let cantidad= 23;

```

2. Usar _UPPER CASE_

```

const VALOR-PI= 3,1416;

```

---

## MAILING

###### desarrollo rutinario de la celula de ripley.com

Los mailing son estructuras desarrolladas en bases de plantillas traspiladas en webpack para tener una estructura mas rápida. Estableciendo así, un objeto JS que inyecta imagen y url absolutas al html. Enviando a producción y proyectandose el armado secuencial del mailing.
Aspecto a resaltar **_debe ser enviado a testeo como elemento fundamental de entrega al proveedor_**

> PRIMERA PARTE

Los mailing, como lo descrito anteriormente, se construyen por medio de un JS llamado items, que por medio de un array de objeto, inyecta la imagen previamente cortada y una URl.

> _ADVERTENCIA_: los link de objetos que no han sido señalados ni instruidos desde la tarea, siempre deben llevar al _home_, en dado caso, no dan una instrucción distinta. Por _default_ siempre al home.

> Existen dos elementos un objeto y un array, sirven dependendiendo de la propuesta gráfica.

#### Objecto Simple

Es usado cuando hay una sola section cortada en la maqueta y te conduce a una sola url.
Es decir, una imagen, una URL.

```

{
photo: require("../img/images/03-blandosgenericos_01.jpg"),
link: "https://simple.ripley.cl/",
},

```

#### Array dual o bloque

Es usado cuando en una sola section existe dos imagenes antagonicas y a su vez las URL tambien tiene dicha caracteristica contraria.

```

{
block: [
{
photo: require("../img/images/04-ultimosdias2-vertical6_01.jpg"),
link: "https://simple.ripley.cl/otras-categorias/servicios-y-gift-card/tiempo-libre",
},
{
photo: require("../img/images/04-ultimosdias2-vertical6_02.jpg"),
link: "https://simple.ripley.cl/supermercado/despensa",
},
],
},

```

#### Array triple o bloque

Caso excepcional y rara vez sucede.
_ADVERTENCIA_ solicitar al diseñador que esta section sea cortada de manera equitativa en tres partes para el armado.

> Verificar en el html final en producción que cada width contenga el 33%. Esto se evidencia debido a la división del 100% de la imagen en tres partes iguales.

```

{
block: [
{
photo: require("../img/images/04-ultimosdias2-vertical6_01.jpg"),
link: "https://simple.ripley.cl/otras-categorias/servicios-y-gift-card/tiempo-libre",
},
{
photo: require("../img/images/04-ultimosdias2-vertical6_02.jpg"),
link: "https://simple.ripley.cl/supermercado/despensa",
},

        {
          photo: require("../img/images/04-ultimosdias2-vertical6_03.jpg"),
          link: "https://simple.ripley.cl/supermercado/despensa",
        },
      ],
    },

```

#### Banner promocional de banco ripley o eventualidad puntual

Este banner, se localiza en el footer del mailing. Determinando unas URL adicionales que siempre van. Pero tienen la características de ser modificado cada mes.

```

{
photo: require("../img/banners/cyber2.jpg"),
link: "https://www.bancoripley.cl/solicitar-tarjeta-online?utm_source=ripley-com&utm_medium=mail_footer&utm_campaign=captacion_jun21",
},

```

> SEGUNDA PARTE

Si los elementos legales, son muy extensos al final del mailing, se debe justificar sino centralizar. Se plantea o modifica directo al HTML que es traspilado en la carpeta _dist_ una vez que se mande a producción.

Ejemplo de vigencia + legal que contiene una extensión super a la normal. Se establece tambien la doble etiqueta _<br>_
para enfatizar el orden visual y la separación entre parrafos.

```

<td align="justify">
                                <span style="text-align:center;font-family:Arial, Helvetica, sans-serif; font-size:11px; color:#575757; margin:0; padding:0; font-weight:normal;">
                                  Precios disponibles en Ripley.com hasta el 06 de octubre de 2021 o hasta agotar stock. Precios Internet publicados incluyen descuento adicional. Productos sujetos a disponibilidad de stock al momento de la compra. No acumulable con otras promociones. Despacho de producto se realizará una vez confirmada la compra. *Dcto. ya aplicado a precio Internet | **Sólo productos seleccionados. <br><br>Contratación de Tarjeta de Crédito Ripley Mastercard sujeta a evaluación de antecedentes del cliente. Promoción válida para personas que contraten su Tarjeta de Crédito Ripley Mastercard entre el 27/09/2021 y 06/10/2021. Cupón de descuento de $20.000 será cargado al día hábil siguiente a la contratación en la app Banco Ripley, utilizable hasta el 31/11/2021 pagando con Tarjeta Ripley o Tarjeta Ripley Mastercard en compras sobre $40.000. Exclusivo para captaciones online. No es acumulable con otros cupones y no aplica en despacho ni compras en Mercado Ripley. Entrega de cupón, descuentos en Ripley son de responsabilidad de Comercial Eccsa S.A. Oportunidades exclusivas en tiendas Ripley y <a href="http://ripley.com/">ripley.com</a> y la administración del programa Ripley Puntos Go y la entrega de sus beneficios son de responsabilidad de Comercial Eccsa S.A. Términos y condiciones del programa Ripley Puntos Go en www.ripleypuntosgo.com. Restaurantes adheridos y condiciones del programa Restofans disponibles en pestaña “Beneficios / Restofans” de bancoripley.com. Tarjetas Ripley son emitidas por CAR S.A., sociedad de apoyo al giro y filial de Banco Ripley. Infórmese sobre la garantía estatal de los depósitos en su banco o en <a href="www.cmfchile.cl">www.cmfchile.cl</a>  <br><br>  Acumulan doble Ripley Puntos Go las compras en tiendas Ripley y Ripley.com realizadas con Tarjeta Ripley MasterCard y Debito Banco Ripley entre el 01/10/2021 y el 06/10/2021. Máximo 5.000 Ripley Puntos Go extra por cliente. Participan en la promoción sólo los clientes inscritos. Tope de 10.000 inscritos por campaña. Abono de Ripley Puntos Go promocionales se realizará durante el mes siguiente al pago. La administración del Programa Ripley Puntos Go y entrega de sus beneficios es de exclusiva responsabilidad de Comercial ECCSA S.A. Términos y condiciones del Programa en www.ripleypuntosgo.com. Tarjetas de Crédito Ripley son emitidas por CAR S.A., sociedad de apoyo al giro y filial de Banco Ripley. Infórmese sobre la garantía estatal de los depósitos en su banco o en www.cmfchile.cl.
                                </span>
                              </td>
```

> TERCERA PARTE
> Mailing informativos.

Son elementos informativos de rápida construcción, donde se establece, un mensaje directo y preciso. Para efectos de armado, se debe establecer su estructura y corte adecuado al diseño, se manda a producción y directamente en el html final, se plantea el comentar las fracciones que no se deben proyectar, tal es el caso:

Aspectos a considerar:

1. title: se mantiene.
2. marker: se mantiene.
3. legal: se comenta.
4. barilliance: false.
5. puntos: false.

Ejemplo:

```
var general = {
  title: "Blandos Genérico", // aplica en todo momento (nombre de la tarea)
  marker: "mail_r_blando1_cyber_s40_20211005_rc", (marcaje importante)
  source: "email", // no modificar
  medium: "mailing_rc", // no modificar
  legal:
    "Precios disponibles ...", // se comenta la vigencia y el legal
  barilliance: true, // se coloca en false
  puntos: true, // se coloca en false
};
module.exports = general;

```

## MAILING CON CAMPO VARIABLE

###### Estructuras variante y dependiendo de la instrucción del Product Manager.

Consiste en desarrollar e inyectar un campo variable para que se determine diferentes aspectos dinámicos al layout en la visual del usuario. Dicho elemento, se arma con imagenes cortadas dadas por el diseñador e implementadas por el front, contemplando y tomando en cuenta la salvedad, desde el html, se arma la fracción que conllevará el campo variable.

> ¡Una excepción!: se estipula la etiqueta style y su cierre en el head antes del body para afectar directamente al html, producto que dicho elemento ya paso por la traspilación y se encuentra en calidad de producción. Por ese aspecto y solo por ese motivo, se permite la flexibilidad de las buenas practicas en el uso de style dentro del archivo html.

## IC DINÁMICA- CIRCULAR- TARJETA

###### Estructuras diversas en su composición que van desde botoneras que conllevan a enrutamientos absolutos, como también, carousel circular y en forma de tarjetas.

Normalmente, dichas piezas van en las cabeceras de las landing y de diferentes mundos del ecosistema de Ripley.com

Existen varios elementos a considerar entre las IC dinámicas mas antiguas, se describe como una botonera flexible y adaptable a mobile y muchas veces lleva banner que dependiendo del boton van cambiando dicho elemento.

Ejemplo:

Descripción del array de objetos.

1. category: nombre que se inyectará en el html al boton.
2. url: url dada por el Product manager.
3. banners: objeto que inyecta el banner para desktop y para mobile

```
const imageDesktop = "../images/1.jpg";
const imageMobile = "../images/1-mb.jpg";

const data = [
  {
    category: "vestuario deportivo",
    url: "https://simple.ripley.cl/deporte/ropa-deportiva/ropa-deportiva",
    banners: {
      desktop: "../images/ic-dinamica-vestuario-deportivo-desk_.jpg",
      mobile: "../images/ic-dinamica-vestuario-deportivo-mob.jpg",
    },
  },

]
```

### Elemento de SASS (búsqueda de reforma de las estructuras actuales para la refactorización)

#### Se modifica para los aspectos gráficos y cromáticos de la ic dinámica.

Espeficaciones determinadas en la tarea.

```
$caja-on: #363636;
$caja-off: #ea4c61;
$texto-on: #fff;
$texto-off: #fff;
$borde: #000;
$border-opacity: 0.1;

```

#### Hacer _build_ ejecuta la construcción del array de objeto.

> Entregando en producción diferentes html que posterior seran ensamblados por Webmaster en Ripley.com

## IC DINÁMICA CIRCULAR

Se plantea como elemento carousel, determinando en pantalla la cantidad de items entregado por el diseñador en el boceto aprobado por PM. La manera de la entrega del mismo, son imagenes sueltas por medio de un zip, facilitadas por el diseñador. Para ser implementadas.

La implementación según Webmaster tiene una normativa en su configuración

> _Alerta_: la estructura debe cambiar en la brevedad por ser desarrollada con un carousel de caracteristicas arcaicas y tiene un mantenimiento nulo.

Esta estructura contiene un cintillo que será comentado o descomentado dependiendo del requerimiento establecido y la aprobación de boceto de diseño y PM.

## ¡ADVERTENCIA!

> Recordar que el primer elemento se debe especificar en su clase para la activación del css la clase **active**

> Si en el caso contrario se quiere desactivar eventualidades de hover a un elemento o items particular. Se estipula en inline el atributo `pointer-events: none;` a la etiqueta señalada para que elimine el evento y quede desactivado.

### Considerar:

> eliminar el atributo _with: auto_ para que el cintillo quede centrado.
> copiar fragmento de código refactorizado

```
 <!-- espacio CINTILLO PUBLICITARIO -->
  <a href="#" class="cintillo-icnueva">
    <picture>
      <source
        media="(min-width:1000px)"
        srcset="assets/img/Cintillo-desk.jpg"
      />
      <img src="assets/img/Cintillo-mob.jpg" alt="cintillo infantil" />
    </picture>
  </a>
  <!--FIN -->

```

#### Estructura en HTML de la IC circular.

```

 <div id="ic-container">
    <div class="iccarousel-nueva owl-carousel owl-theme">
      <a
        href="https://simple.ripley.cl/deporte-y-aventura/camping-y-tiempo-libre/carpas-y-sacos?icd-camping-carpas-sacos"
        class="item active"
      >
        <img src="assets/img/carpa.png" alt="carpas y sacos" />
        <h2>carpas y sacos</h2>
      </a>

```

#### Configuración a considerar dependiendo de los items entregados.

## 1. Menor a 5.

```
$("#ic-container .iccarousel-nueva").owlCarousel({
  loop: false,
  autoplay: true,
  nav: true,
  navText: [
    "<div class='nav-btn prev-slide'></div>",
    "<div class='nav-btn next-slide'></div>",
  ],
  items: 5,
  responsive: {
    0: {
      items: 2,
    },
    500: {
      items: 3,
    },
    750: {
      items: 3,
    },
    1000: {
      items: 4,
    },
  },
});

```

## 2. _Mayor a 5_.

```
$("#ic-container .iccarousel-nueva").owlCarousel({
  loop: false,
  autoplay: true,
  nav: true,
  navText: [
    "<div class='nav-btn prev-slide'></div>",
    "<div class='nav-btn next-slide'></div>",
  ],
  items: 5,
  responsive: {
    0: {
      items: 2,
    },
    500: {
      items: 3,
    },
    750: {
      items: 4,
    },
    1000: {
      items: 5,
    },
  },
});

```

#### Configuración CSS.

> Se determinó con webmaster esta depuración del 80% en el width para cuando se monte en el marco de ripley quede adecuado y no se encoja.

```
#ic-container {
  position: relative;
  width: 80%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  max-width: 1280px;
  margin: 0 auto;
  /*padding: 10px 0;*/
  margin-bottom: -30px;
}

```

---

## IC DINÁMICA TARJETA

> Se aplica la misma determinación de IC DINÁMICA CIRCULA. Solo cambia, el elemento visual de forma.

Recordar que el primer elemento se debe especificar en su clase para la activación del css la clase **active**

Si en el caso contrario se quiere desactivar eventualidades de hover a un elemento o items particular. Se estipula en inline (html) el atributo `pointer-events: none;` a la etiqueta señalada para que elimine el evento y quede desactivado.

> Se presenta las mismas características semanticas de armado de la ic dinámica tarjeta.

1. HTML

```
 <div class="iccarousel-nueva owl-carousel owl-theme">
      <a
        href="https://simple.ripley.cl/moda-y-accesorios/marcas-hombre/tennis"
        class="item active"
      >
        <img src="assets/img/pantalonhombre1.jpg" alt="hombre" />
        <h2>hombre</h2>
      </a>

```

2. RUN JS

```
$("#ic-container .iccarousel-nueva").owlCarousel({
  loop: false,
  autoplay: true,
  nav: true,
  navText: [
    "<div class='nav-btn prev-slide'></div>",
    "<div class='nav-btn next-slide'></div>",
  ],
  items: 5,
  responsive: {
    0: {
      items: 2,
    },
    500: {
      items: 2,
    },
    750: {
      items: 2,
    },
    1000: {
      items: 4,
    },
  },
});

```

3. CSS Contiene un 100% de with

```
#ic-container {
  position: relative;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  max-width: 1280px;
  margin: 0 auto;
  /*padding: 10px 0;*/
  margin-bottom: -30px;
}

```

## ¡ADVERTENCIA!

Dichas estructuras deben ser siempre revisadas y refactorizadas en el tiempo para su mantención, el uso de librerías o de factores de código ya construido y aplicado determina una fiel atención para una modernización o evaluación de sus componente sigan estando vigente.

> La recomendación, establecer siempre los ambitos nativo a medida que vayan siendo aceptados por los navegadores y puesto en practicas por las diferentes versiones de mejoras en la codificación.

# Creación de biblioteca de front.
````
