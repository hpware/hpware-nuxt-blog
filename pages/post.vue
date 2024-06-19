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
        <div class="blog" v-if="pid === '1'">
            <p1 />
        </div>
        <div class="blog" v-else-if="pid === '2'">
            <p2 />
        </div>
        <div v-else>
            <div>
                <br><br>
                <h1 style="text-align: center;">ㄜ... 你來到了黑洞？</h1>
                <h2 style="text-align:center;"><a style="text-decoration: none; color:aliceblue" href="https://hpware.hwtw.cc">按這邊回去吧！</a></h2>
            </div>
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
    vertical-align: middlex;
}
.norm {
    display: flex;
	 align-items: center;
	justify-content: center;
}

</style>