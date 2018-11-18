<template>
    <div>
        <div class="logo">
            <a href="#">
                <img src="../assets/logo.png" alt="logo">
            </a>
        </div>
        <s-v-g-component/>
        <contact-phone/>
    </div>
</template>
<script>
    import SVGComponent from './SVGComponent'
    import ContactPhone from './ContactPhone'
    export  default {
        name: 'HomeComponent',
        components: {
            SVGComponent,
            ContactPhone
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


    @media screen and (max-width: 523px) {
        .logo {
            text-align: center;
            padding-top: 20px;
            display: none;
        }
    }

</style>
