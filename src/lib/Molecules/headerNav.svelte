<script>
    import logo from '/assets/INK-logo.svg'
    import arrow from '/assets/arrow.svg'
</script>

<nav>
    <a href="/">
        <img class="logo" src={logo} alt="The INk logo" />
    </a>
    <input class="menu-btn" type="checkbox" id="menu-btn" />
    <label class="menu-icon" for="menu-btn">
        <span class="navicon"></span>
    </label>
    <ul class="menu">
        <li>
            <a href="/about">About</a>
        </li>
        <li>
            <a href="/promise">Promise</a>
        </li>
        <li>
            <a href="/becomeSponsor" class="sponsor-button">
                Become a Sponsor
                <span class="arrow"><span/>
            </a>
        </li>
    </ul>
</nav>


<style scoped>

    a {
        color: var(--justWhite);
        font-family: var(--Apercu-font);
        text-transform: uppercase ;
        font-size: 24px;
    }

    .logo{
        height: 3.5em;
        width:  3.5em;
        padding: .4em;
    }

    .logo:hover{
        scale: 1.1;
    }

    /* header */

    nav {
        background-color: var(--charcoal);
        box-shadow: 1px 1px 4px 0 rgba(0,0,0,.1);
        position: fixed;
        width: 100%;
        z-index: 3;
        padding: 0 1em;

    }

    nav ul {
        margin: 0;
        padding: 0;
        list-style: none;
        overflow: hidden;
        background-color: var(--charcoal);
    }

    nav li{
        padding: 2em 0;
    }

    nav li a {
        display: block;
        padding: 20px 20px;
        text-decoration: none;
        text-align: center;
    }

    nav li a:hover,
    nav .menu-btn:hover {
        color: var(--candelLight);
    }

    /* Button */

    nav li:nth-last-child(1){
        display: flex;
        justify-content: center;
    }

    .sponsor-button{
        display: inline-block;
        margin: 0 auto;
        border: none;
        border-radius: 3em;
        padding: 1em 2em;
        background-color: var(--candelLight);
        color: var(--charcoal);
        font-weight: bold;
        transition: .2s ease-in-out;
    }

    .sponsor-button:hover{
        background-color: var(--justWhite);
        color: var(--charcoal);
    }

    /* menu */

    nav .menu {
        clear: both;
        max-height: 0;
        transition: max-height .2s ease-out;
    }

    /* menu icon */

    nav .menu-icon {
        cursor: pointer;
        display: inline-block;
        float: right;
        padding: 44px 44px;
        position: relative;
        user-select: none;
    }

    nav .menu-icon .navicon {
        background: var(--justWhite);
        display: block;
        height: 3px;
        position: relative;
        transition: background .2s ease-out;
        width: 24px;
    }

    nav .menu-icon .navicon:before,
    nav .menu-icon .navicon:after {
        background: var(--justWhite);
        content: '';
        display: block;
        height: 100%;
        position: absolute;
        transition: all .2s ease-out;
        width: 100%;
    }

    nav .menu-icon .navicon:before {
        top: 5px;
    }

    nav .menu-icon .navicon:after {
        top: -5px;
    }

    /* menu btn */

    nav .menu-btn {
        display: none;
    }

    nav .menu-btn:checked ~ .menu {
        max-height: 50vh;
    }

    nav .menu-btn:checked ~ .menu-icon .navicon {
        background: transparent;
    }

    nav .menu-btn:checked ~ .menu-icon .navicon:before {
        transform: rotate(-45deg);
    }

    nav .menu-btn:checked ~ .menu-icon .navicon:after {
        transform: rotate(45deg);
    }

    nav .menu-btn:checked ~ .menu-icon:not(.steps) .navicon:before,
    nav .menu-btn:checked ~ .menu-icon:not(.steps) .navicon:after {
        top: 0;
    }

    /* 48em = 768px */

    @media (min-width: 48em) {

        nav ul{
            display: flex;
            align-items: center;
            padding: 0 3em;
        }

        nav li {
            float: left;
            padding: 1em 0;
        }
        nav li a {
            padding: 20px 30px;
            font-size: 1em;

        }
        nav .menu {
            clear: none;
            float: right;
            max-height: none;
        }
        nav .menu-icon {
            display: none;
        }

        .arrow{
            background-image: url(/assets/arrow.svg);
            background-repeat: no-repeat;
            width: 28px;
            height: 28px;
            display: block;
            position: absolute;
            top: 40px;
            right: 62px;
        }

        .sponsor-button:hover .arrow{
            right: 56px;
        }

    }


</style>