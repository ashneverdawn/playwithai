<template>
    <nb-container>
        <Header title="Game Options" :navigation="navigation"/>
        <nb-content padder>
            <nb-card>
                <nb-card-item button :on-press="editGame">
                    <nb-left>
                        <nb-text>Edit Game</nb-text>
                    </nb-left>            
                    <nb-right>
                        <nb-icon name="arrow-forward"></nb-icon>
                    </nb-right>            
                </nb-card-item>
            </nb-card>
            <nb-card>
                <nb-card-item button :on-press="playGame">
                    <nb-left>
                        <nb-text>Play (2 Local Players)</nb-text>
                    </nb-left>            
                    <nb-right>
                        <nb-icon name="arrow-forward"></nb-icon>
                    </nb-right>            
                </nb-card-item>
            </nb-card>
        </nb-content>
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
    },
    methods: {
        editGame : function() {
            this.navigation.navigate("EditGame");
        },
        playGame : function() {
            this.navigation.navigate("PlayGame");
        }
    }
}
</script>
