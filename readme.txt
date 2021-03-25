create nuxt project
npx create-nuxt-app "nuxt name"

run nuxt service
npm run dev

Assets -> nuxt tiene un precompilador 
Componentes -> vue
layouts -> paginas vistas <Nuxt>
middleware -> funciones antes de que se renderize una pagina / layouts
pages -> vistas del proyectos (directorios)
plugins -> librerias o archivos antes de que se monte la raiz del proyecto ejemplo axios
static -> informacion estatica del sitio
store -> almacenamiento de vuex
-----------------------------
nuxt.config.js -> configuracion del sitio

----------------------------------------
nuxt como aplicacion universal (bueno para el seo)
nuxt como aplicacion spa (client side rendering)
nuxt como aplicacion estatica (carga de la vista en prerenderizada)

rutas
en pages se pueden crear archivos vue con el nombre que se llama la ruta ejemplo
about.vue
sin embargo tambien se pueden crear folders pero estos se tienen que llamar como se llamaria la ruta y su contenido index.vue


ir a una ruta 
this.$router.push('/routername')

rutas con parametros

se utiliza _ para agregar parametros
por ejemplo
_id / index.vue

si se requieren mas parametros se van creando subcarpetas
_id/id2/index.vue

pasar datos como query
<nuxt-link :to="{ path: '/posts/1/13', query: { ...personalData } }">

se accesa mediante
    console.info(this.$route.params);
    console.info(this.$route.query);

    obtener informacion de la ruta actual
    console.log(this.$router.currentRoute);

    ejemplo de envio de datos
    sendData() {
      this.$router.push({
        name: "posts-id-id2",
        params: {
          id: 12,
          id2: 432,
          ...this.personalData,
        },
      });
    },

    -----------------------------------------------
    validate(data) {
    console.log(data);
    return true;
  },
  es una funcion en nuxt que nos permite validar antes de que se carge el componente
  retorna true o false dependiendo de que se necesite si es false no cargara

  rutas hijo child
  en una ruta padre mostrar rutas hijas
    usamos nuxt-child y la ruta que contendra el nuxt-child se debe de llamar igual que la carpeta donde estaran las rutas hijas