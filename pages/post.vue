<script setup lang="ts">
import p1 from "../posts/1.vue"
import p2 from "../posts/2.vue"
import { ref, onMounted } from 'vue'

const pid = ref<string | null>(null)

onMounted(() => {
  pid.value = new URLSearchParams(window.location.search).get("id")
})
// thx chatgpt
</script>
<template>
    <br>
    <br>
    <div class="norm">
        <div>
        <div class="blog" v-if="pid === '1'">
            <p1 />
        </div>
        <div class="blog" v-else-if="pid === '2'">
            <p2 />
        </div>
        <div v-else>
        </div>
        <br>
        <a style="text-decoration: none; color:aliceblue;text-align: center;" href="https://hpware.hwtw.cc">返回</a>
        </div>
    </div>
</template>
<style>
.blog {
    text-align: center;
    align-items:center;
    justify-content: center;
    display: block;
    flex-direction: column;
    vertical-align: middle;
}
.norm {
    display: flex;
	 align-items: center;
	justify-content: center;
}
.error {
    transition-delay: 2s;
}

</style>