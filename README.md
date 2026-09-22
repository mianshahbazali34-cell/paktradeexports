<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>PakTrade Exports | Premium Pakistani Products Worldwide</title>
    <link rel="stylesheet" href="https://github.com/mianshahbazali34-cell/paktradeexports.git">

    <meta name="description"
          content="PakTrade Exports supplies premium Pakistani meat, mangoes, rice, wheat and agricultural products to international markets.">

    <style>

        /* =========================================================
           GLOBAL
        ========================================================= */

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        :root {
            --green: #0b4d2b;
            --dark-green: #062719;
            --gold: #d7a83b;
            --light-gold: #f2ce73;
            --cream: #f7f5ed;
            --white: #ffffff;
            --dark: #101914;
            --gray: #69736d;
            --light-gray: #e9ece8;
        }

        body {
            font-family: "Segoe UI", Arial, sans-serif;
            background: var(--cream);
            color: var(--dark);
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        img {
            display: block;
            width: 100%;
        }

        .container {
            width: min(1180px, 90%);
            margin: auto;
        }


        /* =========================================================
           LOADING SCREEN
        ========================================================= */

        #loader {
            position: fixed;
            inset: 0;
            background: var(--dark-green);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 99999;
            transition: opacity 0.6s ease, visibility 0.6s ease;
        }

        #loader.hide {
            opacity: 0;
            visibility: hidden;
        }

        .loader-logo {
            text-align: center;
            color: white;
        }

        .loader-logo h1 {
            font-size: 34px;
            letter-spacing: 3px;
        }

        .loader-logo span {
            color: var(--gold);
        }

        .loader-line {
            width: 180px;
            height: 3px;
            background: rgba(255,255,255,.2);
            margin-top: 20px;
            overflow: hidden;
        }

        .loader-line::after {
            content: "";
            display: block;
            width: 50%;
            height: 100%;
            background: var(--gold);
            animation: loading 1s infinite ease-in-out;
        }

        @keyframes loading {
            0% {
                transform: translateX(-100%);
            }

            100% {
                transform: translateX(300%);
            }
        }


        /* =========================================================
           NAVBAR
        ========================================================= */

        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 5000;
            transition: .3s;
        }

        header.scrolled {
            background: rgba(6,39,25,.96);
            backdrop-filter: blur(15px);
            box-shadow: 0 5px 30px rgba(0,0,0,.18);
        }

        nav {
            height: 82px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            color: white;
            font-weight: 900;
            font-size: 23px;
            letter-spacing: 1.5px;
        }

        .logo span {
            color: var(--gold);
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 32px;
            list-style: none;
        }

        .nav-links a {
            color: white;
            font-size: 14px;
            font-weight: 600;
            position: relative;
        }

        .nav-links a::after {
            content: "";
            position: absolute;
            left: 0;
            bottom: -8px;
            width: 0;
            height: 2px;
            background: var(--gold);
            transition: .3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-contact {
            background: var(--gold);
            color: var(--dark-green) !important;
            padding: 12px 20px;
            border-radius: 30px;
        }

        .nav-contact::after {
            display: none;
        }

        .menu-btn {
            display: none;
            color: white;
            font-size: 30px;
            cursor: pointer;
        }


        /* =========================================================
           HERO
        ========================================================= */

        .hero {
            min-height: 100vh;
            position: relative;
            display: flex;
            align-items: center;

            background:
                linear-gradient(
                    90deg,
                    rgba(3,27,17,.92) 0%,
                    rgba(3,27,17,.72) 45%,
                    rgba(3,27,17,.25) 100%
                ),
                url("https://images.unsplash.com/photo-1500382017468-9049fed747ef?auto=format&fit=crop&w=2200&q=90");

            background-size: cover;
            background-position: center;
        }

        .hero-content {
            max-width: 760px;
            padding-top: 80px;
        }

        .hero-label {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            color: var(--light-gold);
            font-weight: 700;
            letter-spacing: 3px;
            font-size: 13px;
            margin-bottom: 22px;
        }

        .hero-label::before {
            content: "";
            width: 35px;
            height: 2px;
            background: var(--gold);
        }

        .hero h1 {
            color: white;
            font-size: clamp(48px, 7vw, 82px);
            line-height: .98;
            letter-spacing: -3px;
        }

        .hero h1 span {
            color: var(--light-gold);
        }

        .hero p {
            color: #dce7df;
            font-size: 18px;
            line-height: 1.8;
            max-width: 670px;
            margin: 28px 0;
        }

        .hero-buttons {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            padding: 15px 27px;
            border-radius: 40px;
            font-weight: 700;
            transition: .3s;
        }

        .btn-gold {
            background: var(--gold);
            color: var(--dark-green);
        }

        .btn-gold:hover {
            background: var(--light-gold);
            transform: translateY(-4px);
            box-shadow: 0 10px 25px rgba(0,0,0,.2);
        }

        .btn-outline {
            border: 1px solid rgba(255,255,255,.7);
            color: white;
        }

        .btn-outline:hover {
            background: white;
            color: var(--dark-green);
            transform: translateY(-4px);
        }

        .hero-bottom {
            position: absolute;
            bottom: 30px;
            left: 0;
            width: 100%;
        }

        .hero-bottom-inner {
            display: flex;
            justify-content: space-between;
            color: rgba(255,255,255,.7);
            font-size: 12px;
            letter-spacing: 2px;
        }


        /* =========================================================
           STATS
        ========================================================= */

        .stats-wrapper {
            margin-top: -60px;
            position: relative;
            z-index: 20;
        }

        .stats {
            background: white;
            border-radius: 18px;
            box-shadow: 0 20px 60px rgba(0,0,0,.12);
            display: grid;
            grid-template-columns: repeat(4,1fr);
            overflow: hidden;
        }

        .stat {
            padding: 30px;
            text-align: center;
            border-right: 1px solid var(--light-gray);
        }

        .stat:last-child {
            border-right: 0;
        }

        .stat-number {
            font-size: 34px;
            color: var(--green);
            font-weight: 900;
        }

        .stat p {
            color: var(--gray);
            margin-top: 5px;
            font-size: 14px;
        }


        /* =========================================================
           GENERAL SECTIONS
        ========================================================= */

        section {
            padding: 110px 0;
        }

        .section-heading {
            max-width: 720px;
            margin: 0 auto 60px;
            text-align: center;
        }

        .eyebrow {
            color: var(--gold);
            font-size: 13px;
            font-weight: 800;
            letter-spacing: 3px;
        }

        .section-heading h2 {
            font-size: clamp(34px, 5vw, 52px);
            line-height: 1.1;
            margin: 13px 0 18px;
        }

        .section-heading p {
            color: var(--gray);
            line-height: 1.8;
        }


        /* =========================================================
           PRODUCTS
        ========================================================= */

        #products {
            background: white;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(4,1fr);
            gap: 22px;
        }

        .product-card {
            position: relative;
            background: var(--cream);
            border-radius: 18px;
            overflow: hidden;
            transition: .4s;
            border: 1px solid #e6e9e4;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 45px rgba(0,0,0,.12);
        }

        .product-image {
            height: 270px;
            overflow: hidden;
            position: relative;
        }

        .product-image img {
            height: 100%;
            object-fit: cover;
            transition: .6s;
        }

        .product-card:hover .product-image img {
            transform: scale(1.08);
        }

        .product-tag {
            position: absolute;
            top: 15px;
            left: 15px;
            background: white;
            color: var(--green);
            padding: 7px 12px;
            border-radius: 20px;
            font-size: 11px;
            font-weight: 800;
        }

        .product-content {
            padding: 24px;
        }

        .product-content h3 {
            font-size: 22px;
            margin-bottom: 9px;
        }

        .product-content p {
            color: var(--gray);
            line-height: 1.6;
            font-size: 14px;
        }

        .product-link {
            display: inline-block;
            margin-top: 18px;
            color: var(--green);
            font-weight: 800;
            font-size: 14px;
        }


        /* =========================================================
           ABOUT
        ========================================================= */

        #about {
            background: var(--cream);
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
            align-items: center;
        }

        .about-images {
            position: relative;
        }

        .about-main-image {
            width: 88%;
            height: 540px;
            object-fit: cover;
            border-radius: 20px;
        }

        .about-small-image {
            position: absolute;
            right: 0;
            bottom: -30px;
            width: 45%;
            height: 230px;
            object-fit: cover;
            border: 10px solid var(--cream);
            border-radius: 20px;
        }

        .about-badge {
            position: absolute;
            top: 35px;
            left: -25px;
            background: var(--green);
            color: white;
            padding: 18px 22px;
            border-radius: 12px;
            font-weight: 700;
            box-shadow: 0 10px 30px rgba(0,0,0,.15);
        }

        .about-text .eyebrow {
            display: block;
            margin-bottom: 12px;
        }

        .about-text h2 {
            font-size: clamp(34px, 5vw, 52px);
            line-height: 1.1;
            margin-bottom: 22px;
        }

        .about-text > p {
            color: var(--gray);
            line-height: 1.9;
            margin-bottom: 18px;
        }

        .check-list {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 13px;
            margin-top: 28px;
        }

        .check {
            background: white;
            padding: 15px;
            border-radius: 10px;
            font-weight: 700;
            font-size: 14px;
        }

        .check span {
            color: var(--gold);
            margin-right: 7px;
        }


        /* =========================================================
           EXPORT PROCESS
        ========================================================= */

        #process {
            background: var(--dark-green);
            color: white;
        }

        #process .section-heading p {
            color: #bdccc2;
        }

        .process-grid {
            display: grid;
            grid-template-columns: repeat(4,1fr);
            gap: 20px;
        }

        .process-card {
            padding: 35px 25px;
            border: 1px solid rgba(255,255,255,.13);
            border-radius: 18px;
            background: rgba(255,255,255,.03);
            transition: .3s;
        }

        .process-card:hover {
            background: rgba(255,255,255,.07);
            transform: translateY(-7px);
        }

        .process-number {
            color: var(--gold);
            font-size: 13px;
            font-weight: 900;
            letter-spacing: 2px;
            margin-bottom: 28px;
        }

        .process-icon {
            font-size: 35px;
            margin-bottom: 18px;
        }

        .process-card h3 {
            margin-bottom: 12px;
            font-size: 20px;
        }

        .process-card p {
            color: #b7c5bc;
            line-height: 1.7;
            font-size: 14px;
        }


        /* =========================================================
           WHY US
        ========================================================= */

        #why-us {
            background: white;
        }

        .why-grid {
            display: grid;
            grid-template-columns: repeat(3,1fr);
            gap: 22px;
        }

        .why-card {
            padding: 35px;
            border: 1px solid var(--light-gray);
            border-radius: 18px;
            transition: .3s;
        }

        .why-card:hover {
            border-color: var(--gold);
            transform: translateY(-5px);
        }

        .why-icon {
            width: 55px;
            height: 55px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: #edf3ed;
            font-size: 25px;
            margin-bottom: 22px;
        }

        .why-card h3 {
            margin-bottom: 10px;
        }

        .why-card p {
            color: var(--gray);
            line-height: 1.7;
            font-size: 14px;
        }


        /* =========================================================
           GLOBAL CTA
        ========================================================= */

        .global-cta {
            padding: 100px 0;
            background:
                linear-gradient(rgba(5,35,22,.88),rgba(5,35,22,.88)),
                url("https://images.unsplash.com/photo-1524666041070-9d87656c25bb?auto=format&fit=crop&w=2000&q=85");
            background-size: cover;
            background-position: center;
            text-align: center;
            color: white;
        }

        .global-cta h2 {
            font-size: clamp(35px,5vw,60px);
            margin-bottom: 18px;
        }

        .global-cta p {
            max-width: 650px;
            margin: auto;
            color: #d4e0d8;
            line-height: 1.8;
        }

        .global-cta .btn {
            margin-top: 30px;
        }


        /* =========================================================
           CONTACT
        ========================================================= */

        #contact {
            background: var(--cream);
        }

        .contact-grid {
            display: grid;
            grid-template-columns: .85fr 1.15fr;
            gap: 30px;
        }

        .contact-info {
            background: var(--dark-green);
            border-radius: 20px;
            padding: 45px;
            color: white;
        }

        .contact-info h2 {
            font-size: 36px;
            margin-bottom: 15px;
        }

        .contact-info > p {
            color: #bdccc2;
            line-height: 1.7;
            margin-bottom: 35px;
        }

        .contact-detail {
            margin-bottom: 25px;
        }

        .contact-detail small {
            color: var(--gold);
            display: block;
            font-weight: 800;
            margin-bottom: 5px;
            letter-spacing: 1px;
        }

        .contact-detail div {
            color: white;
        }

        .contact-form {
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 15px 45px rgba(0,0,0,.06);
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }

        .input-group {
            margin-bottom: 16px;
        }

        .input-group label {
            display: block;
            font-size: 13px;
            font-weight: 700;
            margin-bottom: 7px;
        }

        input,
        select,
        textarea {
            width: 100%;
            border: 1px solid #dfe3df;
            padding: 14px 15px;
            border-radius: 9px;
            font-family: inherit;
            outline: none;
            font-size: 14px;
            background: #fafbf9;
            transition: .3s;
        }

        input:focus,
        select:focus,
        textarea:focus {
            border-color: var(--green);
            background: white;
        }

        textarea {
            height: 135px;
            resize: vertical;
        }

        .submit-btn {
            border: 0;
            width: 100%;
            padding: 16px;
            border-radius: 30px;
            background: var(--green);
            color: white;
            font-weight: 800;
            font-size: 15px;
            cursor: pointer;
            transition: .3s;
        }

        .submit-btn:hover {
            background: #073a20;
            transform: translateY(-2px);
        }


        /* =========================================================
           FOOTER
        ========================================================= */

        footer {
            background: #041b10;
            color: white;
            padding: 70px 0 25px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 50px;
        }

        .footer-brand .logo {
            display: inline-block;
            margin-bottom: 18px;
        }

        .footer-brand p {
            color: #aab9b0;
            line-height: 1.8;
            max-width: 400px;
        }

        footer h3 {
            color: var(--gold);
            margin-bottom: 18px;
            font-size: 15px;
        }

        footer ul {
            list-style: none;
        }

        footer li {
            margin-bottom: 11px;
        }

        footer li a {
            color: #aab9b0;
            font-size: 14px;
            transition: .2s;
        }

        footer li a:hover {
            color: white;
        }

        .footer-bottom {
            border-top: 1px solid rgba(255,255,255,.1);
            margin-top: 55px;
            padding-top: 22px;
            text-align: center;
            color: #78877e;
            font-size: 13px;
        }


        /* =========================================================
           WHATSAPP BUTTON
        ========================================================= */

        .whatsapp {
            position: fixed;
            right: 25px;
            bottom: 25px;
            width: 62px;
            height: 62px;
            border-radius: 50%;
            background: #25D366;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 28px;
            z-index: 4000;
            box-shadow: 0 10px 30px rgba(0,0,0,.25);
            transition: .3s;
        }

        .whatsapp:hover {
            transform: scale(1.1);
        }


        /* =========================================================
           SCROLL REVEAL
        ========================================================= */

        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: opacity .8s ease, transform .8s ease;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }


        /* =========================================================
           RESPONSIVE
        ========================================================= */

        @media(max-width: 1000px) {

            .products-grid {
                grid-template-columns: 1fr 1fr;
            }

            .process-grid {
                grid-template-columns: 1fr 1fr;
            }

            .about-grid {
                gap: 40px;
            }

            .footer-grid {
                grid-template-columns: 1fr 1fr;
            }
        }


        @media(max-width: 760px) {

            .nav-links {
                position: absolute;
                top: 82px;
                left: 0;
                width: 100%;
                background: var(--dark-green);
                flex-direction: column;
                gap: 0;
                padding: 15px 0;
                display: none;
            }

            .nav-links.active {
                display: flex;
            }

            .nav-links li {
                width: 100%;
                text-align: center;
                padding: 14px;
            }

            .menu-btn {
                display: block;
                
            }

            .hero {
                background-position: 60% center;
            }

            .hero-bottom {
                display: none;
            }

            .stats {
                grid-template-columns: 1fr 1fr;
            }

            .stat {
                border-bottom: 1px solid var(--light-gray);
            }

            .stat:nth-child(2) {
                border-right: 0;
            }

            .about-grid {
                grid-template-columns: 1fr;
            }

            .about-main-image {
                width: 100%;
            }

            .about-small-image {
                right: 10px;
            }

            .contact-grid {
                grid-template-columns: 1fr;
            }

            .why-grid {
                grid-template-columns: 1fr;
            }

            .form-row {
                grid-template-columns: 1fr;
            }
        }


        @media(max-width: 560px) {

            section {
                padding: 80px 0;
            }

            .products-grid,
            .process-grid,
            .footer-grid {
                grid-template-columns: 1fr;
            }

            .stats {
                grid-template-columns: 1fr;
            }

            .stat {
                border-right: 0;
            }

            .hero h1 {
                font-size: 48px;
            }

            .hero p {
                font-size: 16px;
            }

            .about-main-image {
                height: 400px;
            }

            .about-small-image {
                height: 170px;
            }

            .contact-form,
            .contact-info {
                padding: 28px;
            }
        }

    </style>
