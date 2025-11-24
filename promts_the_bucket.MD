# PROMT 1

Actúa como un **Desarrollador Senior en JavaScript**, experto en depuración, análisis de errores y buenas prácticas.  
Tu tarea es revisar mi código, identificar todos los errores que puedan generar fallos o resultados incorrectos, explicar la causa de cada uno y entregar una versión corregida y mejorada.

---

## Contexto

Estoy trabajando con un arreglo de usuarios y dos funciones:

- Una que filtra usuarios mayores de edad.  
- Otra que busca un usuario por ID y devuelve su nombre.  

El código está generando errores y quiero que los identifiques y los soluciones.

---

## Código con el error

    const usuarios = [
      { id: 1, nombre: "Ana", edad: 20 },
      { id: 2, nombre: "Luis", edad: 17 },
      { id: 3, nombre: "Carla", edad: 25 }
    ];
    
    function filtrarMayores(lista) {
      return lista.filter(usuario => usuario.edad > 18);
    }
    
    function buscarUsuario(id) {
      return usuarios.find(u => u.id === id).nombre.toUppercase();
    }
    
    const mayores = filtrarMayores(usuarios);
    console.log("Usuarios mayores de edad:", mayores);
    
    const nombreUsuario = buscarUsuario(4);
    console.log("Nombre del usuario:", nombreUsuario);

---

## Lo que necesito que hagas

- Detectar todos los errores del código.  
- Explicar claramente la causa de cada error.  
- Entregar una versión corregida y funcionando.  
- Dar recomendaciones para evitar estos errores a futuro.  

---

## Formato de respuesta esperado

1. **Errores detectados**  
2. **Explicación técnica**  
3. **Código corregido**  
4. **Recomendaciones finales**

# PROMT 2

Actúa como un **Desarrollador Senior en JavaScript**, experto en asincronía, promesas, async/await, debugging y buenas prácticas.  
Tu tarea es analizar mi código, identificar todos los errores que produzcan fallos en tiempo de ejecución o resultados incorrectos, explicar por qué ocurren y entregarme una versión corregida y optimizada.

---

## Contexto

Estoy trabajando con funciones asincrónicas que obtienen datos simulados mediante `setTimeout`.  
Luego intento filtrar esos datos por nombre y mostrar el usuario encontrado, pero el código falla.  
Necesito que identifiques y soluciones todos los errores.

---

## Código con el error

    async function obtenerDatos() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve([
            { id: 1, nombre: "Juan" },
            { id: 2, nombre: "Sara" },
            { id: 3, nombre: "Carlos" }
          ]);
        }, 1000);
      });
    }
    
    function filtrarPorNombre(lista, nombre) {
      return lista.filter(user => user.name.toLowerCase() === nombre.toLowerCase());
    }
    
    async function mostrarUsuario(nombre) {
      const datos = obtenerDatos();
      const filtrados = filtrarPorNombre(datos, nombre);
    
      console.log("Usuario encontrado:", filtrados[0].nombre.toUpperCase());
    }
    
    mostrarUsuario("Sara");

---

## Lo que necesito que hagas

- Detectar **todos** los errores del código (asincronía, propiedades mal escritas, acceso a datos, etc.).  
- Explicar de manera clara la causa de cada uno.  
- Entregar una **versión corregida y funcionando** del código.  
- Recomendar buenas prácticas para evitar problemas similares en el futuro.  

---

## Formato de respuesta esperado

1. **Errores detectados**  
2. **Explicación técnica**  
3. **Código corregido y funcional**  
4. **Recomendaciones finales**  

---

# PROMT 3 

Actúa como un **Desarrollador Senior en JavaScript**, especialista en POO, clases, herencia, validación de datos y debugging.  
Tu tarea es analizar mi código, detectar todos los errores que generen fallos en tiempo de ejecución o resultados incorrectos, explicar por qué ocurren y entregarme una versión corregida y optimizada.

---

## Contexto

Estoy trabajando con clases en JavaScript (`Persona` y `Estudiante`).  
Quiero crear un estudiante, validar los datos recibidos y mostrar información formateada.  
Sin embargo, el código presenta errores y necesito ayuda para encontrarlos y corregirlos.

---

## Código con el error

    class Persona {
      constructor(nombre, edad) {
        this.nombre = nombre;
        this.edad = edad;
      }
    
      saludar() {
        return "Hola, soy " + this.Nombre;
      }
    }
    
    class Estudiante extends Persona {
      constructor(nombre, edad, curso) {
        super(nombre);
        this.curso = curso;
      }
    
      info() {
        return `Estudiante: ${this.nombre} - Curso: ${this.curso.toUppercase()} - Edad: ${this.edad}`;
      }
    }
    
    function crearEstudiante(data) {
      if (!data.nombre || !data.edadd || !data.curso) {
        throw new Error("Datos incompletos");
      }
    
      return new Estudiante(data.nombre, data.edad, data.curso);
    }
    
    const datos = { nombre: "Felipe", edad: 17, curso: "javascript" };
    
    const est = crearEstudiante(datos);
    console.log(est.info());

---

## Lo que necesito que hagas

- Detectar **todos** los errores del código (POO, herencia, validaciones, propiedades mal escritas, etc.).
- Explicar claramente la causa de cada error.
- Entregar una **versión corregida y funcional** del código.
- Recomendar buenas prácticas para este tipo de estructuras y validaciones.

---

## Formato de respuesta esperado

1. **Errores detectados**
2. **Explicación técnica**
3. **Código corregido y funcional**
4. **Recomendaciones finales**

---

# PROMT 4 

