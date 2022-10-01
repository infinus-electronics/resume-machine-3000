<script>
    export let text;
    export let uc = false;
    if(uc){
        text = text.toUpperCase();
    }
    
</script>

<h2>{text}</h2>

<style lang="scss">
    h2 {
        margin: 0;
        margin-bottom: 00.25em;
        font-weight: 700;
        font-size: 18px;
        width: 100%;
        display: inline-block;

        
        border-bottom: solid;
        border-bottom-width: 0.1px; 
        border-color: black;
    }
</style>