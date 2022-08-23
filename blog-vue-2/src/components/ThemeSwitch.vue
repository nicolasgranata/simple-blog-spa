<template>
  <div class='theme-switch'>
    <button v-on:click="openThemeOptions()" type="button" class="theme-button">
      <span class="theme-text">
        <font-awesome-icon v-bind:icon="themeIcon" />
        Theme
      </span>
    </button>
    <ul v-if="openOptions" class="theme-menu">
      <li>
        <button
          v-on:click="changeTheme($event.target.value)"
          type="button"
          class="theme-button"
          value="theme-light"
        >
          <span class="theme-option">
            <font-awesome-icon icon="fa-solid fa-lightbulb" />
            Light
          </span>
        </button>
      </li>
      <li>
        <button
          v-on:click="changeTheme($event.target.value)"
          type="button"
          class="theme-button"
          value="theme-dark"
        >
          <span class="theme-option">
            <font-awesome-icon icon="fa-solid fa-moon" />
            Dark
          </span>
        </button>
      </li>
    </ul>
  </div>
</template>

<script lang='ts'>
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class ThemeSwitch extends Vue {
  public openOptions = false;
  public themeIcon = 'fa-solid fa-lightbulb';

  public openThemeOptions(): void {
    this.openOptions = !this.openOptions;
  }

  public changeTheme(themeValue: string): void {
    document.body.classList.toggle('dark-mode');
    this.openOptions = !this.openOptions;
    this.themeIcon = themeValue === 'theme-light' ? 'fa-solid fa-lightbulb' : 'fa-solid fa-moon';
  }
}
</script>

<style scoped>
.theme-switch {
    position: relative;
    display: inline-block;
}

.theme-button {
    background: transparent;
    border-radius: 0.25rem;
    border-color: transparent;
}

.theme-button:hover {
    background-color: #cdcdcd;
    cursor: pointer;
}

.theme-text {
    font-weight: bold;
    color: #637485;
    font-size: 0.9rem;
}

.theme-menu {
    list-style: none;
    margin: 0;
    padding: 0;
    background-color: #f9f9fb;
    border-radius: 0.25rem;
    box-shadow: 0px 1px 6px rgba(43,42,51,.1);
    width: max-content;
    padding: 0.5rem;
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
}

.theme-option {
    color: #3d4853;
    font-size: 0.9rem;
}

button span {
  pointer-events: none;
}
</style>