Actúa como un Desarrollador Senior en JavaScript, experto en asincronía, manejo de datos, validaciones, Promesas, async/await y debugging avanzado.
Tu tarea es revisar mi código, identificar todos los errores que puedan causar fallos, explicar por qué ocurren y entregarme una versión corregida, optimizada y segura.

---

## Contexto

Estoy obteniendo una lista de productos simulados con setTimeout.
Luego intento calcular el total de los precios, pero el código genera errores debido a problemas de asincronía, tipos de datos y propiedades mal escritas.
Necesito que los identifiques y los soluciones.

---

## Código con el error

    async function fetchProductos() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve([
            { id: 1, nombre: "Laptop", precio: 2500 },
            { id: 2, name: "Mouse", precio: 50 },
            { id: 3, nombre: "Teclado", precio: "100" }
          ]);
        }, 800);
      });
    }
    
    function calcularTotal(productos) {
      return productos.reduce((acc, p) => acc + p.precio.toUpperCase(), 0);
    }
    
    async function obtenerTotal() {
      const productos = fetchProductos();
      if (productos.length === 0) {
        throw new Error("No hay productos disponibles");
      }
    
      const total = calcularTotal(productos);
      console.log("Total:", total.toFixed(2));
    }
    
    obtenerTotal();

---

## Lo que necesito que hagas

- Detectar todos los errores del código.
- Explicar claramente la causa de cada error.
- Entregar una versión corregida y funcional del código.
- Dar recomendaciones para evitar errores similares en el futuro.

---

## Formato de respuesta esperado

1. Errores detectados
2. Explicación técnica de cada error
3. Código corregido
4. Recomendaciones finales

# PROMT 5 

Actúa como un Desarrollador Senior en JavaScript, experto en módulos ES6, asincronía, clases, validación de datos y debugging avanzado.
Tu tarea es revisar mi código, identificar todos los errores que puedan causar fallos, explicar por qué ocurren y entregarme una versión corregida, optimizada y funcional.

---

## Contexto

Estoy trabajando con módulos separados (`servicios.js` y `app.js`).  
Obtengo usuarios simulados y luego intento convertirlos a instancias de una clase, calcular el promedio de edad y mostrarlo.  
El código contiene varios errores: asincronía, nombres mal escritos, propiedades inexistentes, métodos incorrectos y uso incorrecto de map/reduce.

Necesito que analices absolutamente todo y lo soluciones.

---

## Código con el error

### servicios.js

    export function obtenerUsuarios() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve([
            { id: 1, nombre: "Ana", edad: 20 },
            { id: 2, nombre: "Luis", edaddd: 15 },
            { id: 3, name: "Carlos", edad: 30 }
          ]);
        }, 500);
      });
    }

### app.js

    import { obtenerUsuarios } from "./servicios.js";
    
    class Usuario {
      constructor(id, nombre, edad) {
        this.id = id;
        this.name = nombre;
        this.edad = edad;
      }
    
      descripcion() {
        return `${this.nombre.toUppercase()} (${this.edad} años)`;
      }
    }
    
    async function procesarUsuarios() {
      const lista = obtenerUsuarios();
    
      const usuariosConvertidos = lista.map(u => {
        return new Usuario(u.id, u.nombre, u.edad);
      });
    
      const promedioEdad = usuariosConvertidos.reduce((acc, u) => acc + u.edadd, 0) / usuariosConvertidos.length;
    
      console.log("Promedio de edad:", promedioEdad.toFixed(2));
    }
    
    procesarUsuarios();

---

## Lo que necesito que hagas

- Detectar **todos los errores** en:
  - asincronía (`await` faltante),
  - propiedades mal escritas (`edaddd`, `name`, `nombre`),
  - métodos incorrectos (`toUppercase`),
  - errores en la clase,
  - errores en map/reduce,
  - problemas al convertir datos,
  - uso incorrecto de módulos.

- Explicar **por qué ocurre cada error** y cuál es su impacto.
- Entregar una **versión 100% corregida y funcional** del proyecto.
- Dar recomendaciones profesionales para evitar errores similares.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica  
3. Código corregido completo  
4. Recomendaciones finales  

---

# PROMT 6 

Actúa como un Desarrollador Senior en JavaScript, experto en asincronía, procesamiento de arreglos, validación de datos, debugging avanzado y manejo seguro de información.
Tu tarea es analizar mi código, detectar absolutamente todos los errores, explicar por qué ocurren y entregarme una versión corregida, segura y optimizada.

---

## Contexto

Estoy trabajando con un sistema que obtiene posts simulados con setTimeout.
Luego intento procesarlos (títulos, likes y el post más popular), pero el código contiene errores en:
- propiedades mal escritas,
- métodos incorrectos,
- procesamiento asincrónico,
- map/reduce,
- bucles mal implementados,
- validación de datos,
- tipos inconsistentes.

Necesito que detectes y soluciones **todos** los errores.

---

## Código con el error

    async function traerPosts() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve([
            { id: 1, titulo: "Primer post", likes: 10 },
            { id: 2, tittle: "Segundo post", likes: "20" },
            { id: 3, titulo: "Tercer post", like: 5 }
          ]);
        }, 700);
      });
    }
    
    function procesarPosts(posts) {
      // Obtener solo los títulos en mayúscula
      const titulos = posts.map(p => p.titulo.toUppercase());
    
      // Sumar likes
      const totalLikes = posts.reduce((acc, { likes }) => acc + likes, 0);
    
      // Buscar post con más likes
      let mayor = posts[0];
      for (let i = 1; i <= posts.length; i++) {
        if (posts[i].likes > mayor.likes) {
          mayor = posts[i];
        }
      }
    
      return {
        titulos,
        totalLikes: totalLikes.toFixed(2),
        postMasPopular: mayor.titulo
      };
    }
    
    async function main() {
      const posts = traerPosts();
    
      if (posts.lenght === 0) {
        throw new Error("No hay posts");
      }
    
      const resultado = procesarPosts(posts);
      console.log(resultado);
    }
    
    main();

