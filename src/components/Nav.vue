<script setup> 
import { RouterLink } from "vue-router";
import Container from './Container.vue'
import { ref } from 'vue'
import AuthModal from "./AuthModal.vue";

const SearchUser = ref("")

const isAuth = ref(false)

const onSearch = () => {}
</script>
<template>
    <a-layout-header>
        <Container>
            <div class="nav-container">
                <div class="right-content">
                    <RouterLink to="/">InstaClone</RouterLink>
                    <a-input-search
                    v-model:value="SearchUser"
                    placeholder="Search Users"
                    style="width: 200px"
                    @search="onSearch"
                    />
                </div>
                <div class="left-content" v-if="!isAuth">
                    <AuthModal :is-login="false"/>
                    <AuthModal :is-login="true"/>
                </div>
                <div class="left-content" v-else>
                    <a-button type="primary">Profile</a-button>
                    <a-button type="primary">Log out</a-button>
                </div>
            </div>
        </Container>
    </a-layout-header>
</template>

<style scoped>
.nav-container {
    display: flex;
    justify-content: space-between;
}

.right-content {
    display: flex;
    align-items: center;
    gap: 10px;
}
.left-content {
    display: flex;
    align-items: center;
    gap: 10px;
}
</style>