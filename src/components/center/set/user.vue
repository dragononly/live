<template>
  <div style="padding: 10px">
    <div style="margin-top: 10px">
      <a-button @click="out_login()" type="primary">退出登陆</a-button>
    </div>
  </div>
</template>

<script lang="ts">
import { toRefs, defineComponent } from 'vue';
import { data } from '../store/tuiliu';
import { Mpost } from '../../../../config/http/index';
import { useRouter } from 'vue-router';
export default defineComponent({
  data() {
    return {
      ...toRefs(data),
    };
  },
  async setup() {
    const router = useRouter();
    const out_login = () => {
      localStorage.autologin = '0';
      router.push('/');
    };
    return { out_login };
  },
  components: {},
});
</script>
<style type="text/css">
</style>