---

## Lo que necesito que hagas

- Detectar todos los errores del código:
  - asincronía mal manejada,
  - propiedades con nombres incorrectos,
  - métodos mal escritos,
  - valores de tipo incorrecto,
  - errores en map/reduce,
  - errores en el ciclo for,
  - validaciones mal hechas.

- Explicar de manera clara la causa exacta de cada error.
- Entregar una versión corregida y funcionando del código completo.
- Recomendar buenas prácticas para evitar errores similares.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica  
3. Código corregido completo  
4. Recomendaciones finales

# PROMT 7

Actúa como un Desarrollador Senior en JavaScript, experto en programación orientada a objetos, asincronía, validación de datos, debugging avanzado y manipulación de estructuras como Map, Set y arrays.
Tu tarea es revisar mi código, detectar todos los errores que puedan causar fallos o resultados incorrectos, explicar por qué ocurren y entregarme una versión corregida, optimizada y totalmente funcional.

---

## Contexto

Estoy trabajando con un inventario de productos obtenido de manera asincrónica.  
Luego convierto esos productos a instancias de una clase, calculo estadísticas (totales, duplicados, mapa de IDs, producto más caro), pero el código tiene múltiples errores:

- Propiedades mal escritas  
- Métodos inexistentes  
- Tipos incorrectos  
- Errores en reduce, map y sort  
- Errores de asincronía  
- Errores en validaciones  
- Datos mal estructurados desde la API simulada  
- Problemas dentro de la clase `Producto`

Necesito que analices todo y lo soluciones.

---

## Código con el error

    class Producto {
      constructor(id, nombre, precio) {
        this.id = id;
        this.nombre = nombre;
        this.precioo = precio;
      }
    
      info() {
        return `${this.name.toUppercase()} - $${this.precio}`;
      }
    }
    
    async function obtenerInventario() {
      return new Promise((res, rej) => {
        setTimeout(() => {
          res([
            { id: 1, nombre: "Laptop", precio: 2500 },
            { id: 2, nombre: "Mouse", costo: 40 },
            { id: 3, name: "Teclado", precio: 100 },
            { id: 4, nombre: "Monitor", precio: "300" }
          ]);
        }, 600);
      });
    }
    
    function convertirAClases(lista) {
      return lista.map(item => new Producto(item.id, item.nombre, item.precio));
    }
    
    function calcularEstadisticas(productos) {
      const precios = productos.map(p => p.precio);
    
      const total = precios.reduce((acc, p) => acc + p.toUpperCase(), 0);
    
      const duplicados = new Set(precios);
      if (duplicados.lenght < productos.length) {
        console.log("Hay productos duplicados");
      }
    
      const mapa = new Map();
      productos.forEach(p => mapa.set(p.id, p.nombre.toLowerCase()));
    
      return {
        total: total.toFixed(2),
        masCaro: productos.sort((a, b) => b.precio - a.precio)[0].nombre,
        mapaIds: mapa
      };
    }
    
    async function main() {
      const inventario = obtenerInventario();
    
      if (!inventario || inventario.size === 0) {
        throw new Error("Inventario vacío");
      }
    
      const productos = convertirAClases(inventario);
    
      const stats = calcularEstadisticas(productos);
      console.log(stats);
    }
    
    main();

---

## Lo que necesito que hagas

- Detectar **todos** los errores del código:
  - Propiedades mal escritas (`precioo`, `name`, `precio`, `lenght`, etc.)  
  - Métodos incorrectos (`toUppercase`, `toUpperCase` mal aplicado)  
  - Tipos de datos incorrectos (precios string)  
  - Errores en reduce y sort  
  - Errores en Set, Map y validaciones  
  - Errores serios de asincronía (falta await)  
  - Problemas al crear instancias de la clase  
  - Problemas con datos faltantes en la API simulada  

- Explicar la **causa exacta** de cada error.  
- Entregar una **versión corregida y funcional** de todo el código.  
- Dar **recomendaciones profesionales** para evitar errores similares.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica  
3. Código corregido completo  
4. Recomendaciones finales  

# PROMT 8 

Actúa como un Desarrollador Senior en JavaScript, experto en asincronía, fetch API, clases, validación de datos, debugging avanzado y buenas prácticas.
Tu tarea es revisar mi código, identificar absolutamente todos los errores que puedan causar fallos o comportamientos incorrectos, explicar por qué ocurren y entregar una versión corregida, optimizada y funcional.

---

## Contexto

Estoy consumiendo una API falsa con fetch, procesando los datos y filtrando los usuarios activos.  
Después intento sumar sus edades, pero el código contiene múltiples errores graves relacionados con:

- nombres de propiedades incorrectos,  
- uso incorrecto de fetch,  
- asincronía mal manejada,  
- mal uso de json(),  
- métodos mal escritos,  
- validaciones incorrectas,  
- uso incorrecto de map y reduce,  
- comparaciones incorrectas,  
- errores dentro de la clase `ApiCliente`.

Necesito que los detectes todos y los soluciones.

---

