<!-- src/components/InputBox.vue -->
<template>
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
        <div class="container-fluid container">
            <!-- <a class="navbar-brand" href="#">KB, 하이</a> -->
            <RouterLink class="navbar-brand" :to="{ name:'home' }">KB, 하이</RouterLink>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
                <!-- <li class="nav-item">
                    <RouterLink class="nav-link" :to="{ name:'home' }">Home</RouterLink>
                </li> -->
                <li class="nav-item">
                    <a class="nav-link" href="https://obank.kbstar.com/quics?page=C030037#loading">국민은행</a>
                </li>
                <li class="nav-item">
                    <RouterLink class="nav-link" :to="{ name:'chat' }">AI agent</RouterLink>
                </li>
            </ul>
            </div>
        </div>
    </nav>
</template>
  
<script>
import { RouterLink, RouterView } from 'vue-router'

</script>

<style scoped>
.navbar {
    font-family: 'Noto Sans KR', sans-serif;
}
</style>
