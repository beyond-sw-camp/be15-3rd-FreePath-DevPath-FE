<script setup>
import { useRouter } from 'vue-router'

const props = defineProps({
  text: {
    type: String,
    default: '회원가입 하기'
  },
  goTo: {
    type: String,
    default: ''
  },
  icon: {
    type: String,
    default: ''
  },
  bgColor: {
    type: String,
    default: '#c6c7f8' // 기본 색상
  }
})

const router = useRouter()

function handleClick() {
  if (props.goTo) {
    router.push(props.goTo)
  }
}
</script>

<template>
  <div
      class="button-frame"
      :style="{ backgroundColor: bgColor }"
  @click="handleClick"
  >
  <img :src="icon" alt="img" class="icon" />
  <div class="text">{{ text }}</div>
  </div>
</template>

<style scoped>
.button-frame {
  width: fit-content;
  border-radius: 8.74px;
  padding-left: 13.1px;
  padding-right: 13.1px;
  padding-top: 8.74px;
  padding-bottom: 8.74px;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  gap: 4.37px;
  position: relative;
  border-style: hidden;
  outline: none;
  cursor: pointer;
}

.text {
  color: #000000;
  text-align: left;
  vertical-align: text-top;
  font-size: 12px;
  line-height: 20px;
  border-style: hidden;
  outline: none;
}
</style>
