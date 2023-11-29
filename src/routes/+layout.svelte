<script>
    import '../lib/styles/fonts.css';
    import { Header } from "../lib/index.js";

</script>

<Header />


<slot />

<style>

    :global(*){
        box-sizing: border-box;
        text-decoration: none;
        list-style: none;
        margin: 0;
        padding: 0;
        font-family: var(--Apercu-font);
    }

    /* Color variable */

    :global(:root){
        --charcoal: #051A1A;
        --candelLight: #FFDA1D;
        --justWhite: #FFFFFF;
        --jungleDarkGreen: #0c2121;
        --jungleGreen: #163A3A;
        --plantGreen: #179446;
        --pictonBlue: #3DBAE1;
        --Apercu-font: 'Apercu pro', sans-serif;
        --paragraph-font: 'Jubilat', serif;
        --header-font: 'Kirang Haerang', sans-serif;
        --link-hover-color: #FFDA1D;
        --button-hover-color: #FFFFFF;
        --top-nav-sponsor-button-hover-color: #051A1A;
    }

    :global(body) {
        background-color: var(--jungleDarkGreen);
        color: var(--justWhite);
        width: 100%;
        height: 100vh;
        overflow: hidden;
        overflow-y: scroll;
    }

    :global(h1){
        font-family: var(--header-font);
        font-size: 4em;
        padding: .5em;
        color: var(--candelLight);
    }

</style>