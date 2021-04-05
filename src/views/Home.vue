<template>
  <div class="body-container">
    <div class="grid-container">
        <router-link class="project-anchor" :to="{ name: 'projet', params : { name : 'accor' } }">
          <p>Octobre 2017</p>
          <hr>
          <h3 class="home__project-title">Accor Live Limitless</h3>
          <p class="home__project-description">
            Mission longue, toujours en cours.
            <br><br>
            Travail sur le couloir de réservation d'une chambre d'hôtel.
            <br>
            <br>
            <router-link :to="{ name: 'projet', params : { name : 'accor'} }">En savoir plus !</router-link>
          </p>
        </router-link>

        <div class="home__project-illustration">
          <img class="menu-logo" src="../assets/accor-logo.png" alt="Accor Live Limitless logo">
        </div>
      </div>

      <hr>

      <div class="grid-container">
        <router-link class="project-anchor" :to="{ name: 'projet', params : { name : 'seat' } }">
          <p>Janvier 2020</p>
          <hr>
          <h3 class="home__project-title">Seat</h3>
          <p class="home__project-description">
            Missions ponctuelles.
            <br><br>
            <router-link :to="{ name: 'projet', params : { name : 'seat'} }">En savoir plus !</router-link>
          </p>
        </router-link>

        <div class="home__project-illustration">
          <img class="menu-logo" src="../assets/seat-illustration.png" alt="Seat logo">
        </div>
      </div>

      <hr>

      <div class="grid-container">
        <router-link class="project-anchor" :to="{ name: 'projet', params : { name : 'volkswagen' } }">
          <p>Mars 2020</p>
          <hr>
          <h3 class="home__project-title">Volkswagen</h3>
          <p class="home__project-description">
            Missions ponctuelles.
            <br><br>
            <router-link :to="{ name: 'projet', params : { name : 'volkswagen'} }">En savoir plus !</router-link>
          </p>
        </router-link>

        <div class="home__project-illustration">
          <img class="menu-logo" src="../assets/vw-illustration.png" alt="Seat logo">
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Home'
}
</script>

<style lang="scss">
.home {
  &__item {
    display: flex;
    margin: 0 0 29px;

    &__content {
      position: relative;
      display: flex;
      align-items: center;
      width: 68%;

      &__date {
        font-family: 'Bitter', serif;
        flex-shrink: 0;
        width: 223px;
      }

      &__title {
        font-size: 23px;
        line-height: 1.3em;
        position: relative;
        margin: 0;
      }
    }
    
    &__image {
      width: 32%;

      img {
        display: none;
        height: auto;
        max-width: 100%;
      }
    }
  }
}
</style>
