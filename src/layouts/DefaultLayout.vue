<template>
    <div>
        <nav class="navbar py-2"
            role="navigation"
            aria-label="main navigation">
            <div class="navbar-brand">
                <a class="navbar-item" href="https://thesyafiq.dev">
                    <i class="fa-solid fa-notes"></i>
                    --
                </a>

                <a role="button"
                    class="navbar-burger"
                    aria-label="menu"
                    aria-expanded="false"
                    data-target="navbarBasicExample">
                    <span aria-hidden="true"></span>
                    <span aria-hidden="true"></span>
                    <span aria-hidden="true"></span>
                </a>
            </div>

            <div id="navbarBasicExample" class="navbar-menu">
                <div class="navbar-end">
                    <!-- <router-link class="nav-item my-auto is-family-code"
                        to="/#top"
                        v-slot="{ navigate }">
                        <a @click="navigate"
                            @keypress.enter="navigate"
                            role="link"
                            class="navbar-item"
                            tabindex="0">
                            Home
                        </a>
                    </router-link>
                    <router-link class="nav-item my-auto is-family-code"
                        to="/#contact"
                        v-slot="{ navigate }">
                        <a @click="navigate"
                            @keypress.enter="navigate"
                            role="link"
                            class="navbar-item"
                            tabindex="0">
                            Contact
                        </a>
                    </router-link>
                    <router-link class="nav-item my-auto is-family-code"
                        to="/about"
                        v-slot="{ navigate }">
                        <a @click="navigate"
                            @keypress.enter="navigate"
                            role="link"
                            class="navbar-item"
                            tabindex="-1">
                            About
                        </a>
                    </router-link>
                    <router-link class="nav-item my-auto is-family-code"
                        to="/testing"
                        v-slot="{ navigate }">
                        <a @click="navigate"
                            @keypress.enter="navigate"
                            role="link"
                            class="navbar-item"
                            tabindex="-1">
                            Testing
                        </a>
                    </router-link> -->
                    <div class="navbar-item">
                        <div class="buttons">
                            <a class="button is-family-code"
                                aria-label="Github redirect"
                                href="https://github.com/syfqpie"
                                target="_blank">
                                <i class="fa-brands fa-github-alt mr-2"></i>
                                Github
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </nav>
    </div>
</template>
