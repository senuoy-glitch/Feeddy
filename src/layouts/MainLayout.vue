<template>
  <q-layout view="hHh lpR fFf">

    <q-header reveal class="bg-primary text-white" height-hint="98">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          Title
        </q-toolbar-title>
      </q-toolbar>

      <q-tabs align="left">
        <q-route-tab to="/page1" label="Send Feedback" />
        <q-route-tab to="/page2" label="Request Feedback" />
        <q-route-tab to="/page3" label="Recognize" />
      </q-tabs>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" side="left" overlay behavior="desktop">
      <!-- drawer content -->
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer reveal class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          <div>Title</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const leftDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
}
</script>
<template>
  <div class="q-pa-md q-gutter-md">
    <q-btn color="teal">
      <q-icon left size="3em" name="map" />
      <div>Label</div>
    </q-btn>

    <q-btn round>
      <q-avatar size="42px">
        <img src="https://cdn.quasar.dev/img/avatar2.jpg">
      </q-avatar>
    </q-btn>

    <q-btn color="indigo" no-caps>
      Multiline<br>Button
    </q-btn>

    <q-btn color="deep-orange" push>
      <div class="row items-center no-wrap">
        <q-icon left name="map" />
        <div class="text-center">
          Custom<br>Content
        </div>
      </div>
    </q-btn>
  </div>
</template>