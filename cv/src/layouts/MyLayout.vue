<template>
  <q-layout view="hHh lpR fFf">
    <q-header class="lt-lg" elevated>
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
    <q-header class="gt-md bg-transparent" >
      <div class="row ">
      <div class="col-3">
        <img class="q-ml-md" src="public/photo-output.png" alt="" style="width: 80px; height: 80px;">
      </div>
      <div class="col-9 text-center">
        <nav>
          <ul>
            <li><a href="">about</a></li>
            <li><a href="">contact</a></li>
            <li><a href="">servise</a></li>
            <li><a href="">about</a></li>
          </ul>
        </nav>
      </div>
     </div>
    </q-header>

    <!-- <q-drawer
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
      </q-drawer> -->
      <q-drawer
        v-model="drawer"
        :width="200"
        :breakpoint="500"
        overlay
        bordered
        :class="$q.dark.isActive ? 'bg-grey-9' : 'bg-grey-3'"
      >
        <q-scroll-area class="fit">
          <q-list>

            <template v-for="(menuItem, index) in menuList" :key="index">
              <q-item clickable :active="menuItem.label === 'Outbox'" v-ripple>
                <q-item-section avatar>
                  <q-icon :name="menuItem.icon" />
                </q-item-section>
                <q-item-section>
                  {{ menuItem.label }}
                </q-item-section>
              </q-item>
              <q-separator :key="'sep' + index" v-if="menuItem.separator" />
            </template>

          </q-list>
        </q-scroll-area>
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