## Código con el error

    class ApiCliente {
      constructor(url) {
        this.urll = url;
      }
    
      async obtenerDatos() {
        const respuesta = await fetch(url);
        const data = respuesta.json;
        return data.map(item => ({
          ...item,
          nombre: item.name.toUppercase()
        }));
      }
    }
    
    function filtrarActivos(usuarios) {
      return usuarios.filter(u => u.activo === "true");
    }
    
    async function procesar() {
      const api = new ApiCliente("https://api.fake.com/users");
    
      const datos = api.obtenerDatos();
    
      if (datos.length < 0) {
        throw new Error("No hay datos");
      }
    
      const activos = filtrarActivos(datos);
    
      const totalEdad = activos.reduce((acc, { edad }) => acc + edad.toFixed(2), 0);
    
      console.log("Activos:", activos);
      console.log("Total edades:", totalEdad);
    }
    
    procesar();

---

## Lo que necesito que hagas

- Detectar **todos los errores** del código:
  - Uso incorrecto de fetch  
  - Falta de `this` al usar la URL  
  - No usar `await` correctamente  
  - No ejecutar `json()`  
  - Propiedades mal escritas  
  - Métodos mal escritos (`toUppercase`)  
  - Comparaciones incorrectas  
  - Validaciones mal hechas  
  - Uso incorrecto de `reduce`  
  - Tipos incorrectos en cálculos  
  - Errores en el manejo de asincronía  

- Explicar claramente **cada error y su causa**.  
- Entregar una **versión corregida y funcional** de todo el código.  
- Dar recomendaciones profesionales para evitar este tipo de errores en el futuro.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica  
3. Código corregido  
4. Recomendaciones finales  

# PROMT 9 

Actúa como un Desarrollador Senior en JavaScript, experto en programación orientada a objetos, manejo de fechas, asincronía, validación de datos y debugging avanzado.
Tu tarea es revisar mi código, detectar absolutamente todos los errores que puedan causar fallos o resultados incorrectos, explicar por qué ocurren y entregarme una versión corregida, optimizada y funcional.

---

## Contexto

Estoy trabajando con un sistema de eventos que se cargan de manera asincrónica.  
Cada evento debe convertirse en una clase con getters y setters, calcular días restantes y filtrar los que están próximos.
El código tiene múltiples errores graves relacionados con:

- propiedades mal escritas,  
- métodos escritos incorrectamente,  
- manejo incorrecto de fechas,  
- comparaciones inválidas,  
- asincronía mal usada,  
- errores en getters/setters,  
- nombres inconsistentes en los datos originales,  
- errores en reduce,  
- validación de listas,  
- creación incorrecta de objetos.

Necesito que los detectes todos y los soluciones.

---

## Código con el error

    class Evento {
      constructor(nombre, fecha) {
        this.nombre = nombre;
        this.fecha = fecha;
      }
    
      get diasRestantes() {
        const hoy = new Date;
        const f = new Date(this.fechaa);
        return Math.floor((f - hoy) / 1000 * 60 * 60 * 24);
      }
    
      set nombreDelEvento(nuevo) {
        if (nuevo.lenght === 0) throw "Nombre inválido";
        this.name = nuevo;
      }
    }
    
    async function cargarEventos() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve([
            { nombre: "Concierto", fecha: "2025-10-10" },
            { name: "Cumpleaños", fecha: "2025-05-01" },
            { nombre: "Examen Final", date: "2025-04-12" }
          ]);
        }, 500);
      });
    }
    
    function convertirAClases(lista) {
      return lista.map(e => new Evento(e.nombre, e.fecha));
    }
    
    async function mostrarProximos() {
      const eventos = cargarEventos();
    
      if (eventos === []) {
        throw new Error("No hay eventos");
      }
    
      const clases = convertirAClases(eventos);
    
      const proximos = clases.filter(e => e.diasRestantes > 0);
    
      const totalDias = proximos.reduce((acc, e) => acc + e.diasRestante, 0);
    
      console.log("Eventos próximos:", proximos);
      console.log("Suma de días restantes:", totalDias.toFixed(2));
    }
    
    mostrarProximos();

---

## Lo que necesito que hagas

- Detectar **todos** los errores del código:
  - Propiedades incorrectas (`fechaa`, `lenght`, `name`, `date`, `diasRestante`, etc.)  
  - Métodos incorrectos (`toUppercase`, cálculos de fechas)  
  - Errores en GET/SET  
  - Errores de asincronía (falta de `await`)  
  - Errores en comparación de listas  
  - Errores en reduce  
  - Datos con nombres inconsistentes  
  - Problemas de conversión al crear instancias  
  - Errores de lógica en filtros y cálculos  

- Explicar claramente **cada error**, por qué falla y cuál es la solución correcta.  
- Entregar una **versión corregida y funcionando** de todo el código.  
- Dar **recomendaciones profesionales** para evitar estos errores.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica  
3. Código corregido completo  
4. Recomendaciones finales  

# PROMT 10

Actúa como un Desarrollador Senior en JavaScript, experto en programación orientada a objetos, manejo de JSON, asincronía, validación de datos, debugging avanzado y buenas prácticas.
Tu tarea es revisar mi código, identificar absolutamente todos los errores que puedan causar fallos o resultados incorrectos, explicar por qué ocurren y entregarme una versión corregida, optimizada y totalmente funcional.

---

## Contexto

Estoy simulando la obtención de usuarios desde un servidor.  
Luego convierto esos datos en instancias de una clase `Usuario`, permito depósitos y retiros y finalmente muestro información final.  
El código tiene múltiples errores relacionados con:

- propiedades mal escritas,  
- uso incorrecto de JSON,  
- asincronía mal manejada,  
- métodos inexistentes,  
- tipos incorrectos,  
- cálculos numéricos mal realizados,  
- validaciones mal hechas,  
- errores al convertir datos,  
- errores graves dentro de los métodos de la clase.

