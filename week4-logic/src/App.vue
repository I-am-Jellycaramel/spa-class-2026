<script setup>
  import {ref} from "vue";
  const removeData = (id) => {
    console.log(`${id} 데이터 삭제함.`);
  }
  const keyword = ref('');
  const isOpen = ref(true);
  const currentTab = ref('액션');
</script>

<template>
  <button type="button" @click="removeData(1)">1번 데이터 삭제</button>
  <button type="button" @click="removeData(2)">2번 데이터 삭제</button>
  <button type="button" @click="removeData(3)">3번 데이터 삭제</button>
  <input type="test" v-model="keyword" @keyup.enter="search" placeholder="검색어를 입력하세요">
  <button type="button" @click="isOpen = !isOpen">isOpen토글</button>
  <div v-if="isOpen">v-if 영역</div>
  <div v-show="isOpen">v-show 영역</div>
  <button :class="{active: currentTab==='액션'}" @click="currentTab='액션'">액션</button>
  <button :class="{active: currentTab==='sf'}" @click="currentTab='sf'">sf</button>
  <button :class="{active: currentTab==='로맨스'}" @click="currentTab='로맨스'">로맨스</button>
</template>

<style scoped>
  .active {
    background-color: #42b883;
  }
</style>
