<template>
    <User>
        <template #userLoading="{userLoading}">
            <LoadingSpinner v-if="userLoading" />
        </template>
        <template #user="{user}">
            <main-header :user="user"></main-header>
            <main>
                <ChatList v-if="user" :uid="user.uid" />
                <Login v-else />
            </main>
        </template>
    </User>
</template>

<script>
import User from '../components/User'
import ChatList from '../components/ChatList'
import Login from '../components/Login'
import LoadingSpinner from '../components/LoadingSpinner'
import MainHeader from '../components/MainHeader'

export default {
    components: {
        User,
        ChatList,
        Login,
        LoadingSpinner,
        MainHeader,
    }
}
</script>

<style lang="scss">
main {
    position: relative;
    flex: 1;
    display: flex;
    flex-direction: column;
    max-width: 500px;
    width: 100%;
    margin: 0 auto;
    padding: 8px;
    box-sizing: border-box;

    h2 {
        margin-top: 0;
        text-align: center;
    }

    button {
        background-color: white;
        border-radius: 4px;
        font-size: 1rem;
    }
}
</style>