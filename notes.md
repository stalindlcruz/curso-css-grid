<!--
🧩 ¿Qué es CSS Grid?
CSS Grid es un sistema de maquetación bidimensional que te permite controlar el diseño de una página web utilizando filas y columnas. En lugar de depender de técnicas más antiguas, como flotantes o posición absoluta, Grid simplifica el proceso de creación de layouts complejos.

CSS Grid es un sistema de diseño bidimensional. Esto implica que se puede acomodar contenido tanto en filas como en columnas. Con Grid, tienes la flexibilidad de colocar elementos en cualquier parte de la cuadrícula, incluso superponerlos sin necesidad de utilizar position: absolute.

➡️ ¿Qué es Flexbox?
Por otro lado, Flexbox es un sistema de diseño unidimensional. Esto significa que solo puedes trabajar en una dirección: filas o columnas. Ideal para situaciones donde solo necesitas alinear elementos de forma lineal.

🔑 Comparativa: ¿Cuándo usar cada uno?
Usa Grid: cuando necesites trabajar en bidimensional (filas y columnas) o cuando tu diseño sea más complejo y requiera superposiciones.
Usa Flexbox: para diseños unidimensionales, especialmente si solo necesitas alinear elementos en una línea.

En conclusión, no hay un método “mejor” que el otro. Ambos tienen su lugar en el diseño web, y saber cuándo usar cada uno puede simplificar tu trabajo y mejorar los resultados de tus proyectos.

📊 Introducción a CSS Grid
Para transformar nuestro contenedor en una cuadrícula, utilizaremos la propiedad display: grid;. Esto crea una estructura de cuadrícula donde los elementos se organizan automáticamente.

Al hacerlo, podrás notar algunos números interesantes cuando inspeccionas tu cuadrícula con las herramientas de desarrollo del navegador. Estos números representan las filas y columnas.

🏗️ Definiendo Columnas en la Cuadrícula
Por defecto, los elementos están organizados en una sola columna. Si deseas más columnas, simplemente debes definirlas. Por ejemplo, si queremos dos columnas de 100 píxeles, usaríamos:

.container {
  background-color: lightsalmon;
  border: 1px solid black;
  border-radius: 8px;
  display: grid;
  grid-template-columns: 100px 100px;
}

Al comenzar a trabajar con CSS Grid, es común encontrarse con el comportamiento automático del sistema de cuadrículas. Por ejemplo:

.container {
  display: grid;
  grid-template-columns: 1fr 1fr; /* Dos columnas */
  grid-template-rows: auto; /* Filas automáticas */
}

Con esta configuración, CSS crea automáticamente las filas según el espacio disponible. Puedes observar cómo se añaden filas de manera dinámica:

1ª fila: Toma el espacio necesario.
2ª fila: Igualmente se ajusta automáticamente.

📏 Personalizando las filas
Pero no te limites a lo automático. Puedes personalizar la altura de las filas con la propiedad grid-template-rows. Por ejemplo:

.container {
  display: grid;
  grid-template-rows: 100px 50px 30px 100px; /* Alturas específicas */
}

Esto te permite definir alturas específicas para cada fila, creando un diseño más controlado y atractivo.

Cuando inspecciones tu cuadrícula en las herramientas de desarrollo, podrás notar líneas que delimitan las filas y columnas:

Cuidado: No asumas que si no hay elementos, no hay cuadrícula. Puedes tener un diseño planeado y dejar espacio para elementos futuros.

Cuando utilizas grid-template-rows, puedes especificar el tamaño de las filas. Sin embargo, si decides omitir esta propiedad, CSS Grid generará las filas automáticamente. Esto es extremadamente útil cuando el contenido fluctúa.

.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-auto-rows: 200px; /* Altura automática de las filas */
}

⚙️ ¿Cómo Funciona?
Cuando defines dos columnas, pero no especificas filas, CSS Grid genera nuevas filas automáticamente a medida que se necesita espacio adicional. Además, puedes configurar la altura que tendrán estas filas automáticamente.

Si decides establecer una altura de fila específica, CSS Grid la utilizará para la primera fila generada, mientras que las siguientes filas adoptarán la altura que hayas especificado en grid-auto-rows.