Necesito que los detectes todos y los soluciones.

---

## Código con el error

    class Usuario {
      constructor(id, nombre, saldo) {
        this.id = id;
        this.name = nombre;
        this.saldoo = saldo;
      }
    
      depositar(valor) {
        if (valor <= 0) return "No se puede depositar valores negativos";
    
        this.saldo += valor.toFixed();
      }
    
      retirar(valor) {
        if (valor > this.saldo) throw new Error("Saldo insuficiente");
        this.saldo = this.saldo - valor.toUpperCase();
      }
    
      info() {
        return `${this.nombre.toUppercase()} — $${this.saldo}`;
      }
    }
    
    async function obtenerDatosDelServidor() {
      return new Promise((res, rej) => {
        setTimeout(() => {
          res(`[  
            { "id": 1, "nombre": "Felipe", "saldo": 1000 },  
            { "id": 2, "name": "Ana", "saldo": "500" },  
            { "id": 3, "nombre": "Luis", "saldoDisponible": 300 }  
          ]`);
        }, 400);
      });
    }
    
    function convertirUsuarios(lista) {
      return lista.map(u => new Usuario(u.id, u.nombre, u.saldo));
    }
    
    async function main() {
      const respuesta = obtenerDatosDelServidor();
    
      const datos = JSON.parse(respuesta);
    
      if (datos.lenght === 0) {
        throw new Error("No hay usuarios");
      }
    
      const usuarios = convertirUsuarios(datos);
    
      usuarios[0].depositar("200");
      usuarios[1].retirar(100);
      usuarios[2].retirar(50);
    
      console.log(usuarios.map(u => u.info()));
    }
    
    main();

---

## Lo que necesito que hagas

- Detectar **todos los errores** del código:
  - Propiedades incorrectas (`saldoo`, `name`, `saldoDisponible`, `lenght`, etc.)  
  - Métodos incorrectos (`toUppercase`, `toUpperCase`, `toFixed` mal aplicado)  
  - Errores de JSON (parseo incorrecto)  
  - Errores de asincronía (faltan `await`)  
  - Operaciones matemáticas incorrectas  
  - Errores graves al trabajar con strings y números  
  - Validaciones mal implementadas  
  - Datos incompletos o inconsistentes recibidos del servidor  
  - Errores dentro de la clase `Usuario`  
  - Errores en `convertirUsuarios`  
  - Errores en depósitos y retiros  

- Explicar **cada error con detalle**, incluyendo qué lo causa y cómo impacta el flujo del programa.  
- Entregar un **código corregido, seguro y completamente funcional**.  
- Dar **recomendaciones profesionales** para evitar que estos errores vuelvan a ocurrir.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica de cada error  
3. Código corregido completo  
4. Recomendaciones finales  

# PROMT 11

Actúa como un Desarrollador Senior en JavaScript, experto en programación orientada a objetos, herencia, manejo de fechas, asincronía, validación de datos, debugging avanzado y buenas prácticas.
Tu tarea es revisar mi código, identificar absolutamente todos los errores que puedan causar fallos o comportamientos incorrectos, explicar por qué ocurren y entregar una versión corregida, optimizada y totalmente funcional.

---

## Contexto

Estoy cargando empleados desde un servidor simulado, convirtiéndolos en instancias de una clase, calculando años trabajados, aumentando salario y generando estadísticas.
El código contiene múltiples errores graves relacionados con:

- Propiedades mal escritas  
- Herencia incorrecta (super incompleto)  
- Fechas mal procesadas  
- Métodos incorrectos  
- Tipos mal manejados (strings como números)  
- Errores en reduce  
- Asincronía mal manejada  
- Datos inconsistentes de la API  
- Comparaciones inválidas  
- Cálculos incorrectos de años y salarios  

Necesito que los detectes todos y los soluciones.

---

## Código con el error

    class Persona {
      constructor(nombre, edad) {
        this.name = nombre;
        this.edadd = edad;
      }
    
      info() {
        return `${this.nombre.toUppercase()} — ${this.edad} años`;
      }
    }
    
    class Empleado extends Persona {
      constructor(nombre, edad, salario, fechaIngreso) {
        super(nombre);
        this.salario = salario;
        this.fechaIngreso = fechaIngreso;
      }
    
      añosTrabajados() {
        const inicio = new Date(this.fechaDeIngreso);
        const hoy = new Date;
        return hoy.getFullYear - inicio.getFullYear();
      }
    
      aumentarSalario(porcentaje) {
        if (porcentaje < 0) throw new Error("Porcentaje negativo");
        this.salario = this.salario + (this.salario * porcentaje.toUpperCase());
      }
    }
    
    async function cargarEmpleados() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve([
            { nombre: "Felipe", edad: 17, salario: 1200, fechaIngreso: "2022-03-10" },
            { name: "Ana", edad: "23", salario: "900", fechaInicio: "2020-01-01" },
            { nombre: "Luis", edad: 30, sueldo: 1500, fechaIngreso: "2021-05-22" }
          ]);
        }, 500);
      });
    }
    
    function convertir(lista) {
      return lista.map(e =>
        new Empleado(e.nombre, e.edad, e.salario, e.fechaIngreso)
      );
    }
    
    async function procesar() {
      const datos = cargarEmpleados();
    
      if (datos === []) {
        throw new Error("No hay empleados");
      }
    
      const empleados = convertir(datos);
    
      empleados.forEach(e => {
        const años = e.añosTrabajados();
        if (años > 1) {
          e.aumentarSalario("0.1");
        }
      });
    
      const totalSalarios = empleados.reduce((acc, e) => acc + e.salario.toFixed(2), 0);
    
      console.log("Empleados procesados:", empleados.map(e => e.info()));
      console.log("Total salarios:", totalSalarios);
    }
    
    procesar();