</head>


<body>


<!-- =============================================================
     LOADER
============================================================= -->

<div id="loader">

    <div class="loader-logo">

        <h1>
            PAKTRADE<span>EXPORTS</span>
        </h1>

        <div class="loader-line"></div>

    </div>

</div>


<!-- =============================================================
     NAVBAR
============================================================= -->

<header id="header">

    <div class="container">

        <nav>

            <a href="#home" class="logo">
                PAKTRADE<span>EXPORTS</span>
            </a>

            <div class="#menu-btn" id="menuBtn">
                ☰
            </div>

            <ul class="nav-links" id="navLinks">

                <li>
                    <a href="#home">Home</a>
                </li>

                <li>
                    <a href="#products">Products</a>
                </li>

                <li>
                    <a href="#about">About</a>
                </li>

                <li>
                    <a href="#process">Export Process</a>
                </li>

                <li>
                    <a href="#why-us">Why Us</a>
                </li>

                <li>
                    <a href="#contact" class="nav-contact">
                        Get a Quote
                    </a>
                </li>

            </ul>

        </nav>

    </div>

</header>


<!-- =============================================================
     HERO
============================================================= -->

<section class="hero" id="home">

    <div class="container">

        <div class="hero-content reveal">

            <div class="hero-label">
                PREMIUM PAKISTANI EXPORTS
            </div>

            <h1>
                Quality From<br>
                <span>Pakistan.</span><br>
                Delivered Worldwide.
            </h1>

            <p>
                We connect international buyers with carefully
                selected Pakistani products including premium meat,
                mangoes, rice, wheat and agricultural goods.
            </p>

            <div class="hero-buttons">

                <a href="#products" class="btn btn-gold">
                    Explore Products
                </a>

                <a href="#contact" class="btn btn-outline">
                    Request a Quote
                </a>

            </div>

        </div>

    </div>


    <div class="hero-bottom">

        <div class="container hero-bottom-inner">

            <span>PAKISTAN</span>

            <span>GLOBAL TRADE • TRUST • QUALITY</span>

        </div>

    </div>

