# Solemne-II


# Habitando lo ajeno

### Proyecto realizado en p5.js

---

## Información del proyecto

-  **Nombre del proyecto:**  *Habitando lo ajeno*  
-  **Autor/a:** Ayelen Vásquez Navea See More  

---

## Descripción objetivo

* Habitando lo ajeno * es una pieza interactiva desarrollada en ** p5.js ** basada en la problemática de la disforia de género.  

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

### Conclusión 

- Como tal realizar esta pieza en p5.js fue todo un desafío, ya que más allá de poder entender y dar uso a los códigos que aprendimos en clases, tratar de crear una pieza gráfica digital e interactiva fue algo totalmente nuevo para mí como estudiante. Además puedo decir que este proyecto también me ayudó a entender que programar no es solamente escribir códigos, sino también experimentar, equivocarse, probar distintas soluciones y construir una idea visual desde algo muy técnico. El proceso fue muy importante porque me permitió comprender mejor cómo pequeñas funciones dentro del código podían cambiar completamente la sensación que transmite una obra. Pensar desde lo conceptual a lo interactivo fue una tarea que dentro de todo disfrute. Debo decir que sé que se pueden hacer piezas mejores. Pero poco a poco creo que entenderé mejor como usar la prpgramación como tal para transmitir mejor una idea y/o emoción al usuario. 

