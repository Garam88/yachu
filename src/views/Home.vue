<template>
  <div class="home">
    <div class="game-area">
      <div class="score-area">
        <div class="table">
          <div class="row" v-for="score in scoreType">
            <div class="column title">
              {{ score.title }}
            </div>
            <div class="column">
              {{ score.num }}
            </div>
          </div>
        </div>
      </div>
      <div class="dice-area">
        dice
      </div>
    </div>
    <div class="inf-area">
      interface
    </div>
  </div>
</template>

<script>
import {Vue, Component} from 'vue-property-decorator'

@Component
export default class Home extends Vue {
  scoreType = [{title:'Aces', num: 0}, {title:'Deuces', num: 0}, {title:'Threes', num: 0}, {title:'Fours', num: 0}, {title:'Fives', num: 0}, {title:'Sixes', num: 0}]
}
</script>

<style scoped="scoped" lang="less">
.home {
  display: flex;
  flex-direction: row;
  height: 100vh;

  .game-area {
    width: 1000px;

    .score-area {
      height: 600px;

      .table {
        width: 200px;

        .column.title {
          width: 100px;
        }
      }
    }
  }
  .inf-area {
    display: flex;
    flex: 1 auto;
  }

  .table {
    display: flex;
    flex-direction: column;

    .row {
      display: flex;
      flex-direction: row;

      .column {
        &.title {
          font-weight: bold;
        }
      }
    }
  }
}
</style>