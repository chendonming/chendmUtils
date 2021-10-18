<template>
  <q-layout view="lHh lpR fFf">
    <q-header reveal elevated class="bg-primary text-white" height-hint="98">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="left = !left"/>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          桌面工具
        </q-toolbar-title>
      </q-toolbar>

      <q-tabs align="left">
        <q-route-tab to="/todo" label="TODO清单"/>
        <!--        <q-route-tab to="/page2" label="Page Two"/>-->
        <!--        <q-route-tab to="/page3" label="Page Three"/>-->
      </q-tabs>
    </q-header>

    <q-drawer show-if-above v-model="left" side="left" bordered>
      <q-list>
        <q-item v-for="(item, index) in list" :key="index" clickable v-ripple>
          <q-item-section>
            {{ item.label }}
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container style="height: 100vh;overflow: auto;">
      <div class="full-height overflow-auto" style="padding: 20px;">
        <router-view/>
      </div>
    </q-page-container>

    <q-footer reveal elevated class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          chendm utils
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      left: false,
      list: [
        {
          label: 'TODO清单',
          path: '/todo',
        },
        {
          label: 'json格式化',
          path: '/tojson',
        },
      ],
    };
  },
};
</script>
