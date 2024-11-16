
# 📝 Prueba Técnica: Consumo de API con Vue.js

## 🎯 **Descripción del Proyecto**
Esta prueba técnica tiene como objetivo evaluar tus conocimientos en **Vue.js**, específicamente en el consumo de APIs y la creación de componentes. Deberás crear una aplicación web sencilla que muestre una lista de usuarios obtenida de una API pública y permita ver los detalles de cada usuario al hacer clic en ellos.

## ⚙️ **Requisitos del Proyecto**
- Utilizar **Vue.js** (Vue 2 o Vue 3, según tu preferencia).
- Crear una interfaz básica con **HTML y CSS** (puedes usar frameworks como Tailwind CSS o Bootstrap, opcional).
- Consumir datos desde una API pública utilizando **fetch** o **axios**.
- Manejar el estado de carga y posibles errores al consumir la API.
- Implementar componentes para estructurar la aplicación.

## 🌐 **API Pública a Utilizar**
La API que usarás es [JSONPlaceholder](https://jsonplaceholder.typicode.com/), un servicio gratuito para pruebas de desarrollo.

- **Lista de Usuarios**: `https://jsonplaceholder.typicode.com/users`

## 🛠️ **Instrucciones**
1. [x] Crea un proyecto de Vue.js usando **Vite** o **Vue CLI**.
2. [x] Consume la API para obtener la lista de usuarios.
3. [x] Muestra los usuarios en una lista, incluyendo el nombre y correo electrónico de cada uno.
4. [x] Al hacer clic en un usuario, muestra una vista con los detalles del usuario:
   - Nombre
   - Nombre de usuario (username)
   - Correo electrónico
   - Teléfono
   - Sitio web
   - Dirección (calle y ciudad)
5. Agrega un **indicador de carga** mientras se obtienen los datos.
6. Muestra un **mensaje de error** si la API falla.

## 📂 **Estructura Sugerida del Proyecto**
```
src/
├── components/
│   ├── UserList.vue
│   └── UserDetail.vue
├── App.vue
├── main.js
└── styles.css (opcional)
```

## 🚀 **Iniciar el Proyecto**
Sigue estos pasos para configurar e iniciar tu proyecto:

1. **Clonar el repositorio:**
   ```bash
   git clone <tu-repositorio>
   ```

2. **Instalar dependencias:**
   ```bash
   npm install
   ```

3. **Iniciar el servidor de desarrollo:**
   ```bash
   npm run dev
   ```

4. **Visitar la aplicación en el navegador:**
   - Abre [http://localhost:5173](http://localhost:5173).

## ✨ **Criterios de Evaluación**
- **Consumo de API**: Uso correcto de `fetch` o `axios` para obtener los datos.
- **Interacción**: Implementación de eventos para ver los detalles del usuario.
- **Gestión del Estado**: Uso adecuado del estado local para manejar los datos.
- **Manejo de Errores**: Mostrar mensajes de error si la API falla.
- **Diseño**: Interfaz sencilla, limpia y responsiva.
- **Buenas Prácticas**: Código limpio y organizado, uso de componentes.

## 🌟 **Extras (Opcional)**
- Agregar una **barra de búsqueda** para filtrar usuarios por nombre.
- Implementar **paginación** para la lista de usuarios.
- Agregar **diseño responsivo**.

## 📬 **Entrega**
1. Sube tu proyecto a un repositorio público en **GitHub**.
2. Incluye este archivo `README.md` con instrucciones claras.
3. Comparte el enlace al repositorio para revisión.

## 💡 **Recursos Útiles**
- [Documentación de Vue.js](https://vuejs.org/guide/introduction.html)
- [API JSONPlaceholder](https://jsonplaceholder.typicode.com/)
- [Vite](https://vitejs.dev/guide/)

---

¡Buena suerte y feliz codificación! 🚀💻
