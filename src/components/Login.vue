<script setup>
import { ref } from 'vue'

const name = ref('');

const email = ref('');

const password = ref('');

const isPwd = ref(true);

</script>

<template>
  <div class="q-pa-md bg-green-2" style="max-width: 400px; border-radius:5px">
    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="name"
        label="Your Nick Name *"
        hint="Name and surname"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

      <q-input
        filled
        v-model="email"
        label="Email *"
        hint="Name and surname"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />
      
      <q-input v-model="password" label="Password *" filled :type="isPwd ? 'password' : 'text'" hint="Password with toggle">
        <template v-slot:append>
          <q-icon
            :name="isPwd ? 'visibility_off' : 'visibility'"
            class="cursor-pointer"
            @click="isPwd = !isPwd"
          />
        </template>
      </q-input>

      <div class="row justify-center q-gutter-x-md">
        <q-btn label="Reset" type="reset" color="primary" flat />
        <q-btn label="Submit" type="submit" color="primary" flat/>
      </div>
    </q-form>

  </div>
    
</template>