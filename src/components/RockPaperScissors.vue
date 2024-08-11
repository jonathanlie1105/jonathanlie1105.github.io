<script setup lang="ts">
import { provide, ref, type Ref } from 'vue'
import Button from '@/core-ui/MyButton.vue'
import GameItem from './GameItem.vue'
import IconRock from './icons/IconRock.vue'
import IconPaper from './icons/IconPaper.vue'
import IconScissors from './icons/IconScissors.vue'

enum Options {
  'Rock',
  'Paper',
  'Scissors'
}

type Player = {
  name: string
  point: number
}

const isGameStart = ref(false)
const isGameFinish = ref(false)
const isPlayerWin = ref(false)
const selectedIdx = ref<number | null>(null)
const player = ref<Player>({
  name: 'John Doe',
  point: 0
})
const enemy = ref<Player>({
  name: 'Alter Ego',
  point: 0
})

function wrapUpGame() {
  isGameStart.value = false
  isGameFinish.value = false
  isPlayerWin.value = false
  selectedIdx.value = null
  player.value.point = 0
  enemy.value.point = 0
}
function toggleStartGame() {
  if (isGameStart.value) {
    isGameStart.value = false
    wrapUpGame()
  } else {
    isGameStart.value = true
  }
}
function clickOption(idx: number) {
  if (selectedIdx.value === null || selectedIdx.value !== idx) {
    selectedIdx.value = idx
  } else {
    selectedIdx.value = null
  }
}
function checkWinner() {
  if (player.value.point === 5) {
    isPlayerWin.value = true
  } else {
    isPlayerWin.value = false
  }
}
function addPoint(target: Ref<Player>) {
  target.value.point += 1
  if (target.value.point === 5) {
    isGameFinish.value = true
    checkWinner()
  }
}
function isEnemyWinning(enemyIdx: number) {
  return (
    (enemyIdx === 0 && selectedIdx.value === 2) ||
    (enemyIdx === 1 && selectedIdx.value === 0) ||
    (enemyIdx === 2 && selectedIdx.value === 1)
  )
}
function isPlayerWinning(enemyIdx: number) {
  return (
    (enemyIdx === 2 && selectedIdx.value === 0) ||
    (enemyIdx === 0 && selectedIdx.value === 1) ||
    (enemyIdx === 1 && selectedIdx.value === 2)
  )
}
function startBattle() {
  if (selectedIdx.value === null) {
    alert('Choose your option')
    return
  }

  const enemyIdx = Math.floor(Math.random() * 3)
  if (enemyIdx === selectedIdx.value) {
    alert(`
  ${Options[selectedIdx.value]} vs ${Options[enemyIdx]}
  Draw! Did you read his mind?
    Your Point  : ${player.value.point}
    Enemy Point : ${enemy.value.point}
    `)
  } else if (isEnemyWinning(enemyIdx)) {
    addPoint(enemy)
    alert(`
  ${Options[selectedIdx.value]} vs ${Options[enemyIdx]}
  You Lose!
    Your Point  : ${player.value.point}
    Enemy Point : ${enemy.value.point}
    `)
  } else if (isPlayerWinning(enemyIdx)) {
    addPoint(player)
    alert(`
  ${Options[selectedIdx.value]} vs ${Options[enemyIdx]}
  You Win!
    Your Point  : ${player.value.point}
    Enemy Point : ${enemy.value.point}
    `)
  }
}

provide('selectedIdx', selectedIdx)
</script>

<template>
  <div v-if="!isGameStart" class="container column">
    <div>
      <h4>...or play this mini game</h4>
      <h1>Rock, Paper, Scissors</h1>
    </div>
    <Button :disabled="false" @click="toggleStartGame"> Start Game </Button>
  </div>
  <div v-if="isGameStart && !isGameFinish" class="container column">
    <div class="container row">
      <GameItem :index="0" :on-click="() => clickOption(0)">
        <template #name>Rock</template>
        <template #icon>
          <IconRock />
        </template>
      </GameItem>
      <GameItem :index="1" :on-click="() => clickOption(1)">
        <template #name>Paper</template>
        <template #icon>
          <IconPaper />
        </template>
      </GameItem>
      <GameItem :index="2" :on-click="() => clickOption(2)">
        <template #name>Scissors</template>
        <template #icon>
          <IconScissors />
        </template>
      </GameItem>
    </div>
    <div class="container row">
      <Button type="danger" :disabled="false" @click="toggleStartGame"> Reset </Button>
      <Button type="success" :disabled="false" @click="startBattle"> Shoot </Button>
    </div>
  </div>
  <div v-if="isGameStart && isGameFinish" class="container column">
    <h1>GAME OVER</h1>
    <h2>You {{ isPlayerWin ? 'Win' : 'Lose' }}</h2>
    <Button type="danger" :disabled="false" @click="wrapUpGame"> Restart </Button>
  </div>
</template>

<style scoped>
h1 {
  list-style: 1.5;
  font-size: x-large;
}
.container {
  height: 50vh;
  display: flex;
  place-content: center;
  place-items: center;
  row-gap: calc(var(--section-gap) / 12);
  column-gap: calc(var(--section-gap) / 10);
  padding: 0.6rem;
}
.column {
  flex-direction: column;
}
.row {
  flex-direction: row;
}
@media (min-width: 1024px) {
  .container {
    height: 25vh;
    row-gap: calc(var(--section-gap) / 8);
    column-gap: calc(var(--section-gap) / 2);
  }
}
</style>
