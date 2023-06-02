<template>
  <q-page>
    <div class="q-py-lg q-px-md row items-end q-col-gutter-md">
      <div class="col">
        <q-input bottom-slots v-model="newQweetContent" placeholder="What's happening?" counter maxlength="280" autogrow
          class="new-qweet">
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
        <q-btn class="q-mb-lg" unelevated rounded color="primary" label="Qweet" no-caps :disabled="!newQweetContent" />
      </div>

    </div>

    <q-separator size="10px" color="grey-2" class="divider" />

    <q-list>


      <q-item class="q-py-md">
        <q-item-section avatar top>
          <q-avatar size="xl">
            <img src="https://cdn.quasar.dev/img/avatar5.jpg">
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label class="text-subtitle1">
            <strong>Janet</strong>
            <span class="text-grey-7">
              @janet_Marcel
            </span>
          </q-item-label>

          <q-item-label class="text-body1 qweet-content">
            Lorem ipsum dolor
            sit amet


            consectetur adipisicing elit. Ex ut consectetur voluptas sunt odit maxime,
            architecto
            enim iusto harum non.
          </q-item-label>
        </q-item-section>

        <q-item-section side top>
          1 min ago
        </q-item-section>
      </q-item>

    </q-list>

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
.qweet-content
  white-space: pre-line
</style>