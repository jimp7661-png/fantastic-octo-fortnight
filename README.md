<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NovaVest Capital</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Poppins',sans-serif;
}

html{
scroll-behavior:smooth;
}

body{
background:#eef4ff;
overflow-x:hidden;
color:#222;
}

.app{
max-width:480px;
margin:auto;
background:#f8fbff;
min-height:100vh;
padding-bottom:100px;
}

/* LOADER */

#loader{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:#08152f;
display:flex;
justify-content:center;
align-items:center;
flex-direction:column;
z-index:99999;
color:white;
}

.loader-circle{
width:70px;
height:70px;
border-radius:50%;
border:6px solid rgba(255,255,255,0.2);
border-top:6px solid #4da3ff;
animation:spin 1s linear infinite;
margin-bottom:15px;
}

@keyframes spin{
100%{
transform:rotate(360deg);
}
}

/* TOPBAR */

.topbar{
background:#08152f;
padding:18px;
display:flex;
justify-content:space-between;
align-items:center;
position:sticky;
top:0;
z-index:999;
box-shadow:0 5px 15px rgba(0,0,0,0.2);
}

.logo{
display:flex;
align-items:center;
gap:10px;
color:white;
}

.logo i{
font-size:24px;
color:#4da3ff;
}

.logo h2{
font-size:22px;
}

.top-icons i{
color:white;
margin-left:15px;
font-size:18px;
}

/* PAGE */

.page{
display:none;
animation:fade .4s ease;
}

.page.active{
display:block;
}

@keyframes fade{
from{
opacity:0;
transform:translateY(10px);
}
to{
opacity:1;
transform:translateY(0);
}
}

/* SLIDER */

.banner{
margin:15px;
height:200px;
border-radius:25px;
overflow:hidden;
position:relative;
box-shadow:0 10px 25px rgba(0,0,0,0.15);
}

.slide{
position:absolute;
inset:0;
opacity:0;
transition:1s;
}

.slide.active{
opacity:1;
}

.slide img{
width:100%;
height:100%;
object-fit:cover;
}

.overlay{
position:absolute;
inset:0;
background:linear-gradient(to right,rgba(0,0,0,0.7),rgba(0,0,0,0.2));
display:flex;
justify-content:center;
flex-direction:column;
padding:25px;
color:white;
}

.overlay h2{
font-size:30px;
margin-bottom:10px;
}

/* BALANCE */

