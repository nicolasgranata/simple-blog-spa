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
          value="light"
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
          value="dark"
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

  public created(): void {
    const theme = localStorage.getItem('theme');
    if (theme) {
      this.applyTheme(theme);
    }
  }

  public openThemeOptions(): void {
    this.openOptions = !this.openOptions;
  }

  public changeTheme(themeValue: string): void {
    this.applyTheme(themeValue);
    this.openOptions = !this.openOptions;
    const theme = localStorage.getItem('theme');
    if (!theme || theme !== themeValue) {
      localStorage.setItem('theme', themeValue);
    }
  }

  private applyTheme(themeValue: string): void {
    if (themeValue === 'dark') {
      document.body.classList.toggle('dark-mode');
      this.themeIcon = 'fa-solid fa-moon';
    } else {
      document.body.classList.remove('dark-mode');
      this.themeIcon = 'fa-solid fa-lightbulb';
    }
  }
}
</script>

<style scoped>
.theme-switch {
    --bg-color: #f9f9fb;
    --bg-color-hover: #cdcdcd;
    --option-text-color: #171c20;
    --theme-text-color: #637485;
    --box-shadow-color: 0px 1px 6px rgba(17, 14, 14, 0.404);

    --bg-color-dark-mode: #343434;
    --bg-color-hover-dark-mode: #0c0e10;
    --option-text-color-dark-mode: #cbcbcb;
    --box-shadow-color-dark-mode: 0px 1px 6px rgba(255, 255, 255, 0.7);

    position: relative;
    display: inline-block;
}

.theme-button {
    background: transparent;
    border-radius: 0.25rem;
    border-color: transparent;
}

.theme-button:hover {
    background-color: var(--bg-color-hover);
    cursor: pointer;
}

.dark-mode .theme-button:hover {
  background-color: var(--bg-color-hover-dark-mode);
}

.theme-text {
    font-weight: bold;
    color: var(--theme-text-color);
    font-size: 0.9rem;
}

.dark-mode .theme-text {
  color: var(--secondary-color-dark-mode);
}

.theme-menu {
    list-style: none;
    margin-top: 0.2rem;
    background-color: var(--bg-color);
    border-radius: 0.25rem;
    box-shadow: var(--box-shadow-color);
    width: max-content;
    padding: 0.5rem;
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
}

.dark-mode .theme-menu {
  background-color: var(--bg-color-dark-mode);
  box-shadow: var(--box-shadow-color-dark-mode);
}

.theme-option {
    color:var(--option-text-color);
    font-size: 0.9rem;
}

.dark-mode .theme-option {
  color: var(--option-text-color-dark-mode);
}

button span {
  pointer-events: none;
}
</style>
