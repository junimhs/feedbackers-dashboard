<template>
  <custom-header @create-account="handleAccountCreate" @login="handleLogin"/>
  <contact />
  <footer class="flex justify-center py-10 bg-brand-gray">
    <p class="font-medium text-center text-gray-800">feedback © 2021</p>
  </footer>
</template>

<script>
import CustomHeader from './CustomHeader'
import Contact from './Contact'
import { onMounted } from 'vue'
import { useRouter } from 'vue-router'
export default {
  name: 'index',
  components: { Contact, CustomHeader },
  setup () {
    const router = useRouter()

    onMounted(() => {
      const token = window.localStorage.getItem('token')
      if (token) {
        router.push({ name: 'Feedbacks' })
      }
    })

    function handleLogin () {}
    function handleAccountCreate () {}

    return {
      handleLogin,
      handleAccountCreate
    }
  }
}
</script>

<style scoped>

</style>
