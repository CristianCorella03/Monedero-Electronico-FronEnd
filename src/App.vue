<template>
  <HeaderDinamico :title="pageTitle" :menuOptions="menuOptions" :headerColor="color" />
  <router-view />
</template>

<script>
import HeaderDinamico from './components/HeaderDinamico.vue';

export default {
  name: 'App',
  components: {
    HeaderDinamico
  },
  data() {

    if (window.location.href.includes('/usuario') ) {
      
      return {
        pageTitle: 'Web Clientes',
        color: '#DBF6CA',
        menuOptions: [
          { text: 'Mi Cuenta', link: '/usuario/cuenta' },
          { text: 'Comprar 🛒', link: '/usuario/comprar' },
          { text: 'Recargar', link: '/usuario/recargar' },
          { text: 'Mis Compras', link: '/usuario/compras' },
        ]
      };
    }

    else if (window.location.href.includes('/establecimiento')) {
      
      return {
        pageTitle: 'Local - Establecimiento',
        color: '#CAE2F6',
        menuOptions: [
          { text: 'Productos', link: '/establecimiento/productos' },
          { text: 'Registro Productos', link: '/establecimiento/registro-producto' },
          { text: 'Historial Ventas', link: '/establecimiento/historial-ventas' },
        ]
      };
    }

    else if (window.location.href.includes('/central')) {
      return {
        pageTitle: 'Central - Plataforma',
        color: '#FCD8D8',
        menuOptions: [
          { text: 'Establecimientos', link: '/central/establecimientos' },
          { text: 'Clientes', link: '/central/clientes' },
          { text: 'Registrar Clientes', link: '/central/registro-cliente' },
          { text: 'Registrar Establecimientos', link: '/central/registro-establecimiento' },
        ]
      };
    }

    else {
      return {
        pageTitle: 'Bienvenido a la Plataforma',
        color: '#fcfc83',
        menuOptions: []
      };
    }
  }
}
</script>