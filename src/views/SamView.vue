<template>
  <div class="sam">
    <h1>C'est ma page !</h1>
    <BodyPsam></BodyPsam>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import BodyPsam from '@/components/BodyPsam.vue'; // @ is an alias to /src

@Options({
  components: {
    BodyPsam,
  },
})
export default class SamView extends Vue {}
</script>