Esto es particularmente útil para mantener un diseño limpio y ordenado, permitiendo que se adapten a cualquier contenido que insertes en tu cuadrícula.

📏 Comparación con Columnas
Aunque este sistema de auto-generación se aplica principalmente a las filas, también puedes implementarlo para columnas. Por defecto, los elementos se organizan en filas, pero tienes la opción de reestructurar el diseño a columnas si así lo prefieres. Este aspecto se explorará más a fondo en lecciones posteriores.

La cantidad de columnas no está determinada por una regla rígida. Depende del diseño y la interfaz de usuario (UI). En plataformas como Google, puedes observar un gran número de columnas, y eso es completamente normal. Aquí tu creatividad juega un papel fundamental.

📏 ¿Qué es la función minmax()?
La función minmax() te permite especificar el tamaño mínimo y máximo de un elemento grid. Por ejemplo, si deseas que una columna tenga un ancho mínimo de 100 píxeles y que crezca hasta ocupar el espacio disponible, puedes hacerlo utilizando:

.grid-container {
  display: grid;
  grid-template-columns: minmax(100px, 1fr) 1fr;
}

En el código anterior:

La primera columna tendrá un ancho mínimo de 100 píxeles y puede crecer hasta ocupar una fracción del espacio disponible.

La segunda columna se ajustará al resto del espacio.

🔍 Comportamiento de la función minmax()

Ejemplo práctico
Al ajustar el tamaño de la pantalla, verás cómo la primera columna nunca será más estrecha que 100 píxeles. Aquí tienes un flujo básico de cómo se comportan las columnas al cambiar el tamaño de la ventana:

Ajusta tu pantalla: Observa cómo la primera columna mantiene su tamaño mínimo.

Espacios en fracción: Cuando hay suficiente espacio, ambas columnas se ajustan al espacio de manera uniforme.

📊 Contexto real
Imagina que estás creando una aplicación similar a Spotify, donde necesitas que ciertos elementos de la interfaz, como menús o barras laterales, mantengan un tamaño mínimo para asegurar que los iconos o textos sean visibles. La función minmax() se convierte en tu aliada para lograr esto.

🛠️ Ventajas de utilizar minmax()

Evita media queries: Con minmax(), puedes lograr un diseño responsivo sin la necesidad de múltiples media queries, simplificando tu CSS.

Diseños más flexibles: Permite que tus columnas y filas se comporten de manera más inteligente según el espacio disponible.

✅ Resumen
La función minmax() es esencial para diseñar interfaces responsivas con CSS Grid. Te permite establecer límites en el tamaño de tus columnas y filas, asegurándote de que tu contenido siempre sea visible y bien presentado.

💡 Gap vs Margin en CSS Grid
En esta lección, exploraremos las diferencias esenciales entre gap y margin en el contexto de CSS Grid. Aprenderás por qué el uso de gap es generalmente más efectivo para crear separación entre elementos, y cómo esto puede simplificar tu código y mejorar la coherencia en tu diseño.

📏 ¿Qué es el Gap?
El gap es una propiedad diseñada para trabajar específicamente con contenedores de cuadrícula. Permite controlar la separación entre elementos de forma más sencilla, sin afectar los elementos exteriores.

Ejemplo de Uso de Gap
Imagina que tienes una cuadrícula con varias filas. Puedes establecer un gap para controlar el espacio entre ellas:

.container {
  display: grid;
  grid-template-rows: auto 50px;
  gap: 16px; /* espacio entre filas */
}

📐 Comprendiendo el Margin
Por otro lado, el margin se aplica a los elementos individuales y puede resultar más complicado al intentar cohesionar la separación entre ellos. Al usar margin, la separación externa puede llevar a efectos no deseados que son más difíciles de manejar.

🚀 ¿Cuándo Usar Gap y Margin?
Gap: Utiliza esta propiedad cuando quieras que la separación entre los elementos de la cuadrícula sea uniforme y fácil de administrar.
Margin: Úsalo en situaciones donde necesites controlar el espacio alrededor de los elementos o para lograr separaciones específicas entre elementos que no son parte de la cuadrícula.
 -->
