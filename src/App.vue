<template>
  <h2 v-if="authStatus === 'authenticating'">Authenticating</h2>
  <router-view v-else />
</template>

<script>
import useAuth from '@/modules/auth/composables/useAuth'

export default {
  setup() {
    const { authStatus, checkAuthStatus } = useAuth()

    checkAuthStatus()

    return {
      authStatus
    }
  },
}
</script>
