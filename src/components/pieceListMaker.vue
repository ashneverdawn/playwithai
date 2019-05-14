<template>
    <nb-container>
        <nb-card v-for="piece in pieces" :key="piece.name" >
            <nb-card-item button :on-press="editPiece">
            <nb-left>
                <nb-text>{{piece.name}}</nb-text>
            </nb-left>            
            <nb-right>
                <nb-icon name="arrow-forward"></nb-icon>
            </nb-right>            
            </nb-card-item>
        </nb-card>
        <nb-button block :on-press="addPiece">
            <nb-text v-if="pieces.length===0">Create Piece...</nb-text>
            <nb-text v-else>Create Another Piece...</nb-text>
        </nb-button>
    </nb-container>
</template>

<script>
export default {
    props: {
        navigation: {
            type: Object
        },
        setPieces: {
            type: Function
        },
        pieces: {
            type: Array
        }
    },
    methods: {
        editPiece : function() {
            this.navigation.navigate("EditPiece");
        },
        addPiece : function() {
            let name = "New Piece "
            let counter = 1
            let valid = false
            while (!valid) {
                valid = true
                for(let i = 0; i < this.pieces.length; i++) {
                    if(this.pieces[i].name === name + counter) {
                        valid = false
                        counter++
                        break
                    }
                }
            }
            this.pieces.push({name:name + counter})
        }
    }
}
</script>
