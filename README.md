<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>THE BOSS LOUNGE | Management</title>

<style>

:root{
--gold:#d4af37;
--gold2:#f1d77a;
--black:#080808;
--dark:#111;
--panel:#181818;
--panel2:#202020;
--border:#303030;
--text:#fff;
--muted:#aaa;
--green:#2ecc71;
--red:#e74c3c;
--blue:#3498db;
}

*{
box-sizing:border-box;
}

html{
scroll-behavior:smooth;
}

body{
margin:0;
font-family:Arial,Helvetica,sans-serif;
background:var(--black);
color:var(--text);
}

/* HEADER */

header{
height:70px;
background:#0d0d0d;
border-bottom:1px solid var(--border);
display:flex;
align-items:center;
justify-content:space-between;
padding:0 22px;
position:sticky;
top:0;
z-index:100;
}

.logo{
font-size:19px;
font-weight:900;
letter-spacing:2px;
color:var(--gold);
}

.logo span{
display:block;
font-size:10px;
letter-spacing:4px;
color:#aaa;
margin-top:3px;
}

.clock{
font-size:13px;
color:#bbb;
text-align:right;
}

/* LAYOUT */

.layout{
display:flex;
min-height:calc(100vh - 70px);
}

/* SIDEBAR */

.sidebar{
width:245px;
background:#101010;
border-right:1px solid var(--border);
padding:15px;
flex-shrink:0;
}

.nav-title{
font-size:11px;
color:#777;
text-transform:uppercase;
letter-spacing:2px;
margin:10px 8px;
}

.nav-btn{
width:100%;
border:0;
background:transparent;
color:#ddd;
padding:13px 14px;
border-radius:9px;
margin:3px 0;
text-align:left;
font-size:14px;
cursor:pointer;
transition:.2s;
}

.nav-btn:hover{
background:#242424;
color:var(--gold);
}

