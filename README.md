# JSON

JSON (JavaScript Object Notation) es un **formato de intercambio de datos**, no un lenguaje de programación.

Se usa para enviar y recibir información entre un frontend y un backend.

Está basado en pares clave–valor y estructuras como objetos y arreglos.

Ejemplo:

```json
{
"users":[
{"id":1,"name":"Ana"},
{"id":2,"name":"Luis"}
]
}

```

API y endpoint

Una API es una **interfaz** que permite a una aplicación comunicarse con otra.

Un endpoint es una **URL específica** que representa un recurso dentro de una API.

Ejemplo:

- `/users` → recurso usuarios
- `/products` → recurso productos

Cada endpoint responde a métodos HTTP como GET, POST, PUT y DELETE.

json-server

json-server es un **servidor backend falso** que:

- lee un archivo JSON
- crea automáticamente endpoints REST
- devuelve y modifica datos en formato JSON

Cada clave raíz del archivo JSON se convierte en un endpoint.

Ejemplo:

```json
{
"users":[],
"products":[]
}

```

Crea:

- `/users`
- `/products`

Relación entre frontend y json-server

El frontend **no accede al archivo JSON directamente**.

El frontend se comunica con el servidor usando fetch y endpoints.

Ejemplo conceptual:

- Navegador → fetch
- fetch → endpoint
- endpoint → datos JSON

fetch

fetch es la API del navegador para hacer peticiones HTTP.

Flujo básico:

1. fetch hace la petición
2. el servidor responde con un objeto Response
3. `response.json()` convierte la respuesta a datos JavaScript

GET:

```jsx
fetch('/users')

```

POST:

```jsx
fetch('/users', {
method:'POST',
headers: {'Content-Type':'application/json' },
body:JSON.stringify({name:'Pedro' })
});

```

GET obtiene datos, POST crea datos.

json-server y Git

- Git/GitHub solo guarda archivos
- json-server es un proceso que corre en local
- No se “sube” un servidor a GitHub
- Se versiona el código y el JSON, no el servidor en ejecución

Durante el desarrollo:

- el repo está en GitHub
- el servidor corre localmente
- fetch apunta a `localhost`

Idea clave para la prueba

json-server **simula un backend real** para practicar:

- JSON
- APIs
- endpoints
- fetch
- comunicación frontend–backend

No es para producción, solo para aprendizaje y pruebas.

Si quieres, puedo reducir esto aún más a un esquema tipo “chuleta de examen” o prepararte preguntas típicas con respuestas modelo.
