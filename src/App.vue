<template>
  <div id="app" class="app">
    <header class="menu-container">
      <input type="checkbox" id="openmenu" class="hamburger-checkbox">
      
      <div class="hamburger-icon">
        <label for="openmenu" id="hamburger-label">
          <span></span>
          <span></span>
          <span></span>
        </label>
      </div>

      <div class="menu-pane">
        <nav>
          <ul class="menu-links"></ul>

          <ul class="menu-links">
            <li>
              <router-link :to="{ name: 'home' }">Raphael Gauvain</router-link>
            </li>

            <li><router-link :to="{ name: 'home' }">Accueil</router-link></li>
            <li><router-link :to="{ name: 'about' }">Contact</router-link></li>
            <li><br></li>
          </ul>

          <ul class="menu-links">
            <li>
              <router-link :to="{ name: 'home' }">Projets</router-link>
            </li>

            <li><router-link :to="{ name: 'projet', params : { name : 'accor'} }">Accor Live Limitless</router-link></li>
            <li><router-link :to="{ name: 'projet', params : { name : 'seat'} }">SEAT</router-link></li>
            <li><router-link :to="{ name: 'projet', params : { name : 'volkswagen'} }">Volkswagen</router-link></li>
          </ul>
        </nav>
      </div>

      <div class="menu-body-text">
        <router-link :to="{ name: 'home' }"><img class="menu-logo" src="./assets/logo.png" alt="Raphael Gauvain Logo"></router-link>
        <h3>Portfolio</h3>
      </div>
    </header>

    <transition :name="transitionName">
      <router-view></router-view>
    </transition>
  </div>
</template>

<script>
import Rellax from  'rellax';

export default {
  name: 'app',

  data () {
    return {
      transitionName: 'slide-left'
    }
  },

  mounted() {
    this.body = new Rellax('.rellax');
    this.$el.querySelectorAll('a').forEach((el) => el.addEventListener('click', () => document.querySelector('#openmenu').checked = false))
  },

  watch: {
    '$route' (to, from) {
      const toDepth = to.path.split('/').length
      const fromDepth = from.path.split('/').length
      this.transitionName = toDepth < fromDepth ? 'slide-right' : 'slide-left'
    }
  }
}
</script>