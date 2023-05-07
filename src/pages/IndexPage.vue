<script setup>
import Message from 'components/Message.vue';
import Login from 'components/Login.vue';

const a = false;

</script>

<template>
  <q-page class="flex flex-center">
  <Message v-if="a"/>
  <Login v-if="!a"/>
  </q-page>
</template>