.balance-card{
margin:15px;
padding:25px;
border-radius:25px;
background:linear-gradient(135deg,#0f5eff,#2ba7ff);
color:white;
box-shadow:0 12px 30px rgba(15,94,255,0.3);
}

.balance-card h1{
font-size:40px;
margin:10px 0;
}

/* ACTIONS */

.actions{
display:grid;
grid-template-columns:repeat(4,1fr);
gap:12px;
margin:15px;
}

.action{
background:white;
padding:15px 10px;
border-radius:20px;
text-align:center;
box-shadow:0 5px 15px rgba(0,0,0,0.08);
cursor:pointer;
transition:.3s;
}

.action:hover{
transform:translateY(-5px);
}

.action i{
font-size:22px;
color:#0f5eff;
margin-bottom:8px;
display:block;
}

.action span{
font-size:13px;
font-weight:600;
}

/* STATS */

.stats{
display:grid;
grid-template-columns:repeat(2,1fr);
gap:15px;
margin:15px;
}

.stat{
background:white;
padding:20px;
border-radius:20px;
box-shadow:0 5px 15px rgba(0,0,0,0.08);
}

.stat h3{
margin-top:10px;
color:#0f5eff;
}

/* NOTICE */

.notice{
margin:15px;
background:white;
padding:12px;
border-radius:15px;
box-shadow:0 5px 15px rgba(0,0,0,0.08);
font-weight:600;
color:#0f5eff;
}

/* TITLES */

.section-title{
margin:20px 15px 10px;
font-size:22px;
font-weight:700;
}

/* PRODUCTS */

.products{
padding:0 15px;
}

.product{
background:white;
border-radius:25px;
overflow:hidden;
margin-bottom:20px;
box-shadow:0 10px 25px rgba(0,0,0,0.08);
transition:.3s;
animation:float 4s infinite ease-in-out;
}

@keyframes float{
0%,100%{
transform:translateY(0);
}
50%{
transform:translateY(-3px);
}
}

.product:hover{
transform:translateY(-5px);
}

.product img{
width:100%;
height:180px;
object-fit:cover;
}

.product-content{
padding:18px;
}

.product-content h3{
margin-bottom:15px;
}

.product-grid{
display:grid;
grid-template-columns:repeat(2,1fr);
gap:10px;
}

.info{
background:#eef4ff;
padding:10px;
border-radius:12px;
text-align:center;
font-size:13px;
}

.btn{
width:100%;
padding:14px;
border:none;
border-radius:15px;
background:linear-gradient(135deg,#0f5eff,#2ba7ff);
color:white;
font-weight:600;
margin-top:15px;
cursor:pointer;
transition:.3s;
}

.btn:hover{
transform:scale(1.03);
}

/* CARD */

.card{
background:white;
margin:15px;
padding:20px;
border-radius:20px;
box-shadow:0 5px 15px rgba(0,0,0,0.08);
}

.history{
display:flex;
justify-content:space-between;
padding:12px 0;
border-bottom:1px solid #eee;
}

.history:last-child{
border:none;
}

.green{
color:green;
font-weight:700;
}

.red{
color:red;
font-weight:700;
}

/* PROFILE */

.profile{
text-align:center;
}

.profile img{
width:90px;
height:90px;
border-radius:50%;
object-fit:cover;
margin-bottom:15px;
}

.menu{
display:flex;
justify-content:space-between;
padding:15px 0;
border-bottom:1px solid #eee;
}

.menu i{
color:#0f5eff;
}

/* FORM */

.form-group{
margin-bottom:15px;
}

.form-group label{
display:block;
margin-bottom:8px;
font-weight:600;
}

.form-group input{
width:100%;
padding:15px;
border-radius:15px;
border:1px solid #ddd;
outline:none;
}

/* SHARE */

.share-buttons{
display:grid;
grid-template-columns:repeat(2,1fr);
gap:12px;
margin-top:15px;
}

.share-btn{
padding:14px;
border:none;
border-radius:15px;
color:white;
font-weight:600;
cursor:pointer;
}

.whatsapp{
background:#25d366;
}

.facebook{
background:#1877f2;
}

.telegram{
background:#0088cc;
}

.twitter{
background:black;
}

.copy-box{
display:flex;
gap:10px;
margin-top:15px;
}

.copy-box input{
flex:1;
padding:12px;
border-radius:12px;
border:1px solid #ddd;
}

.copy-box button{
background:#0f5eff;
color:white;
border:none;
padding:12px 18px;
border-radius:12px;
}

/* NAV */

.bottom-nav{
position:fixed;
bottom:0;
left:50%;
transform:translateX(-50%);
width:100%;
max-width:480px;
background:white;
display:grid;
grid-template-columns:repeat(5,1fr);
padding:12px 5px;
box-shadow:0 -5px 20px rgba(0,0,0,0.1);
z-index:999;
border-top-left-radius:25px;
border-top-right-radius:25px;
}

.nav{
text-align:center;
color:#777;
cursor:pointer;
transition:.3s;
}

.nav.active{
color:#0f5eff;
}

.nav i{
display:block;
font-size:20px;
margin-bottom:5px;
}

/* POPUP */

.popup{
position:fixed;
top:20px;
left:50%;
transform:translateX(-50%);
background:#08152f;
color:white;
padding:14px 22px;
border-radius:15px;
display:none;
z-index:999999;
box-shadow:0 10px 25px rgba(0,0,0,0.25);
}

@media(max-width:400px){

.actions{
grid-template-columns:repeat(2,1fr);
}

}

</style>
</head>

<body>

<div id="loader">
<div class="loader-circle"></div>
<h2>NovaVest Capital</h2>
</div>

<div class="popup" id="popup"></div>

<div class="app">

<div class="topbar">
<div class="logo">
<i class="fa-solid fa-chart-line"></i>
<h2>NovaVest</h2>
</div>

<div class="top-icons">
<i class="fa-solid fa-bell"></i>
<i class="fa-solid fa-user"></i>
</div>
</div>

<!-- HOME -->

<div class="page active" id="home">

<div class="banner">

<div class="slide active">
<img src="https://images.unsplash.com/photo-1520607162513-77705c0f0d4a?q=80&w=1200&auto=format&fit=crop">
<div class="overlay">
<h2>Invest Smarter</h2>
<p>Grow your money daily with NovaVest Capital.</p>
</div>
</div>

<div class="slide">
<img src="https://images.unsplash.com/photo-1559526324-593bc073d938?q=80&w=1200&auto=format&fit=crop">
<div class="overlay">
<h2>Daily Profits</h2>
<p>Earn stable passive income every day.</p>
</div>
</div>

<div class="slide">
<img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=1200&auto=format&fit=crop">
<div class="overlay">
<h2>Secure Platform</h2>
<p>Professional investment experience.</p>
</div>
</div>

</div>

<div class="balance-card">
<p>Total Balance</p>
<h1>₦350,000</h1>
<p>Today's Profit: ₦8,500</p>
</div>

<div class="actions">

<div class="action" onclick="openPage('recharge')">
<i class="fa-solid fa-wallet"></i>
<span>Recharge</span>
</div>

<div class="action" onclick="openPage('withdraw')">
<i class="fa-solid fa-money-bill-transfer"></i>
<span>Withdraw</span>
</div>

<div class="action" onclick="openPage('income')">
<i class="fa-solid fa-chart-simple"></i>
<span>Income</span>
</div>

<div class="action" onclick="openPage('team')">
<i class="fa-solid fa-users"></i>
<span>Team</span>
</div>

</div>

<div class="stats">

<div class="stat">
<p>Total Investment</p>
<h3>₦1.2M</h3>
</div>

<div class="stat">
<p>Total Income</p>
<h3>₦620K</h3>
</div>

<div class="stat">
<p>Today's Income</p>
<h3>₦8,500</h3>
</div>

<div class="stat">
<p>Referral Bonus</p>
<h3>₦42K</h3>
</div>

</div>

<div class="notice">
<marquee>Welcome to NovaVest Capital — Recharge and earn daily stable profits instantly.</marquee>
</div>

<h2 class="section-title">Investment Plans</h2>

<div class="products" id="products"></div>

</div>

<!-- INCOME -->

<div class="page" id="income">

<div class="card">

<h2>Profit Statistics</h2>

<div class="history">
<span>Total Earnings</span>
<strong class="green">₦620,000</strong>
</div>

<div class="history">
<span>Today's Profit</span>
<strong class="green">₦8,500</strong>
</div>

<div class="history">
<span>Total Withdrawals</span>
<strong class="red">₦310,000</strong>
</div>

</div>

<div class="card">

<h2>Earnings History</h2>

<div class="history">
<span>Daily Profit</span>
<strong class="green">+₦2,500</strong>
</div>

<div class="history">
<span>Referral Bonus</span>
<strong class="green">+₦8,000</strong>
</div>

<div class="history">
<span>Product Income</span>
<strong class="green">+₦5,200</strong>
</div>

</div>

</div>

<!-- SHARE -->

<div class="page" id="share">

<div class="card">

<h2>Invite & Earn</h2>

<p style="margin-top:10px;">
Earn commissions by inviting your friends.
</p>

<div class="copy-box">
<input type="text" id="refLink" value="https://novavestcapital.com/ref123">
<button onclick="copyReferral()">Copy</button>
</div>

<div class="share-buttons">

<button class="share-btn whatsapp">
WhatsApp
</button>

<button class="share-btn facebook">
Facebook
</button>

<button class="share-btn telegram">
Telegram
</button>

<button class="share-btn twitter">
Twitter
</button>

</div>

</div>

</div>

<!-- TEAM -->

<div class="page" id="team">

<div class="card">

<h2>Team Statistics</h2>

<div class="history">
<span>Total Team Members</span>
<strong>152</strong>
</div>

<div class="history">
<span>Total Referral Bonus</span>
<strong class="green">₦85,000</strong>
</div>

<div class="history">
<span>Today's Team Income</span>
<strong class="green">₦3,500</strong>
</div>

</div>

<div class="card">

<h2>Invite Friends</h2>

<div class="copy-box">
<input type="text" id="inviteLink" value="https://novavestcapital.com/invite">
<button onclick="copyInvite()">Copy</button>
</div>

<button class="btn" onclick="showPopup('Invite link copied successfully')">
Invite Now
</button>

</div>

</div>

<!-- PROFILE -->

<div class="page" id="mine">

<div class="card profile">

<img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?q=80&w=1200&auto=format&fit=crop">

<h2>Mind Prosperity</h2>
<p>VIP Investor</p>

<br>

<h1 style="color:#0f5eff;">₦350,000</h1>

</div>

<div class="card">

<div class="menu">
<span>Message Center</span>
<i class="fa-solid fa-angle-right"></i>
</div>

<div class="menu">
<span>Change Password</span>
<i class="fa-solid fa-angle-right"></i>
</div>

<div class="menu">
<span>Add Bank Card</span>
<i class="fa-solid fa-angle-right"></i>
</div>

<div class="menu">
<span>Deposit Record</span>
<i class="fa-solid fa-angle-right"></i>
</div>

<div class="menu">
<span>Withdrawal Record</span>
<i class="fa-solid fa-angle-right"></i>
</div>

<div class="menu">
<span>Download App</span>
<i class="fa-solid fa-angle-right"></i>
</div>

<div class="menu">
<span>Language Settings</span>
<i class="fa-solid fa-angle-right"></i>
</div>

<div class="menu">
<span>Logout</span>
<i class="fa-solid fa-angle-right"></i>
</div>

</div>

</div>
<div class="menu" onclick="window.open('https://wa.me/2348089932475')">
<span>Customer Support</span>
<i class="fa-solid fa-headset"></i>
</div>

<div class="menu" onclick="window.open('https://chat.whatsapp.com/LjvvQaj2hov3gg3c29Rdwd')">
    <span>Customer Support</span>
    <i class="fa-solid fa-headset"></i>
</div>

<!-- WITHDRAW -->

<div class="page" id="withdraw">

<div class="card">

<h2>Withdraw Funds</h2>

<br>

<div class="form-group">
<label>Account Name</label>
<input type="text" placeholder="Enter account name">
</div>

<div class="form-group">
<label>Bank Name</label>
<input type="text" placeholder="Enter bank name">
</div>

<div class="form-group">
<label>Account Number</label>
<input type="number" placeholder="Enter account number">
</div>

<div class="form-group">
<label>Amount</label>
<input type="number" placeholder="Enter amount">
</div>

<button class="btn" onclick="showPopup('Withdrawal Submitted Successfully')">
Submit Withdrawal
</button>

</div>

</div>

<!-- RECHARGE -->

<div class="page" id="recharge">

<div class="card">

<h2>Recharge Account</h2>

<div class="history">
<span>Bank Name</span>
<strong>Opay Bank</strong>
</div>

<div class="history">
<span>Account Name</span>
<strong>NovaVest Prince-AI</strong>
</div>

<div class="history">
<span>Account Number</span>
<strong>8089932475</strong>
</div>

<div class="copy-box">
<input type="text" value="8089932475">
<button onclick="copyAccount()">Copy</button>
</div>

<br>

<input type="file" class="btn">

<button class="btn" onclick="showPopup('Payment Screenshot Uploaded')">
Submit Recharge
</button>

</div>

</div>

<!-- NAV -->

<div class="bottom-nav">

<div class="nav active" onclick="openPage('home',this)">
<i class="fa-solid fa-house"></i>
Home
</div>

<div class="nav" onclick="openPage('income',this)">
<i class="fa-solid fa-chart-column"></i>
Income
</div>

<div class="nav" onclick="openPage('share',this)">
<i class="fa-solid fa-share-nodes"></i>
Share
</div>

<div class="nav" onclick="openPage('team',this)">
<i class="fa-solid fa-users"></i>
Team
</div>

<div class="nav" onclick="openPage('mine',this)">
<i class="fa-solid fa-user"></i>
Mine
</div>

</div>

</div>

<script>

/* LOADER */

window.onload = function(){

setTimeout(function(){

document.getElementById("loader").style.display = "none";

},2000);

};

/* PRODUCTS */

const products = [

{
name:'Starter Plan',
amount:'₦5,000',
daily:'₦500',
total:'₦15,000',
days:'30 Days',
quota:'120 Remaining',
img:'https://images.unsplash.com/photo-1526628953301-3e589a6a8b74?q=80&w=1200&auto=format&fit=crop'
},

{
name:'Silver Plan',
amount:'₦10,000',
daily:'₦1,000',
total:'₦30,000',
days:'30 Days',
quota:'85 Remaining',
img:'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?q=80&w=1200&auto=format&fit=crop'
},

{
name:'Gold Plan',
amount:'₦20,000',
daily:'₦2,000',
total:'₦60,000',
days:'30 Days',
quota:'70 Remaining',
img:'https://images.unsplash.com/photo-1554224155-6726b3ff858f?q=80&w=1200&auto=format&fit=crop'
},

{
name:'VIP 1',
amount:'₦50,000',
daily:'₦5,000',
total:'₦150,000',
days:'30 Days',
quota:'50 Remaining',
img:'https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?q=80&w=1200&auto=format&fit=crop'
},

{
name:'VIP 2',
amount:'₦100,000',
daily:'₦10,000',
total:'₦300,000',
days:'30 Days',
quota:'42 Remaining',
img:'https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=1200&auto=format&fit=crop'
},

{
name:'VIP 3',
amount:'₦150,000',
daily:'₦15,000',
total:'₦450,000',
days:'30 Days',
quota:'31 Remaining',
img:'https://images.unsplash.com/photo-1559526324-593bc073d938?q=80&w=1200&auto=format&fit=crop'
},

{
name:'Premium Plan',
amount:'₦200,000',
daily:'₦20,000',
total:'₦600,000',
days:'30 Days',
quota:'20 Remaining',
img:'https://images.unsplash.com/photo-1520607162513-77705c0f0d4a?q=80&w=1200&auto=format&fit=crop'
},

{
name:'Elite Plan',
amount:'₦300,000',
daily:'₦30,000',
total:'₦900,000',
days:'30 Days',
quota:'15 Remaining',
img:'https://images.unsplash.com/photo-1521791136064-7986c2920216?q=80&w=1200&auto=format&fit=crop'
},

{
name:'Diamond Plan',
amount:'₦500,000',
daily:'₦50,000',
total:'₦1.5M',
days:'30 Days',
quota:'8 Remaining',
img:'https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?q=80&w=1200&auto=format&fit=crop'
},

{
name:'Executive Plan',
amount:'₦1,000,000',
daily:'₦100,000',
total:'₦3M',
days:'30 Days',
quota:'5 Remaining',
img:'https://images.unsplash.com/photo-1504384308090-c894fdcc538d?q=80&w=1200&auto=format&fit=crop'
}

];

const container = document.getElementById("products");

products.forEach(product=>{

container.innerHTML += `

<div class="product">

<img src="${product.img}">

<div class="product-content">

<h3>${product.name}</h3>

<div class="product-grid">

<div class="info">
Investment
<br>
<strong>${product.amount}</strong>
</div>

<div class="info">
Daily Profit
<br>
<strong>${product.daily}</strong>
</div>

<div class="info">
Total Profit
<br>
<strong>${product.total}</strong>
</div>

<div class="info">
Duration
<br>
<strong>${product.days}</strong>
</div>

</div>

<br>

<p><strong>${product.quota}</strong></p>

<button class="btn" onclick="buyPlan('${product.name}')">
Buy Now
</button>

</div>

</div>

`;

});

/* NAVIGATION */

function openPage(page,el){

document.querySelectorAll('.page').forEach(p=>{
p.classList.remove('active');
});

document.getElementById(page).classList.add('active');

document.querySelectorAll('.nav').forEach(n=>{
n.classList.remove('active');
});

if(el){
el.classList.add('active');
}

window.scrollTo({
top:0,
behavior:'smooth'
});

}

/* POPUP */

function showPopup(message){

const popup = document.getElementById("popup");

popup.innerText = message;

popup.style.display = "block";

setTimeout(function(){

popup.style.display = "none";

},2500);

}

/* BUY */

function buyPlan(name){

showPopup(name + " purchased successfully");

}

/* COPY */

function copyReferral(){

const copyText = document.getElementById("refLink");

copyText.select();

document.execCommand("copy");

showPopup("Referral link copied");

}

function copyInvite(){

const copyText = document.getElementById("inviteLink");

copyText.select();

document.execCommand("copy");

showPopup("Invite link copied");

}

function copyAccount(){

navigator.clipboard.writeText("1234567890");

showPopup("Account number copied");

}

/* SLIDER */

let slides = document.querySelectorAll(".slide");

let current = 0;

setInterval(function(){

slides[current].classList.remove("active");

current++;

if(current >= slides.length){
current = 0;
}

slides[current].classList.add("active");

},3000);

</script>

</body>
</html>
