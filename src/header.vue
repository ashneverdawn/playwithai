<template>
    <nb-header>
      <nb-left>
        <nb-button transparent v-if="navigation!==undefined" :on-press="goBack">
            <nb-icon name='arrow-back' />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>{{title}}</nb-title>
        <nb-subtitle>{{subtitle}}</nb-subtitle>
      </nb-body>
      <nb-right/>
    </nb-header>
</template>

<script>
export default {
  props: {
    title: {
      Type: Object
    },
    subtitle: {
      Type: Object
    },
    navigation: {
      Type: Object
    }
  },
  methods: {
      goBack : function() {
          this.navigation.goBack();
      }
  }
};
</script>