.nav-btn.active{
background:linear-gradient(90deg,#29230f,#202020);
color:var(--gold);
border-left:3px solid var(--gold);
}

/* MAIN */

main{
flex:1;
padding:24px;
min-width:0;
}

.section{
display:none;
animation:fade .2s ease;
}

.section.active{
display:block;
}

@keyframes fade{
from{opacity:.3;transform:translateY(3px)}
to{opacity:1;transform:none}
}

.page-title{
margin:0 0 5px;
font-size:25px;
color:var(--gold);
}

.page-subtitle{
margin:0 0 20px;
color:#888;
font-size:13px;
}

/* CARDS */

.cards{
display:grid;
grid-template-columns:
repeat(auto-fit,minmax(180px,1fr));
gap:14px;
}

.card{
background:var(--panel);
border:1px solid var(--border);
border-radius:13px;
padding:18px;
min-height:105px;
}

.card small{
color:#999;
font-size:12px;
}

.card .value{
font-size:22px;
font-weight:800;
margin-top:10px;
color:#fff;
}

.card.gold-card .value{
color:var(--gold);
}

.card.green-card .value{
color:var(--green);
}

.card.red-card .value{
color:var(--red);
}

/* PANELS */

.grid{
display:grid;
grid-template-columns:
repeat(auto-fit,minmax(300px,1fr));
gap:16px;
margin-top:16px;
}

.panel{
background:var(--panel);
border:1px solid var(--border);
border-radius:13px;
padding:18px;
}

.panel h3{
margin-top:0;
color:#eee;
}

/* BUTTONS */

button{
font-family:inherit;
}

.btn{
border:0;
border-radius:8px;
padding:11px 15px;
cursor:pointer;
font-weight:600;
}

.btn-gold{
background:var(--gold);
color:#111;
}

.btn-gold:hover{
background:var(--gold2);
}

.btn-dark{
background:#292929;
color:white;
}

.btn-green{
background:var(--green);
color:#07150d;
}

.btn-red{
background:var(--red);
color:white;
}

.btn-blue{
background:var(--blue);
color:white;
}

.actions{
display:flex;
flex-wrap:wrap;
gap:8px;
}

/* FORMS */

label{
display:block;
font-size:12px;
color:#aaa;
margin-bottom:5px;
}

input,
select{
width:100%;
background:#0c0c0c;
border:1px solid #414141;
border-radius:8px;
padding:12px;
color:white;
outline:none;
margin-bottom:13px;
}

input:focus,
select:focus{
border-color:var(--gold);
}

/* TABLE */

.table-wrapper{
width:100%;
overflow-x:auto;
}

table{
width:100%;
border-collapse:collapse;
min-width:600px;
}

th,
td{
padding:12px 10px;
border-bottom:1px solid #303030;
text-align:left;
font-size:13px;
}

th{
color:var(--gold);
font-size:12px;
text-transform:uppercase;
}

tr:hover{
background:#1e1e1e;
}

/* BADGES */

.badge{
display:inline-block;
padding:5px 9px;
border-radius:20px;
font-size:11px;
background:#333;
}

.badge-new{
background:#3a2d08;
color:var(--gold2);
}

.badge-prep{
background:#172b3b;
color:#64b5f6;
}

.badge-served{
background:#153523;
color:#61e294;
}

.badge-paid{
background:#183b28;
color:#67e39a;
}

.badge-cancel{
background:#3b1818;
color:#ff7777;
}

/* CART */

.cart-item{
display:flex;
justify-content:space-between;
gap:10px;
align-items:center;
background:#111;
border:1px solid #292929;
border-radius:8px;
padding:10px;
margin-bottom:7px;
}

.cart-name{
font-weight:600;
}

.cart-price{
color:var(--gold);
white-space:nowrap;
}

.total-box{
margin-top:15px;
padding:15px;
background:#0f0f0f;
border:1px solid #3b3219;
border-radius:9px;
display:flex;
justify-content:space-between;
align-items:center;
}

.total-label{
color:#aaa;
}

.total-value{
color:var(--gold);
font-size:22px;
font-weight:900;
}

/* ALERT */

.alert{
padding:11px;
border-radius:8px;
background:#281818;
border:1px solid #542626;
color:#ff8585;
margin-bottom:8px;
}

.success{
color:var(--green);
}

.empty{
color:#777;
padding:15px 0;
}

/* STATUS */

.order-card{
background:#111;
border:1px solid #303030;
border-radius:10px;
padding:14px;
margin-bottom:10px;
}

.order-header{
display:flex;
justify-content:space-between;
align-items:center;
gap:10px;
}

.order-table{
font-weight:800;
color:var(--gold);
}

.order-total{
font-size:18px;
font-weight:800;
}

.order-items{
color:#aaa;
font-size:12px;
margin:10px 0;
line-height:1.7;
}

.order-actions{
display:flex;
gap:6px;
flex-wrap:wrap;
}

/* PRINT */

@media print{

header,
.sidebar,
.no-print{
display:none!important;
}

main{
padding:0;
}

body{
background:white;
color:black;
}

.panel,
.card{
border:1px solid #ccc;
background:white;
color:black;
}

}

/* MOBILE */

@media(max-width:800px){

header{
height:62px;
padding:0 14px;
}

.logo{
font-size:15px;
}

.logo span{
font-size:8px;
}

.layout{
display:block;
}

.sidebar{
position:fixed;
bottom:0;
left:0;
right:0;
width:100%;
height:70px;
padding:5px;
display:flex;
overflow-x:auto;
z-index:200;
border-right:0;
border-top:1px solid var(--border);
}

.nav-title{
display:none;
}

.nav-btn{
min-width:105px;
height:58px;
margin:0 2px;
font-size:10px;
text-align:center;
padding:8px 4px;
border-left:0!important;
}

.nav-btn.active{
border-top:2px solid var(--gold);
}

main{
padding:17px;
padding-bottom:90px;
}

.page-title{
font-size:21px;
}

.cards{
grid-template-columns:
repeat(2,minmax(0,1fr));
gap:9px;
}

.card{
padding:13px;
min-height:90px;
}

.card .value{
font-size:17px;
}

.grid{
grid-template-columns:1fr;
}

.panel{
padding:14px;
}

}

/* VERY SMALL */

@media(max-width:390px){

.cards{
grid-template-columns:1fr;
}

.nav-btn{
min-width:92px;
}

}

</style>
</head>


<body>


<!-- HEADER -->

<header>

<div class="logo">
THE BOSS LOUNGE
<span>MANAGEMENT</span>
</div>

<div class="clock" id="clock">
--
</div>

</header>



<div class="layout">


<!-- SIDEBAR -->

<nav class="sidebar">

<div class="nav-title">
Menu principal
</div>

<button class="nav-btn active"
onclick="showSection('dashboard',this)">
📊<br>Dashboard
</button>

<button class="nav-btn"
onclick="showSection('orders',this)">
🧾<br>Commandes
</button>

<button class="nav-btn"
onclick="showSection('cash',this)">
💰<br>Caisse
</button>

<button class="nav-btn"
onclick="showSection('stock',this)">
📦<br>Stock
</button>

<button class="nav-btn"
onclick="showSection('staff',this)">
👥<br>Personnel
</button>

<button class="nav-btn"
onclick="showSection('accounting',this)">
📚<br>Comptabilité
</button>

<button class="nav-btn"
onclick="showSection('bank',this)">
🏦<br>Banque
</button>

<button class="nav-btn"
onclick="showSection('documents',this)">
🧾<br>Documents
</button>

<button class="nav-btn"
onclick="showSection('users',this)">
🔐<br>Utilisateurs
</button>

</nav>



<main>


<!-- DASHBOARD -->

<section id="dashboard" class="section active">

<h1 class="page-title">
📊 Tableau de bord
</h1>

<p class="page-subtitle">
Vue générale de THE BOSS LOUNGE
</p>


<div class="cards">

<div class="card gold-card">
<small>CA encaissé</small>
<div class="value"
id="dashboardCA">
0 GNF
</div>
</div>

<div class="card">
<small>Commandes</small>
<div class="value"
id="dashboardOrders">
0
</div>
</div>

<div class="card red-card">
<small>Dépenses</small>
<div class="value"
id="dashboardExpenses">
0 GNF
</div>
</div>

<div class="card green-card">
<small>Bénéfice</small>
<div class="value"
id="dashboardProfit">
0 GNF
</div>
</div>

<div class="card">
<small>Commandes en attente</small>
<div class="value"
id="dashboardPending">
0
</div>
</div>

<div class="card">
<small>État caisse</small>
<div class="value"
id="dashboardCash">
FERMÉE
</div>
</div>

</div>


<div class="grid">

<div class="panel">

<h3>🔔 Alertes stock</h3>

<div id="alerts">
Aucune alerte.
</div>

</div>


<div class="panel">

<h3>⚡ Actions rapides</h3>

<div class="actions">

<button class="btn btn-gold"
onclick="goTo('orders')">
➕ Nouvelle commande
</button>

<button class="btn btn-dark"
onclick="goTo('cash')">
💰 Ouvrir caisse
</button>

<button class="btn btn-dark"
onclick="goTo('stock')">
📦 Voir stock
</button>

</div>

</div>

</div>

</section>



<!-- COMMANDES -->

<section id="orders" class="section">

<h1 class="page-title">
🧾 Commandes
</h1>

<p class="page-subtitle">
Création et suivi des commandes
</p>


<div class="grid">


<!-- NOUVELLE COMMANDE -->

<div class="panel">

<h3>➕ Nouvelle commande</h3>

<label>
Numéro de table *
</label>

<input
id="tableNumber"
type="text"
placeholder="Exemple : 12"
>


<label>
Produit
</label>

<select id="productSelect">
</select>


<label>
Quantité
</label>

<input
id="quantity"
type="number"
min="1"
value="1"
>


<button
class="btn btn-gold"
onclick="addToCart()">

➕ Ajouter

</button>


<div id="cart"
style="margin-top:15px">
</div>


<div class="total-box">

<span class="total-label">
TOTAL
</span>

<span
class="total-value"
id="orderTotal">

0 GNF

</span>

</div>


<button
class="btn btn-gold"
style="width:100%;margin-top:12px"
onclick="saveOrder()">

📱 Enregistrer + WhatsApp

</button>

</div>



<!-- COMMANDES -->

<div class="panel">

<div style="
display:flex;
justify-content:space-between;
align-items:center;
gap:10px;
">

<h3>
📋 Commandes récentes
</h3>

<button
class="btn btn-dark"
onclick="refresh()">
↻
</button>

</div>

<div id="ordersList">
Aucune commande.
</div>

</div>

</div>

</section>



<!-- CAISSE -->

<section id="cash" class="section">

<h1 class="page-title">
💰 Caisse
</h1>

<p class="page-subtitle">
Gestion des encaissements et dépenses
</p>


<div class="cards">

<div class="card gold-card">
<small>Solde théorique</small>
<div class="value"
id="cashBalance">
0 GNF
</div>
</div>

<div class="card">
<small>Fond de caisse</small>
<div class="value"
id="cashOpening">
0 GNF
</div>
</div>

</div>


<div class="grid">


<div class="panel">

<h3>
🔐 Ouverture / fermeture
</h3>

<label>
Fond de caisse
</label>

<input
id="openingCash"
type="number"
placeholder="Exemple : 500000"
>


<div class="actions">

<button
class="btn btn-gold"
onclick="openCash()">

🔓 Ouvrir

</button>

<button
class="btn btn-red"
onclick="closeCash()">

🔒 Clôturer

</button>

</div>


<p id="cashMessage">
Caisse fermée
</p>

</div>



<div class="panel">

<h3>
💸 Nouvelle dépense
</h3>

<label>
Motif
</label>

<input
id="expenseName"
placeholder="Exemple : achat charbon"
>


<label>
Montant
</label>

<input
id="expenseAmount"
type="number"
placeholder="GNF"
>


<button
class="btn btn-gold"
onclick="addExpense()">

Enregistrer la dépense

</button>

</div>

</div>

</section>



<!-- STOCK -->

<section id="stock" class="section">

<h1 class="page-title">
📦 Stock
</h1>

<p class="page-subtitle">
Suivi des produits et alertes
</p>


<div class="panel">

<div class="table-wrapper">

<table>

<thead>

<tr>

<th>Produit</th>
<th>Prix</th>
<th>Stock</th>
<th>Seuil</th>
<th>État</th>
<th>Actions</th>

</tr>

</thead>

<tbody id="stockTable">
</tbody>

</table>

</div>

</div>

</section>



<!-- PERSONNEL -->

<section id="staff" class="section">

<h1 class="page-title">
👥 Personnel & Paie
</h1>

<p class="page-subtitle">
Gestion des employés
</p>


<div class="panel">

<div class="table-wrapper">

<table>

<thead>

<tr>
<th>Nom</th>
<th>Fonction</th>
<th>Présence</th>
<th>Salaire</th>
<th>Action</th>
</tr>

</thead>

<tbody>

<tr>

<td>
Zenab Diallo
</td>

<td>
Caissière
</td>

<td>
<span class="badge">
À enregistrer
</span>
</td>

<td>
—
</td>

<td>

<button
class="btn btn-dark"
onclick="alert('Module présence à compléter.')">

Présence

</button>

</td>

</tr>

</tbody>

</table>

</div>

</div>

</section>



<!-- COMPTABILITE -->

<section id="accounting" class="section">

<h1 class="page-title">
📚 Comptabilité
</h1>

<p class="page-subtitle">
Recettes, dépenses et résultat
</p>


<div class="cards">

<div class="card gold-card">

<small>Recettes encaissées</small>

<div
class="value"
id="accountingIncome">
0 GNF
</div>

</div>


<div class="card red-card">

<small>Dépenses</small>

<div
class="value"
id="accountingExpense">
0 GNF
</div>

</div>


<div class="card green-card">

<small>Résultat</small>

<div
class="value"
id="accountingResult">
0 GNF
</div>

</div>

</div>

</section>



<!-- BANQUE -->

<section id="bank" class="section">

<h1 class="page-title">
🏦 Banque
</h1>

<p class="page-subtitle">
Gestion des opérations bancaires
</p>


<div class="panel">

<h3>
🏦 Comptes bancaires
</h3>

<p style="color:#aaa">
Cette partie est préparée pour gérer les comptes,
dépôts, retraits, transferts et soldes.
</p>

<button
class="btn btn-gold"
onclick="alert('Module bancaire à connecter.')">

➕ Nouvelle opération

</button>

</div>

</section>



<!-- DOCUMENTS -->

<section id="documents" class="section">

<h1 class="page-title">
🧾 Documents
</h1>

<p class="page-subtitle">
Impression et rapports
</p>


<div class="panel">

<h3>
📄 Documents disponibles
</h3>

<div class="actions">

<button
class="btn btn-gold"
onclick="printPage()">

🖨️ Imprimer

</button>

<button
class="btn btn-dark"
onclick="generateReport()">

📊 Rapport

</button>

</div>

</div>

</section>



<!-- UTILISATEURS -->

<section id="users" class="section">

<h1 class="page-title">
🔐 Utilisateurs
</h1>

<p class="page-subtitle">
Gestion des rôles et permissions
</p>


<div class="panel">

<div class="table-wrapper">

<table>

<thead>

<tr>

<th>Utilisateur</th>
<th>Fonction</th>
<th>Accès</th>

</tr>

</thead>

<tbody>

<tr>
<td>Administrateur</td>
<td>Administration</td>
<td>Tous les modules</td>
</tr>

<tr>
<td>Gérant</td>
<td>Direction</td>
<td>Dashboard, caisse, stock, rapports</td>
</tr>

<tr>
<td>Caissière</td>
<td>Caisse</td>
<td>Commandes, caisse</td>
</tr>

<tr>
<td>Serveuse</td>
<td>Service</td>
<td>Commandes</td>
</tr>

<tr>
<td>Chicha man</td>
<td>Chicha</td>
<td>Préparation</td>
</tr>

<tr>
<td>Comptable</td>
<td>Comptabilité</td>
<td>Comptabilité, banque, documents</td>
</tr>

</tbody>

</table>

</div>

</div>

</section>


</main>

</div>



<script>

/* =====================================================
   CONFIGURATION
===================================================== */

const STORAGE_KEY =
"THE_BOSS_LOUNGE_MANAGEMENT_V2";

const WHATSAPP =
"224628323057";


/* =====================================================
   DONNEES
===================================================== */

const defaultData={

products:[

{
name:"Café",
price:60000,
stock:20,
minimum:5
},

{
name:"Lait en carton 1L",
price:30000,
stock:20,
minimum:5
},

{
name:"Verre de gingembre",
price:10000,
stock:30,
minimum:8
},

{
name:"Champagne 0%",
price:80000,
stock:10,
minimum:3
},

{
name:"Réservation VIP",
price:100000,
stock:10,
minimum:2
},

{
name:"Arôme Café",
price:70000,
stock:20,
minimum:5
},

{
name:"Arôme Déjavu",
price:60000,
stock:20,
minimum:5
},

{
name:"Arôme Hawaï",
price:60000,
stock:20,
minimum:5
},

{
name:"Red Bull",
price:20000,
stock:30,
minimum:8
}

],

orders:[],

expenses:[],

cash:{
open:false,
opening:0
}

};


/* =====================================================
   CHARGEMENT
===================================================== */

let data;

try{

data=
JSON.parse(
localStorage.getItem(STORAGE_KEY)
);

}catch(error){

data=null;

}


if(!data){

data=defaultData;

localStorage.setItem(
STORAGE_KEY,
JSON.stringify(data)
);

}


/* PANIER */

let cart=[];


/* =====================================================
   OUTILS
===================================================== */

function money(value){

return Number(value || 0)
.toLocaleString("fr-FR")
+" GNF";

}


function saveData(){

localStorage.setItem(
STORAGE_KEY,
JSON.stringify(data)
);

refresh();

}


function getRevenue(){

return data.orders

.filter(order=>
order.status==="Payée"
)

.reduce(
(total,order)=>
total+order.total,
0
);

}


function getExpenses(){

return data.expenses

.reduce(
(total,expense)=>
total+expense.amount,
0
);

}


/* =====================================================
   NAVIGATION
===================================================== */

function showSection(id,button){

document
.querySelectorAll(".section")
.forEach(section=>{

section.classList.remove("active");

});


const target=
document.getElementById(id);

if(target){

target.classList.add("active");

}


document
.querySelectorAll(".nav-btn")
.forEach(btn=>{

btn.classList.remove("active");

});


if(button){

button.classList.add("active");

}

}


function goTo(id){

const button=
[...document.querySelectorAll(".nav-btn")]
.find(btn=>
btn.getAttribute("onclick")
?.includes("'"+id+"'")
);

showSection(id,button);

}



/* =====================================================
   PRODUITS
===================================================== */

function loadProducts(){

const select=
document.getElementById(
"productSelect"
);

select.innerHTML="";


data.products.forEach(
(product,index)=>{

const option=
document.createElement("option");

option.value=index;

option.textContent=
product.name+
" — "+
money(product.price);

select.appendChild(option);

});

}



/* =====================================================
   PANIER
===================================================== */

function addToCart(){

const productIndex=
Number(
document.getElementById(
"productSelect"
).value
);

const quantity=
Number(
document.getElementById(
"quantity"
).value
);


if(!quantity || quantity<1){

alert(
"Veuillez indiquer une quantité valide."
);

return;

}


const product=
data.products[productIndex];


const alreadyInCart=
cart
.filter(item=>
item.productIndex===productIndex
)
.reduce(
(total,item)=>
total+item.quantity,
0
);


if(
alreadyInCart+quantity
>
product.stock
){

alert(
"Stock insuffisant pour "+product.name+
". Stock disponible : "+
product.stock
);

return;

}


cart.push({

productIndex:productIndex,

name:product.name,

price:product.price,

quantity:quantity,

total:product.price*quantity

});


renderCart();

}


function renderCart(){

const container=
document.getElementById("cart");

container.innerHTML="";


if(cart.length===0){

container.innerHTML=
"<div class='empty'>Panier vide.</div>";

}
else{

cart.forEach(
(item,index)=>{

const div=
document.createElement("div");

div.className=
"cart-item";

div.innerHTML=`

<div>
<div class="cart-name">
${item.name} × ${item.quantity}
</div>
<div style="font-size:11px;color:#777">
${money(item.price)} / unité
</div>
</div>

<div class="cart-price">
${money(item.total)}
</div>

<button
class="btn btn-red"
onclick="removeFromCart(${index})">
✕
</button>

`;

container.appendChild(div);

});

}


const total=
cart.reduce(
(sum,item)=>
sum+item.total,
0
);


document
.getElementById("orderTotal")
.textContent=
money(total);

}


function removeFromCart(index){

cart.splice(index,1);

renderCart();

}



/* =====================================================
   COMMANDES
===================================================== */

function saveOrder(){

const table=
document
.getElementById("tableNumber")
.value
.trim();


if(!table){

alert(
"Le numéro de table est obligatoire."
);

return;

}


if(cart.length===0){

alert(
"Ajoutez au moins un produit."
);

return;

}


/* Vérification stock */

for(const item of cart){

const product=
data.products[item.productIndex];

if(
product.stock<item.quantity
){

alert(
"Stock insuffisant pour "+
product.name
);

return;

}

}


/* RETRAIT STOCK */

cart.forEach(item=>{

data.products[
item.productIndex
].stock
-=item.quantity;

});


const total=
cart.reduce(
(sum,item)=>
sum+item.total,
0
);


const order={

id:Date.now(),

table:table,

items:JSON.parse(
JSON.stringify(cart)
),

total:total,

status:"Nouvelle",

date:new Date().toISOString()

};


data.orders.push(order);


/* MESSAGE WHATSAPP */

let message=
"THE BOSS LOUNGE\n"+
"━━━━━━━━━━━━━━\n"+
"TABLE : "+table+"\n\n";


cart.forEach(item=>{

message+=
item.name+
" x "+
item.quantity+
" = "+
money(item.total)+
"\n";

});


message+=
"\n━━━━━━━━━━━━━━\n"+
"TOTAL : "+
money(total)+
"\n"+
"Statut : Nouvelle";


const whatsapp=
"https://wa.me/"+
WHATSAPP+
"?text="+
encodeURIComponent(message);


/* Ouvrir WhatsApp */

window.open(
whatsapp,
"_blank"
);


/* RESET */

cart=[];

document
.getElementById("tableNumber")
.value="";

document
.getElementById("quantity")
.value=1;

saveData();

alert(
"Commande enregistrée avec succès."
);

}



/* =====================================================
   STATUT COMMANDE
===================================================== */

function nextStatus(orderId){

const order=
data.orders.find(
o=>o.id===orderId
);


if(!order)return;


const statuses=[

"Nouvelle",
"Préparation",
"Servie",
"Payée"

];


const index=
statuses.indexOf(order.status);


if(index<statuses.length-1){

order.status=
statuses[index+1];

saveData();

}

}


function cancelOrder(orderId){

const order=
data.orders.find(
o=>o.id===orderId
);


if(!order)return;


if(order.status==="Payée"){

alert(
"Une commande payée ne peut pas être annulée ici."
);

return;

}


if(
!confirm(
"Annuler cette commande ?"
)
){

return;

}


/* RESTITUTION DU STOCK */

order.items.forEach(item=>{

data.products[
item.productIndex
].stock
+=item.quantity;

});


data.orders=
data.orders.filter(
o=>o.id!==orderId
);


saveData();

}



/* =====================================================
   AFFICHAGE COMMANDES
===================================================== */

function renderOrders(){

const container=
document.getElementById(
"ordersList"
);


if(
data.orders.length===0
){

container.innerHTML=
"<div class='empty'>Aucune commande.</div>";

return;

}


container.innerHTML=
data.orders
.slice()
.reverse()
.slice(0,20)
.map(order=>{

const items=
order.items
.map(item=>
item.name+
" × "+
item.quantity
)
.join(" • ");


let badge="badge-new";


if(order.status==="Préparation")
badge="badge-prep";

if(order.status==="Servie")
badge="badge-served";

if(order.status==="Payée")
badge="badge-paid";


const next=
order.status!=="Payée"
?
`<button
class="btn btn-green"
onclick="nextStatus(${order.id})">
${order.status==="Nouvelle"
?"▶ Préparer"
:
order.status==="Préparation"
?"✓ Servir"
:
"💰 Marquer payée"}
</button>`
:
"";


return`

<div class="order-card">

<div class="order-header">

<div>

<div class="order-table">
TABLE ${order.table}
</div>

<div style="font-size:11px;color:#777">
${formatDate(order.date)}
</div>

</div>

<div class="order-total">
${money(order.total)}
</div>

</div>


<div class="order-items">
${items}
</div>


<div class="order-actions">

<span class="badge ${badge}">
${order.status}
</span>

${next}

${
order.status!=="Payée"
?
`<button
class="btn btn-red"
onclick="cancelOrder(${order.id})">
✕ Annuler
</button>`
:""
}

</div>

</div>

`;

})
.join("");

}



/* =====================================================
   CAISSE
===================================================== */

function openCash(){

if(data.cash.open){

alert(
"La caisse est déjà ouverte."
);

return;

}


const amount=
Number(
document.getElementById(
"openingCash"
).value
)||0;


if(amount<0){

alert(
"Montant invalide."
);

return;

}


data.cash={

open:true,

opening:amount,

openedAt:new Date().toISOString()

};


saveData();

alert(
"Caisse ouverte avec "+
money(amount)
);

}


function closeCash(){

if(!data.cash.open){

alert(
"La caisse est déjà fermée."
);

return;

}


const revenue=
getRevenue();


const expenses=
getExpenses();


const theoretical=
data.cash.opening+
revenue-
expenses;


if(
!confirm(
"Clôturer la caisse ?\n\n"+
"Solde théorique : "+
money(theoretical)
)
){

return;

}


data.cash={

open:false,

opening:0,

closedAt:new Date().toISOString()

};


saveData();

alert(
"Caisse clôturée."
);

}



/* =====================================================
   DEPENSES
===================================================== */

function addExpense(){

if(!data.cash.open){

alert(
"Vous devez ouvrir la caisse avant d'enregistrer une dépense."
);

return;

}


const name=
document
.getElementById("expenseName")
.value
.trim();


const amount=
Number(
document
.getElementById("expenseAmount")
.value
);


if(!name){

alert(
"Indiquez le motif de la dépense."
);

return;

}


if(!amount || amount<=0){

alert(
"Indiquez un montant valide."
);

return;

}


data.expenses.push({

id:Date.now(),

name:name,

amount:amount,

date:new Date().toISOString()

});


document
.getElementById("expenseName")
.value="";

document
.getElementById("expenseAmount")
.value="";


saveData();

alert(
"Dépense enregistrée."
);

}



/* =====================================================
   STOCK
===================================================== */

function updateStock(index,direction){

const product=
data.products[index];


const question=
direction>0
?
"Quantité à ajouter :"
:
"Quantité à sortir :";


const value=
Number(
prompt(question,"1")
);


if(!value || value<=0){

return;

}


if(
direction<0 &&
value>product.stock
){

alert(
"Stock insuffisant."
);

return;

}


product.stock
+=direction*value;


saveData();

}


function renderStock(){

const table=
document.getElementById(
"stockTable"
);


table.innerHTML="";


data.products.forEach(
(product,index)=>{

const low=
product.stock<=product.minimum;


const row=
document.createElement("tr");


row.innerHTML=`

<td>
<strong>${product.name}</strong>
</td>

<td>
${money(product.price)}
</td>

<td>
<strong>${product.stock}</strong>
</td>

<td>
${product.minimum}
</td>

<td>

${
low
?
"<span class='badge badge-cancel'>⚠️ FAIBLE</span>"
:
"<span class='badge badge-paid'>✓ OK</span>"
}

</td>

<td>

<button
class="btn btn-gold"
onclick="updateStock(${index},1)">
+ Entrée
</button>

<button
class="btn btn-dark"
onclick="updateStock(${index},-1)">
− Sortie
</button>

</td>

`;

table.appendChild(row);

});

}



/* =====================================================
   DASHBOARD
===================================================== */

function renderDashboard(){

const revenue=
getRevenue();

const expenses=
getExpenses();

const profit=
revenue-expenses;


const pending=
data.orders.filter(
order=>
order.status!=="Payée"
).length;


document
.getElementById("dashboardCA")
.textContent=
money(revenue);


document
.getElementById("dashboardOrders")
.textContent=
data.orders.length;


document
.getElementById("dashboardExpenses")
.textContent=
money(expenses);


document
.getElementById("dashboardProfit")
.textContent=
money(profit);


document
.getElementById("dashboardPending")
.textContent=
pending;


document
.getElementById("dashboardCash")
.textContent=
data.cash.open
?
"OUVERTE"
:
"FERMÉE";


/* ALERTES */

const low=
data.products.filter(
product=>
product.stock<=product.minimum
);


const alerts=
document.getElementById(
"alerts"
);


if(low.length===0){

alerts.innerHTML=
"<p class='success'>✓ Aucun produit en stock faible.</p>";

}
else{

alerts.innerHTML=
low.map(
product=>`

<div class="alert">

⚠️ <strong>
${product.name}
</strong>

<br>

Stock restant :
${product.stock}

</div>

`
).join("");

}

}



/* =====================================================
   CAISSE AFFICHAGE
===================================================== */

function renderCash(){

const revenue=
getRevenue();

const expenses=
getExpenses();


const balance=
data.cash.opening+
revenue-
expenses;


document
.getElementById("cashBalance")
.textContent=
money(balance);


document
.getElementById("cashOpening")
.textContent=
money(data.cash.opening);


document
.getElementById("cashMessage")
.innerHTML=
data.cash.open

?
"<span class='success'>● Caisse ouverte</span>"

:

"Caisse fermée";

}



/* =====================================================
   COMPTABILITE
===================================================== */

function renderAccounting(){

const income=
getRevenue();

const expense=
getExpenses();

const result=
income-expense;


document
.getElementById("accountingIncome")
.textContent=
money(income);


document
.getElementById("accountingExpense")
.textContent=
money(expense);


document
.getElementById("accountingResult")
.textContent=
money(result);

}



/* =====================================================
   RAFRAICHISSEMENT GENERAL
===================================================== */

function refresh(){

loadProducts();

renderCart();

renderOrders();

renderStock();

renderDashboard();

renderCash();

renderAccounting();

}



/* =====================================================
   DATE
===================================================== */

function formatDate(date){

return new Date(date)
.toLocaleString(
"fr-FR",
{
dateStyle:"short",
timeStyle:"short"
}
);

}


/* =====================================================
   HORLOGE
===================================================== */

function updateClock(){

document
.getElementById("clock")
.textContent=
new Date()
.toLocaleString(
"fr-FR",
{
dateStyle:"short",
timeStyle:"medium"
}
);

}


setInterval(
updateClock,
1000
);

updateClock();



/* =====================================================
   IMPRESSION
===================================================== */

function printPage(){

window.print();

}



/* =====================================================
   RAPPORT
===================================================== */

function generateReport(){

const revenue=
getRevenue();

const expenses=
getExpenses();

const profit=
revenue-expenses;


const report=
`
THE BOSS LOUNGE
RAPPORT DE GESTION
============================

Date :
${new Date().toLocaleString("fr-FR")}

RECETTES ENCAISSEES :
${money(revenue)}

DEPENSES :
${money(expenses)}

RESULTAT :
${money(profit)}

COMMANDES :
${data.orders.length}

COMMANDES PAYEES :
${data.orders.filter(
o=>o.status==="Payée"
).length}

============================
`;


const blob=
new Blob(
[report],
{
type:"text/plain;charset=utf-8"
}
);


const url=
URL.createObjectURL(blob);


const a=
document.createElement("a");

a.href=url;

a.download=
"Rapport_The_Boss_Lounge.txt";

a.click();

URL.revokeObjectURL(url);

}



/* =====================================================
   DEMARRAGE
===================================================== */

refresh();

</script>

</body>
</html>