</section>


<!-- =============================================================
     STATS
============================================================= -->

<div class="stats-wrapper">

    <div class="container">

        <div class="stats reveal">

            <div class="stat">

                <div class="stat-number" data-target="15">
                    0
                </div>

                <p>Export Markets</p>

            </div>

            <div class="stat">

                <div class="stat-number" data-target="20">
                    0
                </div>

                <p>Product Categories</p>

            </div>

            <div class="stat">

                <div class="stat-number" data-target="100">
                    0
                </div>

                <p>Quality Focus %</p>

            </div>

            <div class="stat">

                <div class="stat-number" data-target="24">
                    0
                </div>

                <p>Hours Support</p>

            </div>

        </div>

    </div>

</div>


<!-- =============================================================
     PRODUCTS
============================================================= -->

<section id="products">

    <div class="container">

        <div class="section-heading reveal">

            <div class="eyebrow">
                OUR PRODUCTS
            </div>

            <h2>
                Premium Products From Pakistan
            </h2>

            <p>
                We source and supply a range of Pakistani
                food and agricultural products for international
                buyers and distributors.
            </p>

        </div>


        <div class="products-grid">


            <!-- MEAT -->

            <article class="product-card reveal">

                <div class="product-image">

                    <img
                        src="https://images.unsplash.com/photo-1607623814075-e51df1bdc82f?auto=format&fit=crop&w=1000&q=90"
                        alt="Premium meat">

                    <div class="product-tag">
                        PREMIUM
                    </div>

                </div>

                <div class="product-content">

                    <h3>Premium Meat</h3>

                    <p>
                        Carefully sourced meat products prepared
                        for quality-conscious international markets.
                    </p>

                    <a href="#contact" class="product-link">
                        Request Information →
                    </a>

                </div>

            </article>


            <!-- MANGO -->

            <article class="product-card reveal">

                <div class="product-image">

                    <img
                        src="https://images.unsplash.com/photo-1553279768-865429fa0078?auto=format&fit=crop&w=1000&q=90"
                        alt="Fresh Pakistani mangoes">

                    <div class="product-tag">
                        SEASONAL
                    </div>

                </div>

                <div class="product-content">

                    <h3>Fresh Mangoes</h3>

                    <p>
                        Sweet and naturally flavorful Pakistani
                        mangoes selected for export markets.
                    </p>

                    <a href="#contact" class="product-link">
                        Request Information →
                    </a>

                </div>

            </article>


            <!-- RICE -->

            <article class="product-card reveal">

                <div class="product-image">

                    <img
                        src="https://images.unsplash.com/photo-1586201375761-83865001e31c?auto=format&fit=crop&w=1000&q=90"
                        alt="Premium Pakistani rice">

                    <div class="product-tag">
                        EXPORT
                    </div>

                </div>

                <div class="product-content">

                    <h3>Premium Rice</h3>

                    <p>
                        Quality Pakistani rice varieties suitable
                        for wholesalers, distributors and retailers.
                    </p>

                    <a href="#contact" class="product-link">
                        Request Information →
                    </a>

                </div>

            </article>


            <!-- WHEAT -->

            <article class="product-card reveal">

                <div class="product-image">

                    <img
                        src="https://images.unsplash.com/photo-1500382017468-9049fed747ef?auto=format&fit=crop&w=1000&q=90"
                        alt="Wheat and agricultural products">

                    <div class="product-tag">
                        AGRICULTURE
                    </div>

                </div>

                <div class="product-content">

                    <h3>Wheat & Grains</h3>

                    <p>
                        Agricultural products sourced through
                        reliable Pakistani supply networks.
                    </p>

                    <a href="#contact" class="product-link">
                        Request Information →
                    </a>

                </div>

            </article>

        </div>

    </div>

