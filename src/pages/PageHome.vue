<template>
  <q-page>
    <div class="q-py-lg q-px-md row items-end q-col-gutter-md">
      <div class="col">
        <q-input 
        bottom-slots 
        v-model="newQweetContent" 
        placeholder="What's happening?" 
        counter 
        maxlength="280" 
        autogrow
        class="new-qweet"
        clearable
        >
          <!--autogrow:  yazdıkça alt satıra gecer -->
          
        <template v-slot:before>
          <q-avatar size="xl">
            <img src="https://cdn.quasar.dev/img/avatar5.jpg">
          </q-avatar>
        </template>

          <!-- Eğer herhangi bir content yoksa ':disabled' ile burada butonu disable ediyoruz -->
          <!-- no-caps ise yazılan herşeyi küçük algılıyor -->
        </q-input>
      </div>
      <div class="col col-shrink">
        <q-btn 
        class="q-mb-lg"
        unelevated 
        rounded 
        color="primary" 
        label="Qweet" 
        no-caps 
        :disabled="!newQweetContent" 
        />
      </div>

    </div>
    
    <q-separator 
      size="10px" 
      color="grey-2" 
      class="divider"
      />

  </q-page>
</template>

<script setup>
import { ref } from 'vue';
const newQweetContent = ref("")
</script>


<style lang="sass">
.new-qweet
  textarea
   font-size: 19px
   line-height: 1.4 !important
.divider
  border-top: 1px solid
  border-bottom: 1px solid
  border-color: $grey-4  
</style>