---

## Lo que necesito que hagas

- Detectar **todos los errores** del código:
  - Propiedades incorrectas (`name`, `edadd`, `fechaDeIngreso`, `fechaInicio`, `sueldo`, etc.)  
  - Métodos incorrectos (`toUppercase`, `toUpperCase` mal aplicado)  
  - Herencia mal implementada (`super(nombre, edad)` faltante)  
  - Manejo incorrecto de fechas  
  - Comparaciones inválidas  
  - Errores en cálculos (años, salarios, reduce)  
  - Tipos incorrectos (strings en cálculos)  
  - Errores de asincronía (faltan `await`)  
  - Datos inconsistentes provenientes de la API  
  - Conversión incorrecta al crear instancias  
  - Validaciones mal hechas  

- Explicar **cada error con detalle**, indicando la causa y la solución correcta.
- Entregar un **código corregido, seguro y totalmente funcional**.
- Dar **recomendaciones profesionales** para evitar estos errores.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica  
3. Código corregido completo  
4. Recomendaciones finales  

# PROMT 12 

Actúa como un Desarrollador Senior en JavaScript, experto en orientación a objetos, estructuras de datos (Set, Map), asincronía, validación, debugging avanzado y buenas prácticas.
Tu tarea es analizar mi código, identificar absolutamente todos los errores, explicar por qué ocurren y generar una versión corregida, optimizada y totalmente funcional.

---

## Contexto

Estoy trabajando con un sistema que maneja categorías y productos usando clases y estructuras como Set, Map y funciones recursivas.
El código presenta múltiples errores graves en:

- uso incorrecto de `Set`,  
- métodos inexistentes,  
- propiedades mal escritas,  
- recursión infinita,  
- validaciones mal hechas,  
- reduce mal implementado,  
- datos inconsistentes,  
- asincronía mal manejada,  
- conversión incorrecta al crear instancias,  
- comparación lógica inválida,  
- errores en acceso a propiedades dinámicas.

Necesito que detectes todos los errores y me entregues una solución completa.

---

## Código con el error

    class Categoria {
      constructor(nombre, productos) {
        this.nombre = nombre;
        this.productos = new Set(productos);
      }
    
      agregarProducto(p) {
        if (this.productos.includes(p)) {
          console.log("Producto ya existe");
        } else {
          this.productos.push(p);
        }
      }
    
      totalProductos() {
        return this.productos.lenght;
      }
    }
    
    async function obtenerCategorias() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve([
            { nombre: "Tecnologia", productos: ["Laptop", "Mouse", 123] },
            { name: "Ropa", items: ["Camisa", "Pantalon"] },
            { nombre: "Hogar", productos: "Silla" }
          ]);
        }, 400);
      });
    }
    
    function convertir(categorias) {
      return categorias.map(c => new Categoria(c.nombre, c.productos));
    }
    
    function contarTotal(categorias) {
      return categorias.reduce((acc, c) => acc + c.totalProductos().toFixed(), 0);
    }
    
    function buscarRecursivo(mapa, clave) {
      if (mapa.clave) return mapa[clave];
    
      return buscarRecursivo(mapa, clave);
    }
    
    async function main() {
      const data = obtenerCategorias();
    
      if (!data || data.size === 0) {
        throw new Error("No hay categorías");
      }
    
      const categorias = convertir(data);
    
      const mapa = new Map();
      categorias.forEach(c => mapa.set(c.nombre.toLowerCase(), c));
    
      const hogar = buscarRecursivo(mapa, "hogar");
    
      const total = contarTotal(categorias);
    
      console.log("Categoría hogar:", hogar);
      console.log("Total de productos:", total);
    }
    
    main();

---

## Lo que necesito que hagas

- Detectar **todos los errores** del código:
  - Uso incorrecto de Set (`includes`, `push`, etc.)
  - Propiedades mal escritas (`lenght`, `clave`, etc.)
  - Datos inconsistentes (`items`, string en lugar de array)
  - Recursión infinita en `buscarRecursivo`
  - Acceso incorrecto a propiedades dinámicas
  - Reduce mal implementado
  - toFixed aplicado a valores incorrectos
  - Asincronía mal manejada (falta de `await`)
  - Validaciones incorrectas (`data.size`)
  - Conversión incorrecta en `convertir`
  - Errores lógicos en agregar producto

- Explicar **cada error**, por qué ocurre, qué lo causa y cómo corregirlo.
- Entregar una **versión completa, corregida y totalmente funcional** del código.
- Dar **recomendaciones profesionales** para evitar errores similares en el futuro.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica  
3. Código corregido completo  
4. Recomendaciones finales  

# PROMT 13

Actúa como un Desarrollador Senior en JavaScript, experto en programación orientada a objetos, manejo de JSON, generadores, validación de datos, debugging avanzado y buenas prácticas.
Tu tarea es revisar mi código, detectar absolutamente todos los errores que puedan causar fallos o comportamientos incorrectos, explicar por qué ocurren y entregar una versión corregida, optimizada y totalmente funcional.

---

## Contexto

Estoy simulando la obtención de tareas desde un servidor.  
Luego convierto esas tareas a instancias de una clase, utilizo un generador de índices, almaceno las tareas en un mapa y proceso cuáles están completadas.
El código contiene múltiples errores graves en:

- nombres de propiedades incorrectos,  
- mal uso de JSON,  
- generador mal definido,  
- Map mal utilizado,  
- propiedades inexistentes dentro de la clase,  
- toUppercase mal escrito,  
- tipos incorrectos (string vs boolean),  
- reduce mal implementado,  
- validaciones mal hechas,  
- asincronía mal manejada (faltan await),  
- inconsistencias de datos del servidor.