</section>


<!-- =============================================================
     ABOUT
============================================================= -->

<section id="about">

    <div class="container">

        <div class="about-grid">

            <div class="about-images reveal">

                <img
                    class="about-main-image"
                    src="https://images.unsplash.com/photo-1531973576160-7125cd663d86?auto=format&fit=crop&w=1200&q=90"
                    alt="International export business">

                <img
                    class="about-small-image"
                    src="https://images.unsplash.com/photo-1524666041070-9d87656c25bb?auto=format&fit=crop&w=800&q=85"
                    alt="Global shipping">

                <div class="about-badge">
                    🇵🇰 Pakistan<br>
                    <small>To The World</small>
                </div>

            </div>


            <div class="about-text reveal">

                <span class="eyebrow">
                    ABOUT OUR COMPANY
                </span>

                <h2>
                    Built On Quality.<br>
                    Driven By Trade.
                </h2>

                <p>
                    PakTrade Exports is a Pakistan-based export
                    business focused on connecting local suppliers
                    with international buyers.
                </p>

                <p>
                    We aim to make international sourcing simple
                    by focusing on product quality, professional
                    communication and dependable supply.
                </p>


                <div class="check-list">

                    <div class="check">
                        <span>✓</span>
                        Quality Sourcing
                    </div>

                    <div class="check">
                        <span>✓</span>
                        Professional Packaging
                    </div>

                    <div class="check">
                        <span>✓</span>
                        Reliable Supply
                    </div>

                    <div class="check">
                        <span>✓</span>
                        Global Shipping
                    </div>

                </div>

            </div>

        </div>

    </div>

