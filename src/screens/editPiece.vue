<template>
    <nb-container>
        <Header title="Edit Piece" :navigation="navigation"/>
        <nb-content padder>
            <nb-form>
                <nb-item inlineLabel>
                    <nb-label>Piece Name</nb-label>
                    <nb-input />
                </nb-item>
                <nb-list-item>
                    <nb-checkbox :checked="false" />
                    <nb-body>
                    <nb-text>"En Passant"</nb-text>
                    </nb-body>
                </nb-list-item>
                <nb-list-item>
                    <nb-checkbox :checked="false" />
                    <nb-body>
                    <nb-text>"Only Moves Straight"</nb-text>
                    </nb-body>
                </nb-list-item>
                <nb-list-item>
                    <nb-checkbox :checked="false" />
                    <nb-body>
                    <nb-text>"Only Captures Diagonally"</nb-text>
                    </nb-body>
                </nb-list-item>
                <nb-list-item>
                    <nb-checkbox :checked="false" />
                    <nb-body>
                    <nb-text>Checkmate</nb-text>
                    </nb-body>
                </nb-list-item>
                <nb-list-item>
                    <nb-text>TODO: Dropdown to Select Castling Target </nb-text>
                </nb-list-item>
                <nb-list-item>
                    <nb-text>TODO: Forward Range </nb-text>
                </nb-list-item>
                <nb-list-item>
                    <nb-text>TODO: Backward Range </nb-text>
                </nb-list-item>
                <nb-list-item>
                    <nb-text>TODO: Left Range </nb-text>
                </nb-list-item>
                <nb-list-item>
                    <nb-text>TODO: Right Range </nb-text>
                </nb-list-item>
                <nb-list-item>
                    <nb-text>TODO: Forward Left Diagonal Range </nb-text>
                </nb-list-item>
                <nb-list-item>
                    <nb-text>TODO: Forward Right Diagonal Range </nb-text>
                </nb-list-item>
                <nb-list-item>
                    <nb-text>TODO: Backward Right Diagonal Range </nb-text>
                </nb-list-item>
                <nb-list-item>
                    <nb-text>TODO: Backward Left Diagonal Range </nb-text>
                </nb-list-item>
                <nb-list-item>
                    <nb-text>TODO: Jump Locations </nb-text>
                </nb-list-item>
                <nb-button block on-press="savePiece">
                    <nb-text>Save Piece</nb-text>
                </nb-button>
            </nb-form>
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
        savePiece : function() {
            
        }
    }
}
</script>
