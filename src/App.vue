<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <!-- <RouterLink to="/">Home</RouterLink>
  <RouterLink to="/about">About</RouterLink> -->
    <v-layout class="test">
      <v-app-bar  id="app-bar" class="max-width-bar text-grey-darken-3" flat v-once>
        <template v-slot:prepend>
          <a href="#home">
            <v-img class="rounded-circle" width="30px" src="logo-3.png"></v-img>
          </a>
        </template>
        <template v-slot:append>
          <!-- <a class="text-black" href="#home">
            <v-btn flat class="text-capitalize text-grey-darken-4" density="compact" size="small">{{ $t('navbar.home') }}</v-btn>
          </a> -->
          <a class="text-black" href="#about">
            <v-btn flat class="text-capitalize text-grey-darken-4" density="compact" size="small">{{ $t('navbar.aboutMe') }}</v-btn>
          </a>
          <a class="text-black" href="#experience">
            <v-btn flat class="text-capitalize text-grey-darken-4" density="compact" size="small">{{ $t('navbar.experience') }}</v-btn>
          </a>
          <a class="text-black" href="#projects">
            <v-btn flat class="text-capitalize text-grey-darken-4" density="compact" size="small">{{ $t('navbar.projects') }}</v-btn>
          </a>
          <a class="text-black" href="#skills">
            <v-btn flat class="text-capitalize text-grey-darken-4" density="compact" size="small">{{ $t('navbar.skill') }}</v-btn>
          </a>
          <v-menu open-on-hover>
          <template v-slot:activator="{ props }">
            <v-btn
            outlined
            color="black"
            v-bind="props"
            size="small"
            density="compact"
            class="text-capitalize text-grey-darken-4"
          >
          {{ $t('navbar.languages') }}
            
          </v-btn>
          </template>
          <v-list>
            <v-list-item
            >
              <v-list-item-title v-for="locale in $i18n.availableLocales" :key="`locale-${locale}`" :value="locale" @click="$i18n.locale=locale">
                <v-btn
                outlined
                flat
                size="small"
                density="compact"
                class="text-capitalize text-grey-darken-4"
              >
                {{ $t(`navbar.languagesText.${locale}`) }}
            </v-btn>
              </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
          <!-- <v-icon class="text-grey-darken-4" icon="mdi-cart-outline" size="small"/> -->
        </template>
        
      </v-app-bar>
      <v-main>
        <RouterView />
      </v-main>
    </v-layout>
</template>


<style scoped lang="scss">
#app-bar {
  // border-bottom: 1px solid rgba(60, 60, 60, .29);
  :deep(.v-toolbar-title__placeholder) {
    color: #{map-get($grey, 'darken-4')};
    
  }
}

.test {
  height: 200vh;
}


@media #{map-get($display-breakpoints, 'lg-and-up')} {
  .max-width-bar {
    max-width: 1200px;
    display: block;
    margin: 0 auto;
  }

  .v-toolbar.v-toolbar--flat.v-toolbar--density-default {
    transform: translate(-50%, 0%)!important;
    left: 50%!important;
  }
}
</style>