</section>


<!-- =============================================================
     EXPORT PROCESS
============================================================= -->

<section id="process">

    <div class="container">

        <div class="section-heading reveal">

            <div class="eyebrow">
                OUR EXPORT PROCESS
            </div>

            <h2>
                From Source To Shipment
            </h2>

            <p>
                A professional process designed to keep
                international trade clear and organized.
            </p>

        </div>


        <div class="process-grid">


            <div class="process-card reveal">

                <div class="process-number">
                    01 — SOURCE
                </div>

                <div class="process-icon">
                    🌾
                </div>

                <h3>
                    Product Sourcing
                </h3>

                <p>
                    We connect with trusted suppliers and
                    source products according to buyer requirements.
                </p>

            </div>


            <div class="process-card reveal">

                <div class="process-number">
                    02 — CHECK
                </div>

                <div class="process-icon">
                    🔍
                </div>

                <h3>
                    Quality Check
                </h3>

                <p>
                    Products are reviewed and prepared according
                    to agreed specifications.
                </p>

            </div>


            <div class="process-card reveal">

                <div class="process-number">
                    03 — PACK
                </div>

                <div class="process-icon">
                    📦
                </div>

                <h3>
                    Packaging
                </h3>

                <p>
                    Products are professionally prepared for
                    transportation and international handling.
                </p>

            </div>


            <div class="process-card reveal">

                <div class="process-number">
                    04 — SHIP
                </div>

                <div class="process-icon">
                    🚢
                </div>

                <h3>
                    Global Delivery
                </h3>

                <p>
                    We coordinate the export process and shipment
                    toward the agreed destination.
                </p>

            </div>

        </div>

    </div>

