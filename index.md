# 📕 **Apuntes de Node y Express**

<div style="text-align: justify">
    Seguramente si eres un programador nuevo no sepas qué es Node.js y por qué es tan importante el aprenderlo e incluirlo en nuestro set de tecnologías. Y es que seguramente estamos pensando que Javascript sólo vive dentro de los navegadores web, ya que este empezó como un lenguaje en busca de modificar pequeños detalles de las páginas web. No obstante se ha convertido en un lenguaje muy complejo innumerables librerías y diferentes aplicaciones. Y es que mientras pasaba el tiempo los proveedores de navegadores como Mozilla y Google empezaron a dedicarle más recursos en reducir los tiempos de ejecución de Javascript, y es así que estos navegadores obtuvieron "Javascript engines" (motores de javascript) como resultado. <br /><br />
    📅 En el año 2009 surgió el nacimiento de Node.js que empezo a utilizar el motor V8 de Javascript (desarrollado por Google Chrome) en servidores.
</div>

<br />

### **🙋‍♂️ Beneficios de Node**
Podemos iniciar por que funciona a través del motor V8 de Javascript y este es rápido. Asímismo Node mantiene una codificación **asincrónica y no bloqueante** haciendo que el código sea más rapido. Este principio se basa en optimizar los recursos manejando muchas operaciones de IO (Input and Output / Entrada y Salida) en un mismo hilo de forma eficiente. Podrías entender este concepto como un mozo de un restaurante que reparte platillos de comida, el recibe un pedido pero hasta que la comida esté lista el puede seguir consultado a más clientes. No tiene que esperar a que una tarea se complete (no se queda esperando hasta que un platillo esté listo, si no sigue atendiendo a los clientes).

<br />

### **🤔 ¿Qué es una promesa?**
Este es un concepto muy importante, una promesa representa un valor que puede estar disponible ahora, en el futuro o nunca. Interpreta el nombre "Promesa" como justamente su nombre lo dice "una promesa, del verbo prometer, prometerte algo". Y cuando prometes algo no estás dando seguridad que lo harás, simplemente estas comprometiéndote a cumplirlo".

```js
// Creamos una promesa que tiene como parámetro una función que a su vez recibe dós parámetros, (resolve, reject).
// Resolve = Si el trabajo finalizó con éxito, entonces se le incluye un valor a la función resolve(valor).
// Reject = Si ocurrió un error se llama a la función reject(error).

new Promise((resolve, reject) => { /* Cuerpo */});

// Aquí tenemos un ejemplo que trata de simular una peticion de informacion a un servidor, que dentro de ella tiene un temporizador de 3 segundos para demostrar que esta promesa trabaja asincronicamente es decir, que se queda esperando una respuesta si existe.
const userData = new Promise( (resolve, reject) => {
    // Aquí hacemos que obligatoriamente tire un error para poder demostrar el reject()
    if (1 + 1 === 3) {
        setTimeout(() => resolve("Datos del servidor obtenidos"), 3000);
    } else {
        reject("Error obteniendo datos");
    }
});

// El .then() que se traduce como "después" lo que hace es recibir la promesa, y maneja el resultado.
userData
    .then((respuesta) => console.log(respuesta))
    .catch((error) => console.log(error));

```

<br />

### **💻 Hola mundo en node**
Como es de costumbre en una nueva tecnología, mandaremos nuestro primer "Hola mundo" . Crearemos un script de javascript que tenga como extensión el .js

```js
console.log("Hola, mundo!"); // Hola mundo
```

para poder correr este script nos iremos al directorio y en nuestra consola colocaremos el siguiente comando, con la siguiente estructura: <code>node <nombre_del_archivo>.js</code>, en este caso:

```
node helloworld.js
```

<br />

### **💻 Usando módulos en Node**
Es muy común el querer importar 