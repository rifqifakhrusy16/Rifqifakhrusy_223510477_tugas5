<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-info text-white" height-hint="98">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title>
          <q-avatar>
            <img src="https://i.pinimg.com/564x/61/38/c6/6138c673e78ec68cea5cdcda0f8a0b9a.jpg">
          </q-avatar>
          Sepatuku
        </q-toolbar-title>

        <q-btn dense flat round icon="menu" @click="toggleRightDrawer" />
      </q-toolbar>

      <q-tabs align="left">
        <q-route-tab to="/page1" label="Beranda" />
      </q-tabs>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <div class="q-pa-md row items-start q-gutter-md">
    <q-card class="my-card">
      <q-card-section class="bg-primary text-white">
        <div class="text-h6">Sepatu Adidas</div>
        <div class="text-subtitle2">by Adolf Dassler </div>
      </q-card-section>

      <q-separator />

      <q-card-actions align="right">
        <q-btn flat>GO TO STORE</q-btn>
        <q-btn flat>SHOES FAMILIAR</q-btn>
      </q-card-actions>
    </q-card>

    <q-card class="my-card">
      <q-card-section class="bg-purple text-white">
        <div class="text-h6">Sepatu Docrmart</div>
        <div class="text-subtitle2">by Dr.Martens</div>
      </q-card-section>

      <q-card-actions align="around">
        <q-btn flat>GO TO STORE</q-btn>
        <q-btn flat>SHOES FAMILIAR</q-btn>
      </q-card-actions>
    </q-card>

    <q-card class="my-card">
      <q-card-section class="bg-teal text-white">
        <div class="text-h6">Sepatu Converse</div>
        <div class="text-subtitle2">by  NIKE, Inc</div>
      </q-card-section>

      <q-card-actions vertical align="right">
        <q-btn flat>GO TO STORE</q-btn>
        <q-btn flat>SHOES FAMILIAR</q-btn>
      </q-card-actions>
    </q-card>
</div>
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
      <div class="q-pa-md row items-start q-gutter-md">
    <q-card class="my-card">
      <img src="https://i.pinimg.com/564x/d8/c1/23/d8c123fe5b3cfeccfbca8c74443ec52b.jpg">
      <div class="absolute-bottom text-subtitle2 text-center"></div>

      <q-card-section>
        <div class="text-center">Sepatu Samba</div>
        
      </q-card-section>

      <q-card-section class="q-pt-none">
        {{ lorem }}
      </q-card-section>
    </q-card>

    <q-card class="my-card">
      <q-img src="https://i.pinimg.com/564x/f5/b4/6d/f5b46d273f3c61098c8de67d34e91acb.jpg">
        <div class="absolute-bottom text-subtitle2 text-center">
          Sepatu Vans
        </div>
      </q-img>
    </q-card>

    <q-card class="my-card">
      <q-img src="https://i.pinimg.com/564x/97/c2/c4/97c2c4d1035d52eacf565ba3e27275e0.jpg">
        <div class="absolute-bottom text-subtitle2 text-center">
          Sepatu Docmart
        </div>
      </q-img>

      <q-card-section>
        {{ lorem }}
      </q-card-section>
    </q-card>

    <q-card class="my-card">
      <q-img src="https://i.pinimg.com/736x/c3/fe/e0/c3fee0d8820a0d4f119a2ba73aa91149.jpg">
        <div class="absolute-bottom text-subtitle2 text-center">
          Sepatu Nike
        </div>
      </q-img>
    </q-card>

    <q-card class="my-card">
      <q-img src="https://i.pinimg.com/564x/33/54/c9/3354c9e61dd9fb339d2fd77b1468a30e.jpg">
        <div class="absolute-bottom text-subtitle2 text-center">
          Sepatu Adidas
        </div>
      </q-img>
    </q-card>

    <q-card class="my-card">
      <q-img src="https://i.pinimg.com/736x/3a/3a/c8/3a3ac843ea0d97911b0516a7d634e4bb.jpg">
        <div class="absolute-bottom text-subtitle2 text-center">
          Converse High
        </div>
      </q-img>
    </q-card>
  </div>
    </q-drawer>

    <q-page-container>
      <div class="q-pa-md">
        <q-carousel
          animated
          v-model="slide"
          arrows
          navigation
          infinite
        >
          <q-carousel-slide :name="1" img-src="https://i.pinimg.com/564x/75/4b/53/754b539fc0c977ee37e49f8648051386.jpg" />
          <q-carousel-slide :name="2" img-src="https://i.pinimg.com/736x/a6/33/5b/a6335bdfca551612e6ead21072eaee95.jpg" />
          <q-carousel-slide :name="3" img-src="https://i.pinimg.com/736x/3a/3a/c8/3a3ac843ea0d97911b0516a7d634e4bb.jpg" />
          <q-carousel-slide :name="4" img-src="https://i.pinimg.com/564x/97/c2/c4/97c2c4d1035d52eacf565ba3e27275e0.jpg" />
          <q-carousel-slide :name="5" img-src="https://i.pinimg.com/736x/3a/3a/c8/3a3ac843ea0d97911b0516a7d634e4bb.jpg" />
        </q-carousel>
      </div>
      <router-view />
    </q-page-container>

    <q-footer elevated class="bg-grey-8 text-white">
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
  setup() {
    const leftDrawerOpen = ref(false)
    const rightDrawerOpen = ref(false)
    const slide = ref(1)

    const toggleLeftDrawer = () => {
      leftDrawerOpen.value = !leftDrawerOpen.value
    }

    const toggleRightDrawer = () => {
      rightDrawerOpen.value = !rightDrawerOpen.value
    }

    return {
      leftDrawerOpen,
      rightDrawerOpen,
      slide,
      toggleLeftDrawer,
      toggleRightDrawer
    }
  }
}
</script>

<style scoped>
.q-card {
  width: 250px;
}
</style>
