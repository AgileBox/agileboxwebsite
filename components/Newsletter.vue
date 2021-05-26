<template>
    <div>
        <!-- <form class="my-10">
            <input class="px-10 py-3 -mr-1 border border-transparent border-solid rounded-l-sm" type="email" placeholder="Podaj swój e-mail">
            <Btn>Zapisz się</Btn>
        </form> -->
        <div
            class="ml-form-embed"
            data-account="2554897:f9u7w3d0p9"
            data-form="4164994:r8n3r2">
        </div>
    </div>
</template>

<script>

// import Btn from '~/components/Btn.vue'

export default {
    // components: {
    //     Btn
    // },
    mounted() {
        /* eslint-disable */
        (function(m,a,i,l,e,r){ m['MailerLiteObject']=e;function f(){
        var c={ a:arguments,q:[]};var r=this.push(c);return "number"!=typeof r?r:f.bind(c.q);}
        f.q=f.q||[];m[e]=m[e]||f.bind(f.q);m[e].q=m[e].q||f.q;r=a.createElement(i);
        var _=a.getElementsByTagName(i)[0];r.async=1;r.src=l+'?v'+(~~(new Date().getTime()/1000000));
        _.parentNode.insertBefore(r,_);})(window, document, 'script', 'https://static.mailerlite.com/js/universal.js', 'ml');

        var ml_account = ml('accounts', '2554897', 'f9u7w3d0p9', 'load');
        /* eslint-enable */
    }
}
</script>
