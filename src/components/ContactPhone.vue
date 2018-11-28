<template>
    <div class="phones">
        <a href="#" @click="toggleContact" class="floating-moblie">
            <span class="icon-phone">
                <img src="./../assets/phone-icon.png" alt="icon" class="icon-phone-home">
            </span>
        </a>
        <ul class="list-phone">
            <li v-for="contact in $props.contacts">
                <a v-bind:href="'tel:' + contact.phone">
                    <span class="icon-phone">
                        <img src="./../assets/phone-icon.png" alt="icon" class="icon-phone-home">
                    </span>
                    <span class="phone-name">{{ contact.name }}: </span>
                    <span class="hotline">{{ contact.phone }}</span>
                </a>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    props: ['contacts'],
    name: 'ContactPhone',
    data() {
        return {
            state: true
        }
    },
    methods: {
        toggleContact() {
            if (this.state) {
                document.querySelector('.list-phone').style.display = 'block'
                this.state = false
            } else {
                document.querySelector('.list-phone').style.display = 'none'
                this.state = true
            }
        }
    }
}
</script>

<style>
    .icon-phone {
        position: relative;
        padding-left: 25px;
    }
    .icon-phone-home {
        width: 16px;
        position: absolute;
        left: 0px;
        top: 0px;
    }
    .list-phone {
        position: fixed;
        right: 15px;
        padding: 0;
        list-style: none;
        top: 15px;
        font-weight: 600;
        font-size: 14px;
    }
    .list-phone > li {
        margin: 10px 0;
        background: #fff;
        padding: 6px 15px;
        border-top-left-radius: 12px;
        border-bottom-left-radius: 12px;
    }
    .list-phone .hotline {
        margin-left: 5px;
        color: #eb1b2e;
    }
    .list-phone a {
        text-decoration: none;
        color: #000;
    }
    .floating-moblie {
        position: fixed;
        bottom: 16px;
        left: 16px;
        padding: 6px 56px;
        background: #818285;
        border-radius: 18px;
        display: none;
    }
    .floating-moblie > .icon-phone {
        padding: 0;
    }
    
    .floating-moblie > .icon-phone > .icon-phone-home {
        position: unset;
    }
    @media screen and (max-width: 523px) {
        .floating-moblie {
            display: block;
        }
        .list-phone {
            display: none;
            bottom: 30px;
            left: 0;
            top: unset;
            right: unset;
        }
    }
</style>
