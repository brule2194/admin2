<template>

    <MateriaP />

</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import MateriaP from '@/components/MateriaPrimaC.vue'; // @ is an alias to /src

@Component({
  components: {
    MateriaP,
  },
})
export default class Home extends Vue {}
</script>
