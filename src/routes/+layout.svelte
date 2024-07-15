<script>
    const backToTop = () => {
        window.scrollTo( {top: 0, behavior: 'smooth' })
    };
</script>

<header class="header">
    <div class="logo">PARSHWA NAKODA TRAVELS</div>

    <nav class="navbar">
        <a href="../" class="navlink">HOME</a>
        <a href="../pricing" class="navlink">PRICING</a>
        <a href="../about" class="navlink">ABOUT</a>
    </nav>
</header>

<slot></slot>

<footer class="footer">
    <img src="src/assets/layered-steps.svg" alt="steps" class="footer-waves">

    <div class="footer-content">
        <div class="footer-main">
            <div class="info">
                <div class="contact-details">
                    <h2 class="footer-header">Contact Details</h2>
                    <a href="https://maps.app.goo.gl/oWyNoKRaxwh3bH519" class="footer-link"><img class="icon" src="src/icons/location.svg" alt="pin"> Indraprastha Complex D, Rastapeth, Pune</a>
                    <a href="mailto:parshwanakodat@gmail.com" class="footer-link"><img class="icon" src="src/icons/mail.svg" alt="mail"> parshwanakodat@gmail.com</a>
                    <a href="tel:+917972858515" class="footer-link"><img class="icon" src="src/icons/call.svg" alt="call"> +91 79728 58515</a>
                </div>

                <div class="explore-footer">
                    <h2 class="footer-header">Explore</h2>
                    <a href="../" class="footer-link">Home</a>
                    <a href="../pricing" class="footer-link">Pricing</a>
                    <a href="../about" class="footer-link">About</a>
                </div>

                <div class="socials">
                    <h2 class="footer-header">Socials</h2>

                    <a href="https://www.instagram.com/" target="_blank" class="footer-link">Instagram↗</a>
                    <a href="https://www.youtube.com/" target="_blank" class="footer-link">YouTube↗</a>
                    <a href="https://jsdl.in/DT-49UKZ1D3" target="_blank" class="footer-link">Justdial↗</a>
                </div>
            </div>

            <div class="map-embed">
                <iframe title="maps" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d867.3073428188399!2d73.86359475993774!3d18.518892025073434!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bc2c15aece0a363%3A0xa7a75092e9b42fb7!2sIndraprastha%20Complex%20pune!5e0!3m2!1sen!2sin!4v1715929872341!5m2!1sen!2sin" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>
        </div>

        <div class="footer-end">
            <div class="footer-logo"><h1>PN TRAVELS</h1><p>™</p></div>
            <button on:click={backToTop} class="footer-end-text">Back To Top ↑</button>
            <p class="footer-end-text">Copyright © PN Travels 2024</p>
        </div>
    </div>
</footer>

<style>
    .header {
        position: relative;
        width: 100vw;
        height: 5rem;
        display: flex;
        align-items: center;
        justify-content: space-between;
        background: var(--dark-slate-gray);
        color: var(--eggshell);
        box-shadow: 0 0 1rem var(--space-cadet);
        z-index: 1;
    }

    .logo {
        margin: 0.5rem 1rem 0.5rem 1rem;
        font-size: 2.5rem;
        font-weight: 900;
        user-select: none;
        text-shadow: 0 0 1rem var(--muted-grey);
    }

    .navbar {
        display: flex;
        margin: 1rem;
    }

    .navlink {
        margin: 1rem 0.5rem 1rem 0.5rem;
        width: 7rem;
        height: 2.5rem;
        border-radius: 2.5rem;
        font-size: 1.25rem;
        font-weight: 600;
        text-align: center;
        line-height: 2.5rem;
        text-decoration: none;
        background-color: var(--dark-slate-gray);
        color: var(--eggshell);
        box-shadow: 0 0 0.5rem var(--subtle-grey) inset;
        transition: 200ms ease-in-out;
    }

    .navlink:hover {
        font-size: 1.4rem;
        box-shadow: 0 0 0 var(--subtle-grey) inset, 0 0 1rem var(--subtle-grey);
    }

    .footer-waves {
        width: 100vw;
        user-select: none;
        -moz-user-select: none;
        -webkit-user-drag: none;
        -webkit-user-select: none;
        -ms-user-select: none;
    }

    .footer {
        margin-top: 4rem;
        padding: 0;
        bottom: 0;
        display: flex;
        flex-direction: column;
    }

    .footer-content {
        width: 100%;
        padding: 1rem;
        background: var(--dark-slate-gray);
        color: var(--eggshell);
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
    }

    .footer-main {
        width: 100%;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }

    .info {
        height: 24rem;
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        justify-content: center;
    }

    .footer-header {
        margin-bottom: 1rem;
        font-size: 1.5rem;
        text-shadow: 0 0 1rem var(--muted-grey);
    }

    .icon {
        margin: 0;
        padding: 0;
        height: 1rem;
    }

    .contact-details {
        width: 22rem;
        display: flex;
        flex-direction: column;
    }

    .footer-text {
        line-height: 1.5rem;
    }

    .explore-footer {
        margin-left: 2rem;
        display: flex;
        flex-direction: column;
    }

    .socials {
        margin-left: 2rem;
        display: flex;
        flex-direction: column;
    }

    .footer-link {
        width: fit-content;
        line-height: 1.5rem;
        color: var(--eggshell);
        text-decoration: none;
    }

    .footer-link:after {
        content: '';
        width: 0;
        height: 0.125rem;
        display: block;
        margin-top: 0;
        right: 0;
        background: var(--eggshell);
        transition: width 200ms ease-in-out;
    }

    .footer-link:hover:after {
        width: 100%;
        left: 0;
        background: var(--eggshell);
    }

    .map-embed {
        width: min-content;
    }

    .map-embed iframe {
        margin: 0;
        padding: 0;
        width: 40rem;
        height: 24rem;
        border: 0;
        border-radius: 1rem;
        box-shadow: 0 0 1rem var(--muted-grey);
    }

    .footer-end {
        margin-top: 2rem;
        width: 100%;
        display: flex;
        flex-direction: row;
        align-items: flex-end;
        justify-content: space-between;
    }

    .footer-end p {
        font-size: 1rem;
    }

    .footer-logo {
        display: flex;
        flex-direction: row;
    }

    .footer-logo h1 {
        height: 8rem;
        display: inline-block;
        overflow: hidden;
        font-size: 8rem;
        font-weight: 900;
    }

    .footer-logo p {
        font-size: 4rem;
        font-weight: 500;
    }

    .footer-end-text {
        background: none;
        border: none;
        color: var(--eggshell);
    }
</style>