</section>


<!-- =============================================================
     WHY US
============================================================= -->

<section id="why-us">

    <div class="container">

        <div class="section-heading reveal">

            <div class="eyebrow">
                WHY CHOOSE US
            </div>

            <h2>
                A Better Way To Source From Pakistan
            </h2>

            <p>
                We focus on the details that matter when
                working with international buyers.
            </p>

        </div>


        <div class="why-grid">


            <div class="why-card reveal">

                <div class="why-icon">
                    🌍
                </div>

                <h3>
                    International Focus
                </h3>

                <p>
                    We are focused on serving international
                    buyers and building long-term trade relationships.
                </p>

            </div>


            <div class="why-card reveal">

                <div class="why-icon">
                    ⭐
                </div>

                <h3>
                    Quality First
                </h3>

                <p>
                    Product quality and buyer requirements
                    remain central to our sourcing approach.
                </p>

            </div>


            <div class="why-card reveal">

                <div class="why-icon">
                    🤝
                </div>

                <h3>
                    Reliable Communication
                </h3>

                <p>
                    Clear communication helps make every
                    international order easier to manage.
                </p>

            </div>


            <div class="why-card reveal">

                <div class="why-icon">
                    📦
                </div>

                <h3>
                    Flexible Orders
                </h3>

                <p>
                    We discuss product specifications,
                    packaging and quantities according to requirements.
                </p>

            </div>


            <div class="why-card reveal">

                <div class="why-icon">
                    🚢
                </div>

                <h3>
                    Export Support
                </h3>

                <p>
                    We coordinate the export process from
                    product preparation through shipment.
                </p>

            </div>


            <div class="why-card reveal">

                <div class="why-icon">
                    💼
                </div>

                <h3>
                    Long-Term Business
                </h3>

                <p>
                    Our goal is to develop trusted,
                    long-term relationships with buyers.
                </p>

            </div>

        </div>

    </div>

</section>


