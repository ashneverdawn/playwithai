<template>
  <loading v-if="!appIsReady" :finishLoading="finishLoading"/>
  <app-navigation v-else />
</template>

<script>
import { StackNavigator } from "vue-native-router";
import Loading from "./src/loading.vue";
import SelectGameScreen from "./src/screens/selectGame.vue";
import EditGameScreen from "./src/screens/editGame.vue";
import EditPieceScreen from "./src/screens/editPiece.vue";
import GameOptionsScreen from "./src/screens/gameOptions.vue";
import PlayGameScreen from "./src/screens/playGame.vue";

const AppNavigation = StackNavigator(
  {
    Home: { screen: SelectGameScreen },
    GameOptions: { screen: GameOptionsScreen },
    EditGame: { screen: EditGameScreen },
    EditPiece: { screen: EditPieceScreen },
    PlayGame: { screen: PlayGameScreen }
  },
  {
    initialRouteName: 'Home',
    headerMode: "none"
  }
);
export default {
  components: { Loading, AppNavigation },
  data: function() {
    return {
      appIsReady : false
    };
  },
  methods: {
    finishLoading : function() { this.appIsReady = true; }
  }
};
</script>