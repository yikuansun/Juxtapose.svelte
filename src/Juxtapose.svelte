<script>
    import { onMount } from "svelte";
    import juxJS from "juxtaposejs/build/js/juxtapose.min.js?raw";
    import juxCSS from "juxtaposejs/build/css/juxtapose.css?raw";

    onMount(() => {
        if (!document.getElementById("juxtaposeScript")) {
            let jux = document.createElement("script");
            jux.id = "juxtaposeScript";
            jux.innerHTML = juxJS;
            document.body.appendChild(jux);
        }
        if (!document.getElementById("juxtaposeStyle")) {
            let jux2 = document.createElement("style");
            jux2.id = "juxtaposeStyle";
            jux2.innerHTML = juxCSS;
            document.body.appendChild(jux2);
        }
    });

    export let src1;
    export let src2;
</script>

<div class="juxtapose">
    <img src={src1} alt="before" />
    <img src={src2} alt="after" />
</div>

<style>
    .juxtapose {
        width: 800px;
    }
</style>