<template>
    <nb-container>
        <Header title="Edit Game" :navigation="navigation"/>
        <nb-content padder>
            <nb-form>
                <nb-item inlineLabel>
                    <nb-label>Game Name</nb-label>
                    <nb-input />
                </nb-item>
                <BoardSizePicker :boardSize="boardSize" :setBoardSize="setBoardSize" />
                <PieceListMaker :pieces="pieces" :setPieces="setPieces" :navigation="navigation"/>
                <nb-item>
                    <nb-text>TODO: Board Layout </nb-text>
                </nb-item>
            </nb-form>
        </nb-content>
    </nb-container>
</template>

<script>
import Header from "../header.vue";
import BoardSizePicker from "../components/boardSizePicker.vue";
import PieceListMaker from "../components/pieceListMaker.vue";

export default {
    components: { Header, BoardSizePicker, PieceListMaker },
    props: {
        navigation: {
            type: Object
        }
    },
    data: function() {
        return {
            boardSize: "8x8",
            pieces: [
                {name: "Pawn"}
            ]
        };
    },
    methods: {
        setBoardSize : function(boardSize) {
            this.boardSize = boardSize;
        },
        setPieces : function(boardSize) {
            this.pieces = pieces;
        }
    }
};
</script>