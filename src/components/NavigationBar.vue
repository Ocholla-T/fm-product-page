<template>
  <header>
    <!-- This is the hamburger menu and logo -->
    <div>
      <div class="hamburger-menu" aria-label="Open the menu" @click="openMenu"></div>
      <img src="../assets/images/logo.svg" alt="This is the sneakers logo" />
    </div>

    <!-- This is the menu that pops up on mobile and tablet devices -->
    <aside ref="sideMenu" class="side-menu">
      <img src="../assets/images/icon-close.svg" alt="Close the menu" @click="closeMenu" />
      <a href="" class="link">Collections</a>
      <a href="" class="link">Men</a>
      <a href="" class="link">Women</a>
      <a href="" class="link">About</a>
      <a href="" class="link">Contact</a>
    </aside>

    <!-- This is the shopping cart and avatar -->
    <div>
      <img src="../assets/images/icon-cart.svg" alt="This is the shopping cart" />
      <img src="../assets/images/image-avatar.png" alt="This is your avatar" />
    </div>
  </header>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

let sideMenu = ref();

function openMenu() {
  sideMenu.value.style.display = 'grid';
}
function closeMenu() {
  sideMenu.value.style.display = 'none';
}
</script>

<style lang="scss" scoped>
@use '../assets/styles/main';

header {
  display: flex;
  justify-content: space-between;
  padding: 1.5rem;
  position: relative;
  z-index: 0;

  > div:first-of-type {
    align-items: center;
    display: flex;

    > img {
      margin-left: 1.25rem;
      width: 7.875rem; //126px
    }
  }

  > div:last-of-type {
    align-items: center;
    display: flex;

    > img {
      cursor: pointer;
    }

    > img:last-of-type {
      aspect-ratio: 1;
      height: 1.625rem;
      margin-left: 1.25rem;
    }
  }
}
</style>