Necesito que los detectes todos y los soluciones.

---

## Código con el error

    class Tarea {
      constructor(id, titulo, completada) {
        this.idd = id;
        this.titulo = titulo;
        this.completada = completadaa;
      }
    
      marcar() {
        this.completada = !this.completada;
      }
    
      info() {
        return `${this.titulo.toUppercase()} — ${this.completada ? "SI" : "NO"}`;
      }
    }
    
    async function obtenerTareasDelServidor() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve(`[
            { "id": 1, "title": "Estudiar JS", "completada": false },
            { "id": 2, "titulo": "Lavar ropa", "completado": "true" },
            { "id": 3, "titulo": "Hacer ejercicio" }
          ]`);
        }, 300);
      });
    }
    
    function* generadorIndices(tareas) {
      let i = 0;
      while (i <= tareas.length) {
        yield i++;
      }
    }
    
    function convertirAClases(lista) {
      return lista.map(t => new Tarea(t.id, t.titulo, t.completada));
    }
    
    function procesarTareas(tareas) {
      const mapa = new Map();
      tareas.forEach(t => mapa[t.id] = t);
    
      const completadas = tareas.filter(t => t.completada === "true");
      const total = completadas.reduce((acc, t) => acc + t.completada.toFixed(2), 0);
    
      return { mapa, total };
    }
    
    async function main() {
      const respuesta = obtenerTareasDelServidor();
    
      const datos = JSON.parse(respuesta);
    
      if (datos === 0) {
        throw new Error("No hay tareas");
      }
    
      const tareas = convertirAClases(datos);
    
      const indices = generadorIndices(tareas);
      for (let i of indices) {
        console.log("Índice generado:", i);
      }
    
      const resultado = procesarTareas(tareas);
    
      console.log("Resultado:", resultado);
    }
    
    main();

---

## Lo que necesito que hagas

- Detectar **todos** los errores del código:
  - Propiedades incorrectas (`idd`, `completadaa`, `titulo`, `completado`, etc.)
  - Métodos incorrectos (`toUppercase`)
  - JSON mal procesado
  - Generador mal definido (`<= tareas.length`)
  - Uso incorrecto de `Map`
  - Tipos incorrectos en validaciones (`=== 0`)
  - Falta de `await`
  - Inconsistencias entre propiedades enviadas por el servidor y las esperadas
  - Reduce mal implementado
  - Conversión incorrecta al crear instancias
  - Comparaciones inválidas (`completada === "true"`)
  - Errores lógicos en el flujo completo

- Explicar claramente **cada error**, su causa y su impacto.
- Entregar una **versión corregida y completamente funcional** del código.
- Dar **recomendaciones profesionales** para evitar estos errores en el futuro.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica  
3. Código corregido completo  
4. Recomendaciones finales  

# PROMT 14 

Actúa como un Desarrollador Senior en JavaScript, experto en programación orientada a objetos, manejo de fechas, estructuras de datos, validación, asincronía, debugging avanzado y buenas prácticas.
Tu tarea es analizar mi código, detectar absolutamente todos los errores, explicar por qué ocurren y entregar una versión corregida, optimizada y totalmente funcional.

---

## Contexto

Estoy trabajando con pedidos que tienen productos, clientes y fechas.  
Obtengo estos pedidos desde un servidor simulado, los convierto en instancias de una clase y calculo totales y días desde que fueron realizados.

Sin embargo, el código contiene múltiples errores graves en:

- propiedades mal escritas,  
- métodos inválidos,  
- fechas mal procesadas,  
- reduce mal implementado,  
- asincronía incorrecta,  
- datos inconsistentes desde el servidor,  
- validaciones mal hechas,  
- conversión incorrecta al crear instancias,  
- cálculos numéricos incorrectos,  
- propiedades inexistentes en productos,  
- strings en lugar de arrays o números.

Necesito que los detectes y los soluciones.

---

## Código con el error

    class Pedido {
      constructor(id, cliente, productos, fecha) {
        this.id = id;
        this.cliente = cliente;
        this.productos = productos;
        this.fecha = fechaa;
      }
    
      total() {
        return this.productos.reduce((acc, p) => acc + p.precio.toUpperCase(), 0);
      }
    
      diasDesde() {
        const hoy = new Date;
        const f = new Date(this.fecha);
        return hoy.getDay - f.getDay();
      }
    
      info() {
        return `${this.cliente.toUppercase()} — $${this.total()}`;
      }
    }
    
    async function traerPedidos() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve([
            {
              id: 1,
              cliente: "Felipe",
              productos: [
                { nombre: "Mouse", precio: 50 },
                { nombre: "Teclado", cost: 120 }
              ],
              fecha: "2024-03-10"
            },
            {
              id: 2,
              name: "Ana",
              productos: "Laptop",
              fechaPedido: "2024-01-11"
            }
          ]);
        }, 500);
      });
    }
    
    function convertirPedidos(lista) {
      return lista.map(p => {
        const { id, cliente, productos, fecha } = p;
        return new Pedido(id, cliente, productos, fecha);
      });
    }
    
    async function procesar() {
      const datos = traerPedidos();
    
      if (datos == {}) {
        throw new Error("No hay datos");
      }
    
      const pedidos = convertirPedidos(datos);
    
      pedidos.forEach(p => {
        console.log("Días desde pedido:", p.diasDesde());
        console.log("Info:", p.info());
      });
    
      const totalGeneral = pedidos.reduce(
        (acc, p) => acc + p.total().toFixed(2),
        0
      );
    
      console.log("TOTAL GENERAL:", totalGeneral);
    }
    
    procesar();

