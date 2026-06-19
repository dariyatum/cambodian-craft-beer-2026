<template>

<div class="container">

    <h1 class="title">
        Meet The Brewers
    </h1>

    <div class="divider">
        ❦ ❦ ❦
    </div>

    <BreweryList/>

</div>

</template>



<style>
    *{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Inter',sans-serif;
}
    

body{
    background:
        linear-gradient(
            rgba(136, 87, 65, 0.88),
            rgba(255, 212, 193, 0.88)
        ),
        url('https://images.unsplash.com/photo-1514362545857-3bc16c4c7d1b');

    background-size: cover;
    background-position: center;
    background-attachment: fixed;

    min-height: 100vh;
}

.container{
    max-width:1200px;
    margin:auto;
    padding:60px 20px;
}

.title{
    color:#f8e7c1;
    font-size:3.2rem;
    font-weight:800;
    text-transform:uppercase;
    letter-spacing:4px;

    text-shadow:
        0 2px 8px rgba(0,0,0,.5),
        0 6px 20px rgba(0,0,0,.4);
}
.subtitle{
    text-align:center;
    color:#a37558;
    margin-bottom:40px;
}

.brewery-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
    gap:24px;
}

.brewery-card{
    background:
        linear-gradient(
            180deg,
            #f8f0dc 0%,
            #efe2c0 100%
        );

    border: 3px solid #c89b3c;
    border-radius: 18px;

    padding: 25px;

    display: flex;
    flex-direction: column;

    box-shadow:
        0 8px 20px rgba(0,0,0,.25),
        inset 0 0 15px rgba(255,255,255,.5);

    position: relative;

    transition: .3s ease;
}

.brewery-card:hover{
    transform: translateY(-8px);
    box-shadow:
        0 12px 30px rgba(0,0,0,.3),
        inset 0 0 15px rgba(255,255,255,.5);
}

.logo{
    height:130px;
    display:flex;
    justify-content:center;
    align-items:center;
    margin-bottom:20px;
}

.logo img{
    width:100px;
    height:100px;

    object-fit:contain;

    background:#fffaf0;

    border-radius:50%;

    border:4px solid #c89b3c;

    padding:10px;

    box-shadow:
        0 4px 12px rgba(0,0,0,.15);
}
.brewery-card h3{
    font-size:1.3rem;
    margin-bottom:12px;
    color:#2d1a10;
}

.brewery-card p{
    color:#362d26;
    line-height:1.6;
    flex-grow:1;
    margin-bottom:20px;
}

.btn{
    background:#7e2527;

    color:white;

    border:2px solid #d7a332;

    border-radius:10px;

    padding:12px 20px;

    font-weight:600;

    text-decoration:none;

    text-align:center;

    transition:.3s;
}

.btn:hover{
    background:#5f1b1d;
    transform:translateY(-2px);
}
.divider{
    text-align:left;
    color:#C89B3C;
    font-size:1.8rem;
    margin-bottom:40px;
}

@media(max-width:768px){

    .title{
        font-size:2rem;
    }

    .brewery-grid{
        grid-template-columns:1fr;
    }

}
</style>

