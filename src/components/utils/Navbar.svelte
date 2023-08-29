<script lang="ts">
    import { onMount } from "svelte";

    let isMobileMenuOpen = false;

    onMount(() => {
        const mobileMenuButton = document.querySelector(
            ".mobile-menu-button"
        ) as HTMLButtonElement;
        const mobileMenuList = document.querySelector(
            ".mobile-menu-list"
        ) as HTMLUListElement;

        mobileMenuButton.addEventListener("click", () => {
            isMobileMenuOpen = !isMobileMenuOpen;
        });
    });
</script>

<nav>
    <div class="logo">
        <img src="images/logo.jpg" alt="Wallon Logo" />
    </div>
    <ul class="right-elements">
        <li><a href="/">Home</a></li>
        <li><a href="/shop">Shop</a></li>
        <li><a href="/about">About Us</a></li>
        <li><a href="/contact">Contact</a></li>
        <li><a href="/cart">Shopping Cart</a></li>
        <li><a href="/login">Shopping Cart</a></li>
    </ul>
    <!-- Mobile Menu -->
    <div class="mobile-menu">
        <button class="mobile-menu-button">
            <span />
            <span />
            <span />
        </button>
        <ul class="mobile-menu-list" class:open={isMobileMenuOpen}>
            <li><a href="/">Home</a></li>
            <li><a href="/shop">Shop</a></li>
            <li><a href="/about">About Us</a></li>
            <li><a href="/contact">Contact</a></li>
            <li><a href="/cart">Shopping Cart</a></li>
            <li><a href="/login">Login</a></li>
            <!-- Add more menu items here -->
        </ul>
    </div>
</nav>

<style>
    /* Navbar styles */
    nav {
        color: black;
        display: flex;
        position: absolute;
        width: -webkit-fill-available;

        justify-content: space-between;
        align-items: center;
        margin: 10px;

        font-family: "Helvetica Rounded", Arial, sans-serif;
        font-size: 1.2rem;
        font-weight: bold;

        height: 80px;
        z-index: 10;
    }

    .logo {
        display: flex;
        align-items: center;
    }

    .logo img {
        max-width: 100px;
        /* Adjust size of logo */
    }

    nav a {
        text-shadow: 0 0 1px black;
        text-decoration: none;
        color: black;
        transition: color 0.3s;
    }

    nav a:hover {
        color: white;
    }

    .right-elements {
        list-style: none;
        display: flex;
        align-items: center;
    }

    .right-elements li {
        margin-right: 20px;
    }

    .right-elements a {
        text-decoration: none;
        color: #333;
        font-weight: bold;
        transition: color 0.3s;
    }

    .right-elements a:hover {
        color: #ff6600;
    }

    /* Mobile Menu styles */

    .mobile-menu {
        height: 100%;
        top: 0;
        left: 0;
        position: absolute;
        width: 100%;
        z-index: 0;
        justify-content: center;
        display: none;
        flex-direction: column;
    }

    .mobile-menu-button {
        top: 50%;
        all: unset;
        transition: top 0.3s;
        display: inline-block;
        cursor: pointer;
        padding: 10px;
        position: absolute;
        z-index: 101;
        right: 0;
    }

    :global(.mobile-menu-button.open) {
        top: -20px;
    }

    .mobile-menu-button span {
        display: none;
        width: 25px;
        height: 3px;
        background-color: black;
        margin: 5px 0;
        transition: transform 0.3s;
    }

    .mobile-menu-button span:first-child {
        transform-origin: top left;
    }

    :global(.mobile-menu-button.open span:first-child) {
        transform: rotate(45deg);
    }

    :global(.mobile-menu-button.open span:nth-child(2)) {
        opacity: 0;
    }

    :global(.mobile-menu-button.open span:last-child) {
        transform-origin: bottom left;
        transform: rotate(-45deg);
    }

    :global(.mobile-menu-button.open span) {
        background-color: #333;
    }

    .mobile-menu-list {
        display: none;
        list-style: none;
        padding: 0;
        background-color: white;
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        text-align: center;
        z-index: 100;
    }

    :global(.mobile-menu-list.open) {
        padding-top: 0px;
        margin-top: 0px;
        top: 0;
        border-top: none;
        display: block !important;
        animation: slide-down 0.3s ease forwards;
    }

    .mobile-menu-list li {
        height: 30px;
    }

    .mobile-menu-list a {
        height: 100%;
        background-color: white;
        display: block;
        color: #333;
        text-decoration: none;
        font-weight: bold;
        font-size: 18px;
        width: 100%;
    }

    @media (max-width: 768px) {
        nav {
            padding: 10px 5px;
            padding-right: 0;
        }

        nav ul {
            display: none;
        }

        .right-elements {
            display: none;
        }

        .mobile-menu {
            display: flex;
            /* Show in mobile view */
        }

        .right-elements a {
            margin-left: 10px;
        }

        .mobile-menu-button span {
            display: block;
            width: 25px;
            height: 3px;
            background-color: black;
            margin: 5px 0;
        }

        @keyframes slide-down {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }

            to {
                transform: translateY(0);
                opacity: 1;
            }
        }
    }
</style>