---

## Lo que necesito que hagas

- Detectar **todos los errores** del código:
  - Propiedades incorrectas (`fechaa`, `name`, `productos` como string, `fechaPedido`, `cost` en productos).  
  - Métodos incorrectos (`toUppercase`, `toUpperCase` mal aplicado, `.getDay` vs `.getDate`).  
  - Cálculo incorrecto de días.  
  - Reduce mal implementado.  
  - Asincronía incorrecta (faltan `await`).  
  - Conversión incorrecta en `convertirPedidos`.  
  - Datos incompletos o inconsistentes.  
  - Validaciones inválidas (`datos == {}`).  
  - Operaciones numéricas incorrectas (`toFixed` sobre números dentro de reduce).  
  - Productos sin propiedad `precio`.  

- Explicar **cada error con detalle**, qué lo causa y cómo corregirlo.
- Entregar un **código corregido, seguro y totalmente funcional**.
- Dar **recomendaciones profesionales** para evitar que estos errores vuelvan a ocurrir.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica  
3. Código corregido completo  
4. Recomendaciones finales  

# PROMT 15 

Actúa como un Desarrollador Senior en JavaScript, experto en módulos ES, programación orientada a objetos, manejo de fechas, estructuras de datos como Set, validación, asincronía, debugging avanzado y buenas prácticas.
Tu tarea es revisar mi código, detectar absolutamente todos los errores graves, explicar por qué ocurren y entregar una versión corregida, optimizada y totalmente funcional.

---

## Contexto

Estoy simulando la obtención de pagos desde un servidor (módulo separado), convirtiéndolos en una clase y luego analizando los métodos de pago, el total y el promedio.
El código contiene errores en:

- importaciones mal escritas  
- propiedades inexistentes  
- métodos incorrectos  
- manejo incorrecto de fechas  
- Set mal utilizado  
- reduce mal implementado  
- asincronía incorrecta  
- datos inconsistentes del servidor  
- cálculos numéricos mal hechos  
- validaciones incorrectas  
- conversión incorrecta al crear instancias

Necesito que los detectes y los soluciones.

---

## Código con el error

**pagos.js**

    export async function obtenerPagos() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve([
            {
              id: 1,
              usuario: "Felipe",
              monto: 300,
              fecha: 1710000000,
              metodo: "tarjeta"
            },
            {
              id: 2,
              user: "Ana",
              valor: "500",
              fecha: "1715000000",
              metodoPago: "efectivo"
            },
            {
              id: 3,
              usuario: "Luis",
              montoDisponible: 200
            }
          ]);
        }, 600);
      });
    }

**app.js**

    import { obtenerPagos } from "./pagoss.js";
    
    class Pago {
      constructor(id, usuario, monto, fecha, metodo) {
        this.id = id;
        this.usuario = usuario;
        this.monto = montoo;
        this.fecha = fecha;
        this.metodo = metodo;
      }
    
      totalConImpuesto() {
        return this.monto + this.monto * 0.19.toFixed();
      }
    
      fechaFormateada() {
        const f = new Date(this.fecha * 1000);
        return f.toLocaleDateString.toUppercase();
      }
    
      info() {
        return `${this.usuario.toUppercase()} — $${this.totalConImpuesto()} — ${this.fechaFormateada()}`;
      }
    }
    
    function convertirPagos(lista) {
      return lista.map(p => {
        return new Pago(p.id, p.usuario, p.monto, p.fecha, p.metodo);
      });
    }
    
    function analizarPagos(pagos) {
      const metodos = new Set();
      pagos.forEach(p => metodos.push(p.metodo));
    
      const total = pagos.reduce((acc, p) => acc + p.totalConImpuesto().toFixed(2), 0);
    
      const promedio = total / pagos.lenght;
    
      return { metodos, total, promedio };
    }
    
    async function main() {
      const data = obtenerPagos();
    
      if (data === null || data.size === 0) {
        throw new Error("No hay datos");
      }
    
      const pagos = convertirPagos(data);
    
      pagos.forEach(p => console.log(p.info()));
    
      const resumen = analizarPagos(pagos);
    
      console.log("Resumen:", resumen);
    }
    
    main();

---

## Lo que necesito que hagas

- Detectar **todos los errores** del código:
  - Import incorrecto (`pagoss.js`)
  - Propiedades mal escritas (`montoo`, `valor`, `metodoPago`, `montoDisponible`)
  - Datos inconsistentes devueltos por el servidor
  - Métodos incorrectos (`toUppercase`, `toUpperCase`, `toFixed` mal aplicado)
  - Cálculos malos de impuesto
  - Manejo incorrecto de fechas (`toLocaleDateString` sin paréntesis)
  - Set mal usado (`push` no existe)
  - Reduce mal implementado
  - Divisiones mal hechas
  - Validaciones invalidas (`data.size`)
  - Asincronía incorrecta (faltan `await`)
  - Conversión incorrecta en `convertirPagos`
  - Comparaciones incorrectas (`== {}`)
  - Falta manejo de errores cuando faltan campos críticos
  - Números recibidos como strings
  - Propiedades que no existen en los objetos recibidos

- Explicar claramente **cada error**, su causa y cómo corregirlo.
- Entregar un **código corregido, seguro y totalmente funcional**.
- Dar **recomendaciones profesionales** para evitar estos errores a futuro.

---

## Formato de respuesta esperado

1. Errores detectados  
2. Explicación técnica  
3. Código corregido completo  
4. Recomendaciones finales  