<!-- =============================================================
     GLOBAL CTA
============================================================= -->

<section class="global-cta">

    <div class="container reveal">

        <div class="eyebrow">
            READY TO TRADE?
        </div>

        <h2>
            Let's Bring Pakistani Products<br>
            To Your Market.
        </h2>

        <p>
            Tell us what you are looking for and our team
            can discuss product availability, specifications,
            quantities and export requirements.
        </p>

        <a href="#contact" class="btn btn-gold">
            Start an Inquiry
        </a>

    </div>

</section>


<!-- =============================================================
     CONTACT
============================================================= -->

<section id="contact">

    <div class="container">

        <div class="section-heading reveal">

            <div class="eyebrow">
                CONTACT US
            </div>

            <h2>
                Request A Quote
            </h2>

            <p>
                Interested in our products? Send your
                requirements and we will get back to you.
            </p>

        </div>


        <div class="contact-grid">


            <div class="contact-info reveal">

                <h2>
                    Let's Talk Business
                </h2>

                <p>
                    Whether you are a wholesaler, distributor,
                    retailer or international buyer, contact us
                    with your requirements.
                </p>


                <div class="contact-detail">

                    <small>
                        LOCATION
                    </small>

                    Pakistan

                </div>


                <div class="contact-detail">

                    <small>
                        EMAIL
                    </small>

                    info@paktradeexports.com

                </div>


                <div class="contact-detail">

                    <small>
                        PHONE
                    </small>

                    +92 321 2555567

                </div>


                <div class="contact-detail">

                    <small>
                        BUSINESS HOURS
                    </small>

                    Monday — Saturday

                </div>

            </div>


            <div class="contact-form reveal">

                <form id="quoteForm">

                    <div class="form-row">

                        <div class="input-group">

                            <label>
                                Your Name
                            </label>

                            <input
                                type="text"
                                id="name"
                                placeholder="Enter your name"
                                required>

                        </div>


                        <div class="input-group">

                            <label>
                                Email Address
                            </label>

                            <input
                                type="email"
                                id="email"
                                placeholder="Enter your email"
                                required>

                        </div>

                    </div>


                    <div class="form-row">

                        <div class="input-group">

                            <label>
                                Company
                            </label>

                            <input
                                type="text"
                                id="company"
                                placeholder="Company name">

                        </div>


                        <div class="input-group">

                            <label>
                                Country
                            </label>

                            <input
                                type="text"
                                id="country"
                                placeholder="Your country">

                        </div>

                    </div>


                    <div class="input-group">

                        <label>
                            Product
                        </label>

                        <select id="product" required>

                            <option value="">
                                Select a product
                            </option>

                            <option value="Meat">
                                Premium Meat
                            </option>

                            <option value="Mangoes">
                                Fresh Mangoes
                            </option>

                            <option value="Rice">
                                Premium Rice
                            </option>

                            <option value="Wheat">
                                Wheat & Grains
                            </option>

                            <option value="Other">
                                Other Product
                            </option>

                        </select>

                    </div>


                    <div class="input-group">

                        <label>
                            Your Requirements
                        </label>

                        <textarea
                            id="message"
                            placeholder="Product quantity, destination, packaging requirements, etc."
                            required></textarea>

                    </div>


                    <button
                        type="submit"
                        class="submit-btn">

                        Send Inquiry

                    </button>

                </form>

            </div>

        </div>

    </div>

</section>


<!-- =============================================================
     FOOTER
============================================================= -->

<footer>

    <div class="container">

        <div class="footer-grid">


            <div class="footer-brand">

                <a href="#home" class="logo">
                    PAKTRADE<span>EXPORTS</span>
                </a>

                <p>
                    Connecting quality Pakistani products
                    with international markets through
                    reliable export solutions.
                </p>

            </div>


            <div>

                <h3>
                    COMPANY
                </h3>

                <ul>

                    <li>
                        <a href="#about">
                            About Us
                        </a>
                    </li>

                    <li>
                        <a href="#why-us">
                            Why Choose Us
                        </a>
                    </li>

                    <li>
                        <a href="#process">
                            Export Process
                        </a>
                    </li>

                </ul>

            </div>


            <div>

                <h3>
                    PRODUCTS
                </h3>

                <ul>

                    <li>
                        <a href="#products">
                            Meat
                        </a>
                    </li>

                    <li>
                        <a href="#products">
                            Mangoes
                        </a>
                    </li>

                    <li>
                        <a href="#products">
                            Rice
                        </a>
                    </li>

                    <li>
                        <a href="#products">
                            Wheat
                        </a>
                    </li>

                </ul>

            </div>


            <div>

                <h3>
                    CONTACT
                </h3>

                <ul>

                    <li>
                        <a href="#contact">
                            Request Quote
                        </a>
                    </li>

                    <li>
                        <a href="mailto:info@paktradeexports.com">
                            Email Us
                        </a>
                    </li>

                    <li>
                        <a href="#contact">
                            Worldwide
                        </a>
                    </li>

                </ul>

            </div>

        </div>


        <div class="footer-bottom">

            © 2026 PakTrade Exports — All Rights Reserved.

        </div>

    </div>

