<template>
    <div class="login-body">
      <el-select v-model="selectedRole" placeholder="请选择角色">
        <el-option
          v-for="item in selectedOptions"
          :key="item.value"
          :label="item.label"
          :value="item.value">
        </el-option>
      </el-select>
      <div class="login-body-button-div">
        <el-button type="primary" @click="clickLogin">Login</el-button>
      </div>
    </div>
</template>

<script>
import { SELECT_ROLE } from '../store/const-types'
export default {
  name: 'Login',
  data: function () {
    return {
      selectedRole: '',
      selectedOptions: [
        { value: 'customer', label: 'Customer' },
        { value: 'parkingBoy', label: 'Parking Boy' },
        { value: 'manager', label: 'Manager/Admin' }
      ]
    }
  },
  methods: {
    clickLogin () {
      this.$store.commit(SELECT_ROLE, { roleSelected: this.selectedRole })
      if (this.selectedRole === 'customer' || this.selectedRole === 'parkingBoy') {
        this.$router.push('/mobile-home')
      } else if (this.selectedRole === 'manager') {
        this.$router.push('/web-home')
      }
    }
  }
}
</script>

<style scoped>

</style>
