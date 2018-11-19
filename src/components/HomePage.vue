<template>
    <div class="homepage">
        <div class="logo">
            <a :href="urlLogo">
                <img src="../assets/logo.png" alt="logo">
            </a>
        </div>
        <s-v-g-component v-bind:list="list" v-bind:info="info"/>
        <contact-phone v-bind:contacts="contacts"/>
    </div>
</template>
<script>
    import json from './../data.json'
    import SVGComponent from './SVGComponent'
    import ContactPhone from './ContactPhone'
    export  default {
        name: 'HomeComponent',
        components: {
            SVGComponent,
            ContactPhone
        },
        data() {
            return {
                list: json.list,
                info: json.info,
                contacts: json.contact,
                urlLogo: null
            }
        },
        mounted() {
            fetch('data.json').then(e => e.json()).then(e => {
                this.list = e.list
                this.info = e.info
                this.contacts = e.contact
                this.urlLogo = e.info.urlLogo
                if (e.status == 'success')
                    document.querySelector('.homepage').style.display = 'block'
            })
        }
    }
</script>

<style>
    .logo {
        position: absolute;
        top: 1.3rem;
        left: 1.3rem;
        z-index: 444;
    }
    .logo > a > img {
        width: 130px;
    }
    .homepage {
        display: none;
    }

    @media screen and (max-width: 523px) {
        .logo {
            text-align: center;
            padding-top: 20px;
            display: none;
        }
    }

</style>
