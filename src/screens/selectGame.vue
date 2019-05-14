<template>
  <nb-container>
    <Header title="Select Game"/>
    <nb-content padder>
      <!-- Game List -->
      <nb-card v-for="game in games" :key="game.name">
        <nb-card-item button :on-press="gameOptions">
          <nb-left>
            <nb-text>{{game.name}}</nb-text>
          </nb-left>            
          <nb-right>
            <nb-icon name="arrow-forward"></nb-icon>
          </nb-right>            
        </nb-card-item>
      </nb-card>
      <!-- End Game List -->
      <nb-button block :on-press="addGame">
        <nb-text v-if="games.length===0">Create Game...</nb-text>
        <nb-text v-else>Create Another Game...</nb-text>
      </nb-button>
    </nb-content>
  </nb-container>
</template>

<script>
import Header from "../header.vue";
export default {
  components: { Header },
  props: {
    navigation: {
      type: Object
    }
  },
  data: function() {
    return {
      games: [
      ]
    };
  },
  methods: {
    gameOptions : function() {
      this.navigation.navigate("GameOptions");
    },
    addGame : function() {
        let name = "New Chess Game "
        let counter = 1
        let valid = false
        while (!valid) {
            valid = true
            for(let i = 0; i < this.games.length; i++) {
                if(this.games[i].name === name + counter) {
                    valid = false
                    counter++
                    break
                }
            }
        }
        this.games.push({
          name: name + counter,
          boardSize: "8x8",
          pieces: [
            {
              name: "Pawn", 
              enPassant: true, 
              onlyMovesStraight: true, 
              onlyCapturesDiagonally: true, 
              checkmate: false,  
              castlingTarget: "", 
              forwardRange: 1, backwardRange: 0, leftRange: 0, rightRange: 0,
              forwardLeftRange: 1, forwardRightRange: 1, backwardLeftRange: 0, backwardRightRange: 0,
              jumps: []
            },
            {
              name: "Rook", 
              enPassant: false, 
              onlyMovesStraight: false, 
              onlyCapturesDiagonally: false, 
              checkmate: false,  
              castlingTarget: "", 
              forwardRange: 7, backwardRange: 7, leftRange: 7, rightRange: 7,
              forwardLeftRange: 0, forwardRightRange: 0, backwardLeftRange: 0, backwardRightRange: 0,
              jumps: []
            },
            {
              name: "Knight", 
              enPassant: false, 
              onlyMovesStraight: false, 
              onlyCapturesDiagonally: false, 
              checkmate: false,  
              castlingTarget: "", 
              forwardRange: 0, backwardRange: 0, leftRange: 0, rightRange: 0,
              forwardLeftRange: 0, forwardRightRange: 0, backwardLeftRange: 0, backwardRightRange: 0,
              jumps: [
                {x: -2, y: 1}, {x: -1, y: 2},
                {x: 1, y: 2}, {x: 2, y: 1},
                {x: 2, y: -1}, {x: 1, y: -2},
                {x: -1, y: -2}, {x: -2, y: -1}
              ]
            },
            {
              name: "Bishop", 
              enPassant: false, 
              onlyMovesStraight: false, 
              onlyCapturesDiagonally: false, 
              checkmate: false,  
              castlingTarget: "", 
              forwardRange: 0, backwardRange: 0, leftRange: 0, rightRange: 0,
              forwardLeftRange: 7, forwardRightRange: 7, backwardLeftRange: 7, backwardRightRange: 7,
              jumps: []
            },
            {
              name: "Queen", 
              enPassant: false, 
              onlyMovesStraight: false, 
              onlyCapturesDiagonally: false, 
              checkmate: false,  
              castlingTarget: "", 
              forwardRange: 7, backwardRange: 7, leftRange: 7, rightRange: 7,
              forwardLeftRange: 7, forwardRightRange: 7, backwardLeftRange: 7, backwardRightRange: 7,
              jumps: []
            },
            {
              name: "King", 
              enPassant: false, 
              onlyMovesStraight: false, 
              onlyCapturesDiagonally: false, 
              checkmate: true,  
              castlingTarget: "Rook", 
              forwardRange: 1, backwardRange: 1, leftRange: 1, rightRange: 1,
              forwardLeftRange: 1, forwardRightRange: 1, backwardLeftRange: 1, backwardRightRange: 1,
              jumps: []
            }
          ],
          boardLayout: {
            player1: [
              {x: 0, y: 0, piece: "Rook"},
              {x: 1, y: 0, piece: "Knight"},
              {x: 2, y: 0, piece: "Bishop"},
              {x: 3, y: 0, piece: "Queen"},
              {x: 4, y: 0, piece: "King"},
              {x: 5, y: 0, piece: "Bishop"},
              {x: 6, y: 0, piece: "Knight"},
              {x: 7, y: 0, piece: "Rook"},
              {x: 0, y: 1, piece: "Pawn"},
              {x: 1, y: 1, piece: "Pawn"},
              {x: 2, y: 1, piece: "Pawn"},
              {x: 3, y: 1, piece: "Pawn"},
              {x: 4, y: 1, piece: "Pawn"},
              {x: 5, y: 1, piece: "Pawn"},
              {x: 6, y: 1, piece: "Pawn"},
              {x: 7, y: 1, piece: "Pawn"},
            ],
            player2: [
              {x: 0, y: 7, piece: "Rook"},
              {x: 1, y: 7, piece: "Knight"},
              {x: 2, y: 7, piece: "Bishop"},
              {x: 3, y: 7, piece: "Queen"},
              {x: 4, y: 7, piece: "King"},
              {x: 5, y: 7, piece: "Bishop"},
              {x: 6, y: 7, piece: "Knight"},
              {x: 7, y: 7, piece: "Rook"},
              {x: 0, y: 6, piece: "Pawn"},
              {x: 1, y: 6, piece: "Pawn"},
              {x: 2, y: 6, piece: "Pawn"},
              {x: 3, y: 6, piece: "Pawn"},
              {x: 4, y: 6, piece: "Pawn"},
              {x: 5, y: 6, piece: "Pawn"},
              {x: 6, y: 6, piece: "Pawn"},
              {x: 7, y: 6, piece: "Pawn"},
            ]
          }
        });
    }
  }
};
</script>