<script setup>
import { ref } from 'vue';
import { useTheme } from 'vuetify';

const isDark = ref(false)

const { themes, setTheme } = useTheme()
// const initialThemeColors = JSON.parse(JSON.stringify(themes.value.light.colors))
// const colors = ['primary', 'secondary', 'success', 'info', 'warning', 'error']

const setPrimaryColor = color => {
  console.log("Color: ", color)
  themes.value.light.colors.primary = color
  themes.value.dark.colors.primary = color

  setTheme('light', themes.value.light)
  setTheme('dark', themes.value.dark)
}
</script>

<template>
  <v-app :theme="isDark ? 'dark' : 'light'">
    <v-main>
      <v-container>
        <div class="d-flex" style="column-gap: 1rem">
          <v-btn @click="setPrimaryColor('#000')" color="primary">Primary</v-btn>
          <v-btn color="primary" :icon="isDark ? 'mdi-weather-night' : 'mdi-weather-sunny'" @click="isDark = !isDark">
          </v-btn>
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>
