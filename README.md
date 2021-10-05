# Manual de uso para Front en la agencia CABEZA

###### documentación basada en las buenas prácticas de CODE CLEAN. ROBERT C. MARTIN

###### > Ærlighed i små ting er ikke nogen lille ting --> "La honestidad por las cosas pequeñas no es algo menor"

## Prologo

Manual de uso que busca **_desarrollar normativas en apoyo a la toma de decisiones_** para la creación de infraestructura de software. Normando y estableciendo, metodologías entre sus miembros para la mantención y creación de la misma; en plenitud, el entendimiento de patrones para la integración de cada desarrollador en el equipo. Canalizando, una manera de desarrollo sostenible y documentada.

---

### Desarrollo de Landing.

`Las landing son estructuras visuales simples en su planteamiento` pero generan complejidades por las composiciones diversas e interacciones que se busca producto del tono de la marca y el cliente. Estableciendo así, verdaderas piezas gráficas interactivas con el usuario que implementan, la atracción perfecta para la conducta y el objetivo que se necesita.

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

### Implementación de media queries.

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

> _¡Aspectos a considerar!_ PRIMERA PARTE

Los mailing, como lo descrito anteriormente, se construyen por medio de un JS llamado items, que por medio de un array de objeto, inyecta la imagen previamente cortada y una URl.

> _ADVERTENCIA_: los link de objetos que no han sido señalados ni instruidos desde la tarea, siempre deben llevar al _home_, en dado caso, no dan una instrucción distinta. Por _default_ siempre al home.

```
{
photo: require("../img/images/03-blandosgenericos_01.jpg"),
link: "https://simple.ripley.cl/",
},

```

> _¡Aspectos a considerar!_ SEGUNDA PARTE

Si los elementos legales son muy extensos al final del mailing, se debe justificar sino centralizar. Se plantea o modifica directo al HTML que es traspilado en la carpeta _dist_ una vez que se mande a producción.

Ejemplo de vigencia + legal que contiene una extensión super a la normal. Se establece tambien la doble etiqueta _<br>_
para enfatizar el orden visual y la separación entre parrafos.

```
<td align="justify">
                                <span style="text-align:center;font-family:Arial, Helvetica, sans-serif; font-size:11px; color:#575757; margin:0; padding:0; font-weight:normal;">
                                  Precios disponibles en Ripley.com hasta el 06 de octubre de 2021 o hasta agotar stock. Precios Internet publicados incluyen descuento adicional. Productos sujetos a disponibilidad de stock al momento de la compra. No acumulable con otras promociones. Despacho de producto se realizará una vez confirmada la compra. *Dcto. ya aplicado a precio Internet | **Sólo productos seleccionados. <br><br>Contratación de Tarjeta de Crédito Ripley Mastercard sujeta a evaluación de antecedentes del cliente. Promoción válida para personas que contraten su Tarjeta de Crédito Ripley Mastercard entre el 27/09/2021 y 06/10/2021. Cupón de descuento de $20.000 será cargado al día hábil siguiente a la contratación en la app Banco Ripley, utilizable hasta el 31/11/2021 pagando con Tarjeta Ripley o Tarjeta Ripley Mastercard en compras sobre $40.000. Exclusivo para captaciones online. No es acumulable con otros cupones y no aplica en despacho ni compras en Mercado Ripley. Entrega de cupón, descuentos en Ripley son de responsabilidad de Comercial Eccsa S.A. Oportunidades exclusivas en tiendas Ripley y <a href="http://ripley.com/">ripley.com</a> y la administración del programa Ripley Puntos Go y la entrega de sus beneficios son de responsabilidad de Comercial Eccsa S.A. Términos y condiciones del programa Ripley Puntos Go en www.ripleypuntosgo.com. Restaurantes adheridos y condiciones del programa Restofans disponibles en pestaña “Beneficios / Restofans” de bancoripley.com. Tarjetas Ripley son emitidas por CAR S.A., sociedad de apoyo al giro y filial de Banco Ripley. Infórmese sobre la garantía estatal de los depósitos en su banco o en <a href="www.cmfchile.cl">www.cmfchile.cl</a>  <br><br>  Acumulan doble Ripley Puntos Go las compras en tiendas Ripley y Ripley.com realizadas con Tarjeta Ripley MasterCard y Debito Banco Ripley entre el 01/10/2021 y el 06/10/2021. Máximo 5.000 Ripley Puntos Go extra por cliente. Participan en la promoción sólo los clientes inscritos. Tope de 10.000 inscritos por campaña. Abono de Ripley Puntos Go promocionales se realizará durante el mes siguiente al pago. La administración del Programa Ripley Puntos Go y entrega de sus beneficios es de exclusiva responsabilidad de Comercial ECCSA S.A. Términos y condiciones del Programa en www.ripleypuntosgo.com. Tarjetas de Crédito Ripley son emitidas por CAR S.A., sociedad de apoyo al giro y filial de Banco Ripley. Infórmese sobre la garantía estatal de los depósitos en su banco o en www.cmfchile.cl.
                                </span>
                              </td>
```

> _¡Aspectos a considerar!_ TERCERA PARTE

Si los elementos legales son muy extensos al final del mailing, se debe justificar sino centralizar. Se plantea o modifica directo al HTML que es traspilado en la carpeta _dist_ una vez que se mande a producción.

Ejemplo de vigencia + legal que contiene una extensión super a la normal. Se establece tambien la doble etiqueta _<br>_
para enfatizar el orden visual y la separación entre parrafos.
