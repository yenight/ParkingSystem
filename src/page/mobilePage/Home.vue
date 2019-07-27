<template>
    <div>
      <MobileHeader></MobileHeader>
      <MobileParkingBoyFooter v-if="$store.state.roleSelected === 'parkingBoy'"></MobileParkingBoyFooter>
      <MobileCustomerFooter v-else></MobileCustomerFooter>
    </div>
</template>

<script>
import MobileHeader from '../../components/header/MobileHeader'
import MobileParkingBoyFooter from '../../components/footer/MobileParkingBoyFooter'
import MobileCustomerFooter from '../../components/footer/MobileCustomerFooter'
export default {
  name: 'Login',
  components: { MobileCustomerFooter, MobileParkingBoyFooter, MobileHeader },
  data: function () {
    return {
    }
  }
}
</script>

<style scoped>

</style>
