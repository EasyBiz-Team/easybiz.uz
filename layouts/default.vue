<script setup lang="ts">
import { useRoute } from 'vue-router'

const closesidebar = () => {
    const element = document.querySelector(".aside");
    if (element) {
        element.classList.toggle("opened");
    }
};

</script>

<template>
    <!-- <ViewAll /> -->
    <div class="container">
        <header class="header">
            <div class="header-control">
                <button class="header-burger" @click="closesidebar">..</button>
                <div class="logo">
                    <img src="" alt="Constructor X" />
                </div>
            </div>

            <ul class="header-list">
                <li class="header-item">
                    <router-link to="/" class="header-link">
                        Dashboard
                    </router-link>
                </li>
                <li class="header-item">
                    <router-link to="/users" class="header-link">
                        Users
                    </router-link>
                </li>
                <!-- <li class="header-item">
          <router-link to="#" class="header-link">
            Support
          </router-link>
        </li>
        <li class="header-item">
          <router-link to="#" class="header-link">
            More
          </router-link>
        </li> -->
            </ul>
            <div class="header-avatar">
                <button class="header-avatar-button">Upgrade</button>
                <img src="https://ui-avatars.com/api/?name=John+Doe" alt="" />
            </div>
        </header>
        <aside class="aside">
            <div class="aside-container">
                <img src="https://ui-avatars.com/api/?name=John+Doe" class="aside-avatar" alt="" />
                <ul class="aside-list">
                    <li class="aside-item" @click="closesidebar">
                        <RouterLink to="/" class="aside-link">
                            Dashboard
                        </RouterLink>
                    </li>
                    <li class="aside-item" @click="closesidebar">
                        <RouterLink to="/users" class="aside-link"
                            :class="useRoute().path.includes('users') ? 'router-link-active' : ''">
                            Users
                        </RouterLink>
                    </li>
                </ul>
            </div>
            <div class="aside-container">
                <footer class="aside-footer">&copy; {{ new Date().getFullYear() }} PHOENIX GROUP</footer>
            </div>
        </aside>
        <div class="review">
            <slot />
        </div>
    </div>
</template>

<style scoped lang="scss">

.aside {
    height: 100vh;
    width: 20rem;
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    padding-top: 8rem;
    box-shadow: 0 .5rem .3rem .3rem rgba(0, 0, 0, 0.2);
    background: white;
    overflow: hidden;
    transition: 600ms;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: space-between;

    @media(max-width: 1024px) {
        width: 0;
        opacity: 0;
        transform: translateX(-20rem);

        &.opened {
            width: 20rem;
            transform: translateX(0);
            opacity: 1;
            transition: 300ms;
        }
    }

    @media(max-width: 768px) {
        &.opened {
            width: 50%;
        }
    }

    @media(max-width: 500px) {
        &.opened {
            width: 100%;
        }
    }

    &-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        padding: 1rem;
        transition: 300ms;
        row-gap: 2rem;
        position: relative;
    }

    &-avatar {
        width: 4rem;
        height: 4rem;
        border-radius: 50%;
        border: .05rem solid white;
        transition: 300ms;

        @media(max-width: 768px) {
            width: 8rem;
            height: 8rem;
        }
    }

    &-list {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        transition: 300ms;
    }

    &-item {
        width: 100%;
    }

    &-link {
        width: inherit;
        display: block;
        border-radius: 1rem;
        background: #fff;
        text-align: start;
        padding: 1rem 1.5rem;
        color: #475166;

        @media(max-width: 768px) {
            font-size: 2rem;
            line-height: 125%;
            padding: 1.75rem 1.5rem;
        }

        @media(max-width: 500px) {
            font-size: 1.6rem;
            line-height: 130%;
            font-weight: 500;
            padding: 1rem;
        }

        &.router-link-active {
            background: #2563EB;
            color: #fff;
        }

        &:hover {
            background: #2563EB;
            color: #fff;
        }
    }

    &-footer {
        font-size: 1rem;
    }

}
</style>