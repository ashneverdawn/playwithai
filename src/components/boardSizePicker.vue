<template>
    <nb-item picker inlineLabel>
    <nb-label>Board Size</nb-label>
    <nb-picker
        mode="dropdown"
        :iosIcon="getIosIcon()"
        :selectedValue="boardSize"
        :onValueChange="setBoardSize"
    >
        <item label="8x8" value="8x8" />
        <item label="9x9" value="9x9" />
        <item label="10x10" value="10x10" />
        <item label="11x11" value="11x11" />
    </nb-picker>
</template>


<script>
import React from "react";
import { Picker, Icon } from "native-base";

export default {
    components: { Item: Picker.Item },
    props: {
        setBoardSize: {
            type: Function
        },
        boardSize: {
            type: String
        }
    },
    methods: {
        getIosIcon: function() {
            return <Icon name="ios-arrow-dropdown" />;
        }
    }
};
</script>