</footer>


<!-- =============================================================
     WHATSAPP
     
     IMPORTANT:
     Replace 923000000000 with your real WhatsApp number.
     Format: country code + number, without + or spaces.
============================================================= -->

<a
    href="https://wa.me/923212555567"
    class="whatsapp"
    target="_blank"
    aria-label="Chat on WhatsApp">

    💬

</a>


<!-- =============================================================
     JAVASCRIPT
============================================================= -->

<script>
    alert("Welcome to PAKTrade Exports")

    /* ---------------------------------------------------------
       LOADER
    --------------------------------------------------------- */
    
    window.addEventListener("load", function () {

        setTimeout(function () {

            document
                .getElementById("loader")
                .classList.add("hide");

        }, 700);

    });


    /* ---------------------------------------------------------
       NAVBAR SCROLL
    --------------------------------------------------------- */

    const header = document.getElementById("header");

    window.addEventListener("scroll", function () {

        if (window.scrollY > 60) {

            header.classList.add("scrolled");

        } else {

            header.classList.remove("scrolled");

        }

    });


    /* ---------------------------------------------------------
       MOBILE MENU
    --------------------------------------------------------- */

    const menuBtn = document.getElementById("menuBtn");
    const navLinks = document.getElementById("navLinks");

    menuBtn.addEventListener("click", function () {

        navLinks.classList.toggle("active");

        if (navLinks.classList.contains("active")) {

            menuBtn.innerHTML = "✕";

        } else {

            menuBtn.innerHTML = "☰";

        }

    });


    /* ---------------------------------------------------------
       CLOSE MOBILE MENU AFTER CLICK
    --------------------------------------------------------- */

    document.querySelectorAll(".nav-links a").forEach(function (link) {

        link.addEventListener("click", function () {

            navLinks.classList.remove("active");

            menuBtn.innerHTML = "☰";

        });

    });


    /* ---------------------------------------------------------
       SCROLL REVEAL
    --------------------------------------------------------- */

    const revealElements =
        document.querySelectorAll(".reveal");

    const revealObserver =
        new IntersectionObserver(

            function (entries) {

                entries.forEach(function (entry) {

                    if (entry.isIntersecting) {

                        entry.target.classList.add("active");

                        revealObserver.unobserve(entry.target);

                    }

                });

            },

            {
                threshold: 0.12
            }

        );


    revealElements.forEach(function (element) {

        revealObserver.observe(element);

    });


    /* ---------------------------------------------------------
       ANIMATED STATISTICS
    --------------------------------------------------------- */

    const counters =
        document.querySelectorAll(".stat-number");

    let counterStarted = false;


    function startCounters() {

        if (counterStarted) return;

        counterStarted = true;

        counters.forEach(function (counter) {

            const target =
                parseInt(counter.getAttribute("data-target"));

            let current = 0;

            const increment =
                Math.max(1, Math.ceil(target / 50));

            const timer =
                setInterval(function () {

                    current += increment;

                    if (current >= target) {

                        current = target;

                        clearInterval(timer);

                    }

                    counter.textContent = current;

                }, 30);

        });

    }


    const statsSection =
        document.querySelector(".stats");

    const statsObserver =
        new IntersectionObserver(

            function (entries) {

                if (entries[0].isIntersecting) {

                    startCounters();

                }

            },

            {
                threshold: 0.5
            }

        );


    statsObserver.observe(statsSection);


    /* ---------------------------------------------------------
       CONTACT FORM
    --------------------------------------------------------- */

    const quoteForm =
        document.getElementById("quoteForm");


    quoteForm.addEventListener("submit", function (event) {

        event.preventDefault();

        const name =
            document.getElementById("name").value;

        const product =
            document.getElementById("product").value;

        alert(
            "Thank you, " +
            name +
            "!\n\nYour inquiry for " +
            product +
            " has been received.\n\n" +
            "We will contact you soon."
        );

        quoteForm.reset();

    });


    /* ---------------------------------------------------------
       SMOOTH SCROLL
    --------------------------------------------------------- */

    document.querySelectorAll('a[href^="#"]').forEach(function (anchor) {

        anchor.addEventListener("click", function (event) {

            const target =
                document.querySelector(
                    this.getAttribute("href")
                );

            if (target) {

                event.preventDefault();

                target.scrollIntoView({
                    behavior: "smooth"
                });

            }

        });

    });

</script>

</body>
</html>
