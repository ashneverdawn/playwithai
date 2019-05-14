<template> 
    <nb-container>
        <nb-content>
            <nb-container class="loading-container">
                <text class="loading-text">Loading</text>
                <nb-spinner color="blue" />
            </nb-container>
        </nb-content>
    </nb-container>
</template>

<style>
.loading-container {
  flex: 1;
  background-color: white;
  align-items: center;
  justify-content: center;
}
.loading-text {
  color: blue;
  font-size: 30;
}
</style>

<script>
import Vue from "vue-native-core";
import { VueNativeBase } from "native-base";
Vue.use(VueNativeBase);

export default {
  props: {
    finishLoading: {
      Type: Function
    }
  },
  created: function() {
    this.loadFonts();
  },
  methods: {
    loadFonts: loadFonts
  }
};
async function loadFonts() {
    try {
        await Expo.Font.loadAsync({
        Roboto: require("native-base/Fonts/Roboto.ttf"),
        Roboto_medium: require("native-base/Fonts/Roboto_medium.ttf"),
        Ionicons: require("@expo/vector-icons/fonts/Ionicons.ttf")
        });
    } catch (error) {
        console.log("some error occured", error);
    }
    this.finishLoading()
}
</script>
