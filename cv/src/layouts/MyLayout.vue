<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated>
      <q-toolbar class=" text-white custom-toolbar" style="height: 100px; background-color: #1A1A1A;">
        <!-- <q-btn class="q-pr-md q-pl-xs" flat round icon="menu" @click="toggleLeftDrawer" /> -->
        <!-- <q-separator dark vertical inset /> -->
        <q-avatar style="width: 50px; height: 50px;">
        <img src="/public/photo-output.png" style="width: 50px; height: 50px;" >
      </q-avatar>

      <q-space />
      <q-btn flat @click="drawer = !drawer" round dense icon="menu" />

      </q-toolbar>
    </q-header>

    <!-- <q-drawer v-model="leftDrawerOpen" show-if-above side="left" overlay>
      <q-list>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="home" />
          </q-item-section>
          <q-item-section>
            خانه
          </q-item-section>
        </q-item>

        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="info" />
          </q-item-section>
          <q-item-section>
            درباره ما
          </q-item-section>
        </q-item>

        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="contact_page" />
          </q-item-section>
          <q-item-section>
            تماس با ما
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer> -->
    <q-drawer
        v-model="drawer"
        show-if-above
        :width="200"
        :breakpoint="400"
      >
        <q-scroll-area style="height: calc(100% - 150px); margin-top: 150px; border-right: 1px solid #ddd;background: #CFCFCF;">
          <q-list padding>
            <q-item clickable v-ripple>
              <q-item-section avatar>
                <q-icon  name="home" class="drawer-item" />
              </q-item-section>

              <q-item-section class="drawer-item fontf1" >
                home
              </q-item-section>
            </q-item>

            <q-item clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="person" class="drawer-item"/>
              </q-item-section>

              <q-item-section class="drawer-item fontf1">
                about
              </q-item-section>
            </q-item>

            <q-item clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="send" class="drawer-item"/>
              </q-item-section>

              <q-item-section class="drawer-item fontf1">
                Send
              </q-item-section>
            </q-item>

            <q-item clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="drafts" class="drawer-item"/>
              </q-item-section>

              <q-item-section class="drawer-item fontf1">
                Drafts
              </q-item-section>
            </q-item>
          </q-list>
        </q-scroll-area>

        <q-img class="absolute-top" src="/public/bg-drawer.png" style="height: 150px">
          <div class="absolute-bottom bg-transparent">
            <q-avatar size="56px" class="q-mb-sm">
              <img src="/public/avatarDrawer1.png">
            </q-avatar>
            <div class="text-weight-bold">amirhossein1</div>
            <div>@amirhoseeintakhti</div>
          </div>
        </q-img>
      </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      drawer: ref(false)
    }
  }
}
</script>
<style>
.fontf1{
  font-family: 'kalameh-Regular';
}
</style>
