# Angular-testing
<p>Respositorio con mini proyectos de angular, para ir aprendiendo.</p>
<h1>Una pequeñísima introducción</h1>
<p>Antes de empezar, cabe destacar que Angular usa TypeScript. Esta paltaforma de desarrollo incluye un framework para construir aplicaciones web, junto a una colección de librerías que cubren algunas características tales como routing, manejo de formularios, comunicación cliente-servidor... Para ello, Angular usa componentes como los bloques de construcciónque componen una aplicación. Este componente incluye una clase de TypeScript con un <code>@Component()</code>, un template de HTML, y estilos. Por otra parte, aquí se va a utilizar Angular CLI, una herramienta que ayuda a construir aplicaciones en este framework. Algunos comandos son:</p>
  <ul>
    <li><code>ng build</code> - compila una aplicación Angular dentro de un directorio de salida.</li>
    <li><code>ng serve</code>Construye y sirve aplicaciones, reconstruyendo en base a los cambios de archivos.</li>
    <li><code>ng generate</code> - genera o modifica archivos en base a un esquema.</li>
    <li><code>ng test</code> - ejecuta unidades de tests en un proyecto dado.</li>
    <li><code>ng e2e</code> - construye y sirve una aplicación Angular, después ejecuta test de tipo <i>end-to-end</i></li>
  </ul>
<p>Algunos enlaces útiles:</p>
  <ul>
    <li>Qué es Angular: <a href="https://angular.io/guide/what-is-angular</a>https://angular.io/guide/what-is-angular</li>
    <li>Tutorial de Angular para crear un proyecto básico: <a href="https://angular.io/start">https://angular.io/start</a></li>
    <li>Tutorial de este pequeño proyecto: <a href="https://www.udemy.com/course/angular-free-masterclass-part-one/learn/lecture/32560170#overview">https://www.udemy.com/course/angular-free-masterclass-part-one/learn/lecture/32560170#overview</a></li>
  </ul>
<h1>Setup de Angular</h1>
<h2>Primero: instalación de Angular</h2>
    <li>Nos vamos a la página de <a href="https://nodejs.org/en/">https://nodejs.org/en/</a> y descargamos la opción recomendada de la página.</li>
    <li>Insertamos en la consola que se nos ha creado nueva, el siguiente código en cmd: <code>npm install -g @angular/cli</code>. Podemos comprobar la versión ejecutando el comando <code>ng version</code> en la terminal.</li>
    <li>Ahora, crearemos un nuevo proyecto con el código <code>ng new [nombre de proyecto]</code>. En mi caso, el proyecto se llamará <b>covid-tracker-app</b>. Seguidamente, preguntará si queremos añadir "Angular routing", a lo que diremos Yes. En mi caso, cuando pregunte <i>Which stylesheet format would you lke to use?</i>, escogeré <b>CSS</b>.</li>
    <li>Ahora, nos situaremos en la carpeta del proyecto con <code>cd covid-tracker-app</code>.</li>
    <li>Ahora, abriremos nuestro localhost oprimiendo <code>ng serve -o</code>.</li>
  </ol>
  <p>Y eso es todo, con esto podremos abrir la página por defecto de angular una vez accedamos a nuestro navegador. Esta página puede consultarse para conectarse a la Documentación, o a Material extra entre otros.</p>

<h2>Segundo: estructuración de carpetas de un proyecto Angular</h2>
<p>Algunos archivos importantes son:</p>
  <ul>
    <li><b>angular.json</b>: está ubicado en el nivel raíz de la estructura de archivos. Este archivo proporciona valores predeterminados de configuración para todo el espacio de trabajo y específicos del proyecto. Se utilizan para las herramientas de compilación y desarrollo proporcionadas por la CLI de Angular. Los valores de ruta proporcionados en la configuración son relativos al directorio raíz del espacio de trabajo.</li>
    <li><b>src</b>: paquete donde se encuentran los archivos principales para nuestra aplicación, anidados.</li>
    <ul>
      <li><li><b>app</b>: aquí tenemos archivos usados para la aplicación. Por ejemplo, <b>app.component.html</b> contiene todo el código relacionado con la "vista" de la aplicación; es decir, la parte visible (el HTML junto al CSS, si se quiere usar).</li>
      <li>Otro archivo importante en esta carpeta es <b>app.module.ts</b>, donde se encuentran los módulos y compoenentes importados requeridos por la app. Este archivo es IMPORTANTE en relación con las características de los componentes de servicio, módulos distintos que serán importados en este archivo. Este código lo usará Angular para compilar TypeScript en JavaScript. </li>
    </ul>
    <li><b>main.ts</b>: ubicado en la carpeta raíz, este archivo permite que nuestra aplicación permita usar módulos como el de Bootstrap. Esto lo importa y se pasará al archivo <i>app.module.ts</i>.</li>
  </ul>
<h2>Estilizando Angular: Bootstrap y Font Awesome</h2>
<p>Para ello, necesitaremos descargar los módulos mediante NPM (Node Package Manager), usando una terminal, ya sea la de node.js o la del sistema operativo.</p>
  <ol>
    <li>Ejecutamos <code>npm install --save [nombre de módulo]</code>, para aseguranos de que son guardados estos paquetes de terceros en nuestra app. En mi caso, usaré Bootstrap y Font Awesome, instalándolo con el código <code>npm install --save bootstrap font-awesome</code>. Podemos comprobar que se han instalado correctamente yendo al archivo <i>package.json</i>, hasta encontrar la línea donde aparezca Bootstrap y su versión. Lo mismo con Font Awesome.</li>
    <li>Usando paquetes: para usarlos, hay que ir al archivo <b>angular.json</b> de la carpeta raíz. Ahí, hay que buscar la línea <code>"scripts": []</code>. Aquí se pueden importar los CSS y archivos JS de los módulos instalados.</li>
    <li>Modificando <i>angular.json</i> y <i>"styles"</i>: indicaremos nuestra capa de estilos css principal, escribiendo: <code>"styles": [ "" "src/styles.css" ],</code> encima de la línea de <i>"scripts"</i>. Las comillas vaías serán rellenadas con las importaciones de módulos. Ahora, vamos a importar bootstrap incluyendo encima de <i>"src/styles.css"</i> la siguiente línea de código: <code>"node_modules/bootstrap/dist/css/bootstrap.min.css",</code>. De esta forma, importaremos el archivo .csv de Bootstrap. Ahora, hay que instalar Font Awesome de la misma forma que con Bootstrap, insertando código justo debajo: <code>"node_modules/font-awesome/css/font-awesome.min.css",</code>.</li>
    <li>Modificando <i>angular.json</i> y <i>"scripts"</i>: para Bootstrap, también necesitamos incluir su módulo de JS. Entonces dentro de <i>"scripts": []</i>, generaremos la siguiente línea de código: <code>"node_modules/bootstrap/dist/js/bootstrap.min.js"</code>.</li>
    <li>Ejemplo de icono: podemos crear una etiqueta donde genere un icono de Facebook, para probar si funcionan los nuevos módulos. El código es: <code>&lt;i class=""fas fa-facebook"&gt;&lt;i&gt;</code>.</li>
  </ol>
<h1>Módulos, Componentes y Templates</h1>
<h2></h2>
<h1>Routing, Rutas y Lazy Loading</h1>
<h2></h2>
<h1>Trabajando con Datos</h1>
<h2></h2>
<h1>Fin del mini proyecto...</h1>
<h2></h2>
