# Solemne-II


# Habitando lo ajeno

### Proyecto realizado en p5.js

---

## Información del proyecto

-  **Nombre del proyecto:**  *Habitando lo ajeno*  
-  **Autor/a:** Ayelen Vásquez Navea See More  

---

## Descripción objetivo

* Habitando lo ajeno * es una pieza interactiva desarrollada en **p5.js** basada en la problemática de la disforia de género.  

La obra muestra en pantalla la imagen de una persona sin rostro definido y con una expresión corporal que transmite desesperación, tensión e incomodidad. La figura principal ocupa el centro del lienzo y representa el conflicto interno relacionado con la identidad y el cuerpo.  

A través de la interacción del usuario, una misma figura puntiaguda de color azul comienza a repetirse e invadir el espacio visual desde los bordes del boceto hacia el centro. Esta figura fue programada para repetirse 60 veces dentro del sistema, generando una sensación de presión, ansiedad y saturación visual.  

Además, aparecen palabras relacionadas con la disforia, como:


- “de conexión”
- “ansiedad”
- “rechazo”
- “encierro”
- “¿quién soy?”
- “disonancia”

También se agregaron líneas fragmentadas y formas transparentes para representar quiebres emocionales y fragmentación de identidad.

---

## Descripción conceptual

La idea principal del proyecto fue representar e intentar visualmente la sensación de incomodidad, desesperación y desconexión que puede provocar la disforia de género.  

La imagen central busca transmitir la sensación de habitar un cuerpo ajeno, mientras que las figuras invasivas representan pensamientos, presión emocional y ansiedad constante.  

La interacción del usuario es importante dentro de la obra, ya que al mantener presionado el mouse las figuras avanzan hacia el centro del lienzo, generando más tensión visual y una sensación de invasión sobre la imagen principal.  

Cuando el usuario deja de presionar el mouse, las figuras regresan hacia sus posiciones iniciales, pero nunca desaparecen por completo, representando una tensión que sigue existiendo.

### Regla principal del sistema

> Mientras más tiempo el usuario mantiene presionado el mouse, mayor es la invasión visual de las figuras sobre la imagen principal.
---

## Relación con la problemática de género

La lógica interactiva del proyecto se relaciona con la disforia de género porque busca transformar emociones internas en una experiencia visual.  

Las figuras puntiagudas representan pensamientos invasivos, ansiedad, incomodidad corporal y presión social. La ausencia de rostro en la imagen principal simboliza la pérdida de identidad y la dificultad de reconocerse dentro del propio cuerpo.  

Las líneas fragmentadas ayudan a reforzar la idea de ruptura emocional y desconexión interna.

La obra no busca representar literalmente la disforia, sino transmitir una sensación emocional relacionada con ella mediante movimiento, tensión visual e interacción.

---

## Entrada / Salida y sistema

### APORTE

Los datos de entrada utilizados en el sistema fueron:

- Posición del mouse ( ` mouseX ` , ` mouseY ` )
- Haga clic en el ratón ( ` mouseIsPressed ` )
- Valores aleatorios utilizando ` random() `

---

### PROCESO

El sistema procesa la información mediante:

- Condicionales ( ` if ` , ` else ` )
- Bucles ` for `
- Variables de posición y movimiento.
- Transformaciones como:
  -  ` translate() `
  -  ` rotar() `
  -  ` escala() `
- Transparencias con ` tint() `
- Uso de ` map() ` para modificar algunos valores visuales

Las figuras fueron programadas para aparecer desde los bordes y acercarse lentamente al centro cuando el usuario interactúa.

---

### PRODUCCIÓN

El resultado visual es una composición interactiva donde:

- Las figuras invaden el lienzo.
- Las palabras aparecen alrededor de la imagen.
- Las líneas fragmentan visualmente el espacio.
- Las figuras se mueven constantemente generando tensión.

Todo esto crea una experiencia visual relacionada con ansiedad, presión e incomodidad emocional.

---

## Pensamiento computacional

El proyecto fue construido a partir de reglas simples que, al combinarse, generan un sistema visual más complejo.  

Las principales reglas del sistema son:

- Las figuras nacen desde posiciones aleatorias.
- Cada figura posee distinto tamaño, rotación y velocidad.
- Al presionar el mouse las figuras avanzan
- Al soltar el mouse las figuras retroceden
- El movimiento aleatorio genera una sensación nerviosa.
- Las palabras aparecen cuando el usuario entra al sketch.

La interacción permite que el usuario modifique el comportamiento visual en tiempo real, haciendo que la obra no sea estática.

---

## Referentes

### Referentes visuales

- Fotografía corporal expresionista  
  Utilizada para transmitir desesperación, tensión y conflicto corporal.

