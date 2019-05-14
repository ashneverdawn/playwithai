<template>
    <nb-container>
        <Header title="Play Game" :navigation="navigation"/>
        <nb-content padder flex="0.5">
            <nb-card>
                <nb-card-item>
                    <nb-body>
                        <nb-text>White's turn</nb-text>
                    </nb-body>            
                </nb-card-item>
            </nb-card>
        </nb-content>
        <nb-grid>
            <nb-col :style="{ backgroundColor: 'black' }">
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
            </nb-col>
            <nb-col :style="{ backgroundColor: 'white' }">
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
            </nb-col>
            <nb-col :style="{ backgroundColor: 'black' }">
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
            </nb-col>
            <nb-col :style="{ backgroundColor: 'white' }">
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
            </nb-col>
            <nb-col :style="{ backgroundColor: 'black' }">
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
            </nb-col>
            <nb-col :style="{ backgroundColor: 'white' }">
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
            </nb-col>
            <nb-col :style="{ backgroundColor: 'black' }">
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
            </nb-col>
            <nb-col :style="{ backgroundColor: 'white' }">
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'black' }"></nb-row>
                <nb-row :style="{ backgroundColor: 'white' }"></nb-row>
            </nb-col>
        </nb-grid>
    </nb-container>
</template>

<script>
import Header from "../header.vue";
export default {
    components: { Header },
    props: {
        navigation : {
            Type: Object
        }
    }
}
</script>
