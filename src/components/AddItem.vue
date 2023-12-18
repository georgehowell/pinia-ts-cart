<!-- eslint-disable @typescript-eslint/no-empty-function -->
<template>
  <form class="form px-3" @submit.prevent="submit">
      <input v-model="inputs.name" type="text" class="form-control mb-3" placeholder="Name"/>
            <input v-model="inputs.url" type="text" class="form-control mb-3" placeholder="URL" /> 
    <button type="submit" class="btn btn-success mb-1">
        Add
    </button>
  </form>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue'
import { useCartStore } from '@/store/cart';

export default defineComponent({
    setup() {
        const inputs = reactive({ name: '', url: '' })
        const cart = useCartStore()
        const submit = () => {
            cart.addItem({ ...inputs })
            inputs.name = ''
            inputs.url = ''
        }
        return {inputs, submit}
    }
    
})
</script>

<style scoped>
.btn-success {
    width: 100%;
}
@media screen and (min-width: 500px) {
    .btn-success {width: 50%;}
}
@media screen and (min-width: 1200px) {
    .btn-success {width: 20%;}
}

</style>