<template lang="pug">
  section.hero.is-success
    .hero-head
      header.navbar
        .container
          .nav-start
            .nav-item
              strong 📻 Lw Music
          .nav-end.nav-menu
            router-link.nav-item(to="search") Buscar
            router-link.nav-item(to="about") Nosotros
    .hero-body
      .container.has-text-centered
        h1.title Lw Music
        h2.subtitle Canciones que están Vue-nísimas
</template>