- Estética de fragmentación  
  Inspirada en imágenes rotas, glitch y quiebres visuales para representar la desconexión emocional.

- Arte digital minimalista  
  Uso de transparencias, líneas y formas simples para crear tensión visual sin saturar la composición.

---

### Referentes conceptuales

- Disforia de género  
  Como problema principal del proyecto.

- Fragmentación de identidad  
  Representada mediante líneas, figuras invasivas y división del espacio visual.

- Interactividad emocional  
  La interacción del usuario modifica la intensidad visual de la obra y ayuda a transmitir emocionalmente el concepto.

---

# DIAGRAMA DE FLUJO

[DIAGRAMA DE FLUJO.pdf](https://github.com/user-attachments/files/28234455/DIAGRAMA.DE.FLUJO.pdf)

# CÓDIGO DE P5.JS
```markdown
// SOLEMNE II
// DISFORIA DE GÉNERO
// "HABITANDO LO AJENO" BY AYELEN


// VARIABLES //

// IMÁGENES //
// Acá defino las variables que utilizaré para las respectivas imágenes que pondré en el sketch.
let imgPerson;
// Variable donde se guardará la imagen: signo de interrogación
// reemplazar el mouse normal
let signoIntcursor;


// PARA LAS FIGURAS QUE IRÁN INVADIENDO EL SKETCH //
let figura;

//PARA LAS FIGURAS QUE INVADEN
let formas = []; // Creo un array vacío 
let cantidad = 60; // DEFINO EL TOTAL DE LAS FIGURAS 


//CLICK MOUSE// FRASES
let activar = false; // Activamos las variables para integrar el mouse como interacción
let frases = [

  "desconexión",
  "ansiedad",
  "rechazo",
  "encierro",
  "¿quién soy?",
  "disonancia"

];


// PRELOAD //
// IMÁGENES SUBIDAS //
function preload () {
  
  imgPerson = loadImage("ImagenPerson.png"); // Dejamos las imágenes cargadas en Sketch Files, para después ingresarlas por acá
  figura = loadImage("ImaEstrella.png");
  signoIntcursor = loadImage ("signoInt.png");
}


// SETUP //
// DECLARAMOS NUESTRAS CONDICIONES
function setup() {
  createCanvas(700, 700); // Tamaño del lienzo en pixeles 
  
  textAlign(CENTER); // Texto al centro
  rectMode(CENTER);
   
   noCursor(); // oculta el cursor del sistema

  
  //FUNCIÓN PARA CREAR VARIAS DE ESTA FIGURA
  // FOR 
  // este loop repite algo muchas veces, por ende declaramos esta automatización para crear 60 figuras
  
  for(let i = 0; i < cantidad; i=i+1){ // Definimos nuestra variable con el nombre i, variable que funcionará como contador y que partirá desde cero. Luego le decimos al programa que i se siga repitiendo mientras i sea menor que la variable cantidad que definimos como 60. Por último, le decimos al For que esta variable i se vaya reptiendo, hasta llegar a las 60 figuras, por eso la suma de la misma.

    
    let lado = floor(random(4)); // Acá definimos otra variable para poder decirle al programa desde donde aparecerán las figuras. Por ende definimos "lado" como tal y el código random que hará que aparezcan de un número entre el 1-4, que representan las cuatro esquinas del sketch. Floor como tal es para definir que este número del 1 a 4 no sean decimales. "Floor" como tal lo saque de la IA porque no sabía y no entendía como hacer que la variable apareciera alrededor y no solo en un lado.
    
    let x; // Aca creamos dos variables más que definirán las posiciones de las figuras que se activen por el For
    let y;

    
    // DECLARAMOS NUESTRAS CONDICIONALES//
    // aquí estoy usando condicionales, para decidir desde qué lado        aparecerá cada figura
    // la variable "lado"
    // tiene un número random: 0, 1, 2 o 3
    // dependiendo del número, cambia la posición de la figura.

    if(lado == 0){ // Si nuestro lado es 0 
      x = random(width); // width es el ancho del sketch
       // random(width) genera una posición horizontal random
      y = -0; // significa la parte superior del canvas, de arriba
  
    }
    
    else if(lado == 1){ // Si nuestro lado es 1
      x = width; // Define la posición horizontal.
      y = random(height); // Genera una posición vertical random.
    }
    
    else if(lado == 2){ // Si el lado vale 2
      x = random(width); // Hace que la figura aparezca en cualquier posición horizontal.
      y = height; // Define la posición vertical.
    }

    else{ // Si no pasa ninguna condición anterior, entonces automaticamente será 3
      x = -0; // para que aparezcan de la izquierda, por eso el -
      y = random(height); // Cualquier posición vertical
      //Todo esto sirve para que las figuras parezcan invadir el sketch desde distintos bordes y no desde un solo lugar.
      //Yo acá, según teng entendido puede ser If, pero para ccumplir con los requerimientos de lo que pidió, lo condicione a un Else
    }

    // Aquí creamos y guardamos información de lo que harán las formas o figuras que estarán invadiendo el sketch
    formas.push({
      x: x, // Acá guardamos la posición horizontal
      y: y, // Acá guardamos la posicioón vertical 
    
      inicioX: x, // guardamos la posición original // donde nació cada figura
      inicioY: y, // variable que usaremos para la interacción con el mouse
      
    // teniendo las posiciones de las figuras podremos hacer lo siguiente:
      
      
      size: random(30,80), // Aca decimos que a la forma se le asignara un tamaño random de 30 a 80
      rot: random(TWO_PI), // Aca creamos una rotación random para cada figura. //TWO_PI visto en clases, para crear este movimiento nervioso, lo que hace es elegir un ángulo random entre 0° y 360°. Por lo que la figura se verá rotada.
      velocidad: random(0.5,1.5) // Aca declaramos que la velocidad variará entre 0.5 a 1.5.

    });

  }


}


// DRAW //
//EMPEZAMOS A ACTIVAR
function draw() {
  background(0); // SIN FONDO


  // USO DE IMÁGENES //
  image(imgPerson, 0, 0, 700, 700); // POSICIÓN MÁS TAMAÑO DE LA IMAGEN
  
 
  //CAMBIO DE CURSOR
  image(signoIntcursor, mouseX, mouseY, 40, 40); // DEFINIMOS EL CAMBIO DEL CURSOR Y LA POSICION
  
  // TEXTOS //
  //AGREGAMOS UN MAP, donde el texto sera más visible cuando el mouse está en la esquina superior izquierda y más tenue cuando se mueve hacia la esquina inferior derecha.
  let opacidadTexto = map(mouseX + mouseY, 0, width + height, 255, 20); //creamos la variable
  fill (240, 220, 0, opacidadTexto); // COLOR DEL TEXTO 
  textSize(30); // TAMAÑO DEL TEXTO
  textStyle(ITALIC); // ESTILO DEL TEXTO
  noStroke(); // Desactivamos el marco para que no afecte al texto
  text("habitando lo ajeno", 350, 650);
  
  
  // FIGURAS //
  // LOOP
  // este for sirve para recorrer todas las figuras que están guardadas    dentro del array "formas"
  // el loop se repetirá tantas veces como figuras existan

  for(let i = 0; i < formas.length; i=i+1){ 

    let f = formas[i];
  // aquí guardo cada figura en una variable más corta llamada "f"
  // formas[i] significa:"la figura actual del array"


    // MOVIMIENTO RANDOM / NERVIOSO

    f.x += random(-1.5,1.5); // Después de que definimos la variable f podemos decir que queremos la posicion x de esa figura 
      // mover figura horizontalmente
      // random(-1.5,1.5)
      // genera números random positivos
      // y negativos

      // asi logramos entonces que la figura se mueva de manera inestable o nerviosa

    f.y += random(-1.5,1.5); // Lo mismo que lo anterior pero con la posición y

    // INTERACCIÓN
    // SI SE PRESIONA EL MOUSE
    // AVANZAN HACIA EL CENTRO

    if(mouseIsPressed){ //SI MANTIENES EL CLICK DEL MOUSE
      // Aca definimos estas dos variables que son el calculo entre el centro del sketch y la posición de la figura para definir cuánto le falta a la figura para llegar al centro, que es donde quiero que se dirija.
 
      let dx = width/2 - f.x;
      let dy = height/2 - f.y;

      f.x += dx * 0.004 * f.velocidad; // Aca simplemente hacemos el mov al centro y agregamos la velocidad de este al presionar el mouse
      f.y += dy * 0.004 * f.velocidad;

}
else{ //

  f.x = lerp(f.x, f.inicioX, 0.04); //  lerp es una función que sirve para mover algo lentamente desde un punto hacia otro. // función que busqué en ChatGpt para hacer más automatica la idea 

  f.y = lerp(f.y, f.inicioY, 0.04); // basicamente tenemos la posición actual de la figura X e Y con f.x f.y + la f.inicioX/Y que es la variable que definimos que guardara las posiciones originales de cada figura + la velocidad con la cual retrocederá

}
    
    // TRANSFORMACIONES // 
    push(); //sirve para guardar temporalmente todas las transformaciones que usaré en esta figura. Lo utilizo para que los cambios como la rotación, escala o movimiento solo afecten a una imagen y no a todas las demás figuras del sketch.
    translate(f.x, f.y);
    rotate(f.rot);
    scale(random(0.97,1.03));
    tint(255,150); // agrego una transparencia para un toque mas suave a la pieza grafica
    image(figura, 0, 0, f.size, f.size); 
    pop(); //finaliza las transformaciones y devuelve el sketch a su estado original.


  }
  
  // ACÁ ACTIVAMOS LA CONDICIONAL DE SI EL MOUSE INGRESA AL SKETCH ESTE ACTIVRÁ LAS FRASES DENTRO DEL MISMO Y SI ES QUE SALE DEL SKETCH ESTE NO MOSTRARÁ NADA
  
  if(mouseX > 0 && mouseX < 600 && mouseY > 0 && mouseY < 600){

    fill(82, 27, 27); // COLOR DEL TEXTO
    textSize(25); // TAMAÑO DEL TEXTO
    textStyle(ITALIC); // ESTILO DEL TEXTO

    //FRASES CON SUS RESPECTIVAS POSICIONES
    text(frases[0],110,150); 
    text(frases[1],550,120);
    text(frases[2],120,350);
    text(frases[3],580,400);
    text(frases[4],180,610);
    text(frases[5],520,600);

  }
  
 //MARCO // FIGURA GEOMETRICA // CUADRADO SIN RELLENO // 1DE4
  rectMode(CORNER);
  noFill(); // sin relleno
  stroke(3, 3, 3); // color del borde
  strokeWeight(20); // grosor del borde
  rect(0,0,700,700);
  
  {

 // TRIÁNGULOS AL MARCO // FIGURA GEOMETRICA // 2DE4
  fill(0);
  // esquina superior izquierda
  triangle(
    0, 0,
    40, 0,
    0, 40  
  );
 // esquina superior derecha
  triangle(
    700,0,
    660, 0,
    700, 40
  );
  // esquina inferior izquierda
  triangle(
     0, 700,
    0, 660,
    40, 700
  );
  // esquina inferior derecha
  triangle(
    700, 700,
    660, 700,
    700, 660
  );
  }
  // LINEAS COMO SIMBOLIZANDO ALGO ROTO //line(x1, y1, x2, y2)// FIGURA GEOMETRICA //3DE3
  stroke(0, 100);
  strokeWeight(0.4);
  line(0, 200, 700, 500);
  line(100, 0, 600, 700);
  line(0, 500, 700, 200);
  line (500,700,200,0);
  line(700,600,0,100);
  line(200,700,500,0);
  
  
  // EFECTO GLITCH // FIGURA GEOMETRICA //4DE4 //rect(x, y, ancho, alto)
 fill(0, 25); //blanco tenue
  noStroke();
  rect(50, 80, 180, 20);
  rect(300, 60, 250, 15);
  rect(520, 140, 120, 25);
  rect(80, 220, 200, 18);
  rect(350, 260, 300, 22);
  rect(40, 340, 160, 14);
  rect(420, 380, 220, 20);
  fill(134, 25); // morado tenue
  rect(100, 500, 260, 18);
  rect(460, 520, 180, 16);
  rect(70, 620, 300, 22);
  rect(50, 60, 180, 18);
  rect(260, 40, 220, 14);
  rect(520, 90, 140, 22);
  rect(120, 110, 160, 16);
  rect(80, 180, 240, 20);
  rect(360, 170, 280, 18);
  fill(240, 25); // amarillo tenue
  rect(500, 210, 160, 14);
  rect(60, 280, 200, 16);
  rect(300, 300, 260, 22);
  rect(520, 320, 140, 18);
  rect(140, 340, 180, 14);
  rect(90, 420, 220, 18);
  rect(360, 440, 260, 16);
  rect(580, 400, 100, 22);
  fill(134, 25); // morado tenue
  rect(60, 520, 240, 20);
  rect(320, 540, 300, 18);
  rect(100, 580, 200, 16);
  rect(450, 600, 180, 22);
  rect(250, 650, 260, 14);

}

---
```
### Conclusión 

- Como tal realizar esta pieza en p5.js fue todo un desafío, ya que más allá de poder entender y dar uso a los códigos que aprendimos en clases, tratar de crear una pieza gráfica digital e interactiva fue algo totalmente nuevo para mí como estudiante. Además puedo decir que este proyecto también me ayudó a entender que programar no es solamente escribir códigos, sino también experimentar, equivocarse, probar distintas soluciones y construir una idea visual desde algo muy técnico. El proceso fue muy importante porque me permitió comprender mejor cómo pequeñas funciones dentro del código podían cambiar completamente la sensación que transmite una obra. Pensar desde lo conceptual a lo interactivo fue una tarea que, dentro de todo, disfrute. Debo decir que sé que se pueden hacer piezas mejores. Pero poco a poco creo que entenderé mejor como usar la programación como tal para transmitir mejor una idea y/o emoción al usuario. 

