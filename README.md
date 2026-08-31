   <!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>THE BOSS LOUNGE - Management</title>

<style>
*{box-sizing:border-box}

body{
    margin:0;
    font-family:Arial, sans-serif;
    background:#0b0b0b;
    color:white;
}

header{
    background:#111;
    border-bottom:1px solid #333;
    padding:18px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    position:sticky;
    top:0;
    z-index:10;
}

.logo{
    color:#d4af37;
    font-size:20px;
    font-weight:bold;
    letter-spacing:2px;
}

#clock{
    font-size:13px;
    color:#bbb;
}

.layout{
    display:flex;
    min-height:calc(100vh - 70px);
}

nav{
    width:230px;
    background:#111;
    padding:12px;
    border-right:1px solid #292929;
}

nav button{
    width:100%;
    padding:13px;
    margin:4px 0;
    border:0;
    border-radius:8px;
    background:transparent;
    color:white;
    text-align:left;
    cursor:pointer;
}

nav button:hover,
nav button.active{
    background:#292929;
    color:#d4af37;
}

main{
    flex:1;
    padding:20px;
}

.section{
    display:none;
}

.section.active{
    display:block;
}

h2{
    color:#d4af37;
}

.cards{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
    gap:15px;
}

.card,
.panel{
    background:#171717;
    border:1px solid #303030;
    border-radius:12px;
    padding:18px;
}

.card small{
    color:#aaa;
}

.value{
    font-size:24px;
    font-weight:bold;
    margin-top:8px;
}

.grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
    gap:15px;
    margin-top:15px;
}

input,
select{
    width:100%;
    padding:12px;
    margin:7px 0 14px;
    background:#0d0d0d;
    border:1px solid #444;
    border-radius:7px;
    color:white;
}

button{
    padding:11px 15px;
    border:0;
    border-radius:8px;
    cursor:pointer;
}

.gold{
    background:#d4af37;
    color:#111;
    font-weight:bold;
}

.dark{
    background:#292929;
    color:white;
}

.danger{
    background:#b83232;
    color:white;
}

.total{
    color:#d4af37;
    font-size:24px;
    font-weight:bold;
}

table{
    width:100%;
    border-collapse:collapse;
}

th,
td{
    padding:11px;
    border-bottom:1px solid #333;
    text-align:left;
}

th{
    color:#d4af37;
}

.badge{
    display:inline-block;
    padding:5px 8px;
    border-radius:20px;
    background:#333;
    font-size:12px;
}

.alert{
    color:#ff7777;
}

.success{
    color:#50d890;
}

.actions{
    display:flex;
    gap:8px;
    flex-wrap:wrap;
}

@media(max-width:700px){

    .layout{
        display:block;
    }

    nav{
        position:fixed;
        bottom:0;
        left:0;
        right:0;
        width:100%;
        height:68px;
        display:flex;
        overflow-x:auto;
        z-index:20;
        border-top:1px solid #333;
    }

    nav button{
        min-width:110px;
        text-align:center;
        font-size:11px;
    }

    main{
        padding-bottom:90px;
    }

    .logo{
        font-size:15px;
    }
}
</style>
</head>

<body>

<header>

<div class="logo">
THE BOSS LOUNGE
</div>

<div id="clock"></div>

</header>


<div class="layout">


<nav>

<button class="active" onclick="showSection('dashboard',this)">
📊 Tableau de bord
</button>

<button onclick="showSection('orders',this)">
🧾 Commandes
</button>

<button onclick="showSection('cash',this)">
💰 Caisse
</button>

<button onclick="showSection('stock',this)">
📦 Stock
</button>

<button onclick="showSection('staff',this)">
👥 Personnel
</button>

<button onclick="showSection('accounting',this)">
📚 Comptabilité
</button>

<button onclick="showSection('bank',this)">
🏦 Banque
</button>

<button onclick="showSection('documents',this)">
🧾 Documents
</button>

<button onclick="showSection('users',this)">
🔐 Utilisateurs
</button>

</nav>


<main>


<!-- TABLEAU DE BORD -->

<section id="dashboard" class="section active">

<h2>📊 Tableau de bord</h2>

<div class="cards">

<div class="card">
<small>Chiffre d'affaires</small>
<div class="value" id="dashboardCA">0 GNF</div>
</div>

<div class="card">
<small>Ventes</small>
<div class="value" id="dashboardSales">0</div>
</div>

<div class="card">
<small>Dépenses</small>
<div class="value" id="dashboardExpenses">0 GNF</div>
</div>

<div class="card">
<small>Bénéfice</small>
<div class="value" id="dashboardProfit">0 GNF</div>
</div>

<div class="card">
<small>Commandes</small>
<div class="value" id="dashboardOrders">0</div>
</div>

<div class="card">
<small>Caisse</small>
<div class="value" id="dashboardCash">FERMÉE</div>
</div>

</div>


<div class="grid">

<div class="panel">

<h3>🔔 Alertes</h3>

<div id="alerts">
Aucune alerte.
</div>

</div>


<div class="panel">

<h3>⚡ Actions rapides</h3>

<div class="actions">

<button class="gold"
onclick="showSection('orders')">
Nouvelle commande
</button>

<button class="dark"
onclick="showSection('cash')">
Caisse
</button>

<button class="dark"
onclick="showSection('stock')">
Stock
</button>

</div>

</div>

</div>

</section>



<!-- COMMANDES -->

<section id="orders" class="section">

<h2>🧾 Commandes</h2>

<div class="grid">


<div class="panel">

<h3>Nouvelle commande</h3>

<label>
Numéro de table *
</label>

<input
id="tableNumber"
placeholder="Exemple : Table 12"
>


<label>
Produit
</label>

<select id="productSelect"></select>


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
class="gold"
onclick="addToCart()">

Ajouter

</button>


<h3>
Total :
<span class="total" id="orderTotal">
0 GNF
</span>
</h3>


<div id="cart"></div>


<button
class="gold"
onclick="saveOrder()">

Enregistrer + WhatsApp

</button>

</div>


<div class="panel">

<h3>Commandes récentes</h3>

<div id="ordersList">
Aucune commande.
</div>

</div>

</div>

</section>



<!-- CAISSE -->

<section id="cash" class="section">

<h2>💰 Caisse</h2>


<div class="grid">


<div class="panel">

<h3>Ouverture / fermeture</h3>

<label>
Fond de caisse
</label>

<input
id="openingCash"
type="number"
placeholder="GNF"
>

<div class="actions">

<button
class="gold"
onclick="openCash()">

Ouvrir

</button>

<button
class="danger"
onclick="closeCash()">

Clôturer

</button>

</div>

<p id="cashMessage">
Caisse fermée
</p>

</div>


<div class="panel">

<h3>💸 Nouvelle dépense</h3>

<label>
Motif
</label>

<input
id="expenseName"
placeholder="Exemple : charbon"
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
class="gold"
onclick="addExpense()">

Enregistrer la dépense

</button>

</div>

</div>

</section>



<!-- STOCK -->

<section id="stock" class="section">

<h2>📦 Gestion du stock</h2>

<div class="panel">

<table>

<thead>

<tr>

<th>Produit</th>
<th>Stock</th>
<th>Seuil</th>
<th>Actions</th>

</tr>

</thead>

<tbody id="stockTable"></tbody>

</table>

</div>

</section>



<!-- PERSONNEL -->

<section id="staff" class="section">

<h2>👥 Personnel & Paie</h2>

<div class="panel">

<table>

<thead>

<tr>
<th>Nom</th>
<th>Fonction</th>
<th>Présence</th>
<th>Salaire</th>
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

</tr>

</tbody>

</table>

</div>

</section>



<!-- COMPTABILITE -->

<section id="accounting" class="section">

<h2>📚 Comptabilité</h2>

<div class="cards">

<div class="card">

<small>Recettes</small>

<div
class="value"
id="accountingIncome">
0 GNF
</div>

</div>


<div class="card">

<small>Dépenses</small>

<div
class="value"
id="accountingExpense">
0 GNF
</div>

</div>


<div class="card">

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

<h2>🏦 Banque</h2>

<div class="panel">

<h3>Opérations bancaires</h3>

<p>
Gestion des comptes, dépôts, retraits,
transferts et soldes.
</p>

<button
class="gold"
onclick="alert('Module bancaire à compléter.')">

Nouvelle opération

</button>

</div>

</section>



<!-- DOCUMENTS -->

<section id="documents" class="section">

<h2>🧾 Documents</h2>

<div class="panel">

<h3>Documents</h3>

<p>
Factures • Reçus • Rapports • Bulletins de salaire
</p>

<button
class="gold"
onclick="window.print()">

🖨️ Imprimer

</button>

</div>

</section>



<!-- UTILISATEURS -->

<section id="users" class="section">

<h2>🔐 Utilisateurs & droits</h2>

<div class="panel">

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
<td>Dashboard / Caisse / Stock / Rapports</td>
</tr>

<tr>
<td>Caissière</td>
<td>Caisse</td>
<td>Commandes / Caisse</td>
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
<td>Comptabilité / Banque / Documents</td>
</tr>

</tbody>

</table>

</div>

</section>


</main>

</div>



<script>

/* =========================
   DONNÉES
========================= */

const STORAGE_KEY = "THE_BOSS_LOUNGE_V1";


let data = JSON.parse(
localStorage.getItem(STORAGE_KEY)
) || {

products: [

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


let cart=[];



/* =========================
   OUTILS
========================= */

function money(number){

return Number(number || 0)
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



/* =========================
   NAVIGATION
========================= */

function showSection(id,button){

document
.querySelectorAll(".section")
.forEach(section=>{
section.classList.remove("active");
});

document
.getElementById(id)
.classList.add("active");


document
.querySelectorAll("nav button")
.forEach(btn=>{
btn.classList.remove("active");
});


if(button){
button.classList.add("active");
}

}



/* =========================
   PRODUITS
========================= */

function loadProducts(){

const select=
document.getElementById("productSelect");

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



/* =========================
   PANIER
========================= */

function addToCart(){

const index=
Number(
document.getElementById("productSelect").value
);

const quantity=
Math.max(
1,
Number(
document.getElementById("quantity").value
)
);


const product=
data.products[index];


if(product.stock < quantity){

alert(
"Stock insuffisant pour "+product.name
);

return;

}


cart.push({

name:product.name,

price:product.price,

quantity:quantity,

total:product.price*quantity,

productIndex:index

});


renderCart();

}


function renderCart(){

const container=
document.getElementById("cart");

container.innerHTML="";


cart.forEach(
(item,index)=>{

const line=
document.createElement("p");

line.innerHTML=
item.name+
" × "+
item.quantity+
" — "+
money(item.total)+
" <button class='dark' onclick='removeCart("+index+")'>✕</button>";

container.appendChild(line);

});


const total=
cart.reduce(
(sum,item)=>sum+item.total,
0
);

document
.getElementById("orderTotal")
.textContent=money(total);

}


function removeCart(index){

cart.splice(index,1);

renderCart();

}



/* =========================
   ENREGISTRER COMMANDE
========================= */

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


for(const item of cart){

if(
data.products[item.productIndex].stock
<
item.quantity
){

alert(
"Stock insuffisant pour "+
item.name
);

return;

}

}


/* RETRAIT STOCK */

cart.forEach(item=>{

data.products[item.productIndex].stock
-=item.quantity;

});


const total=
cart.reduce(
(sum,item)=>sum+item.total,
0
);


const order={

id:Date.now(),

table:table,

items:[...cart],

total:total,

status:"Nouvelle",

paid:false,

date:new Date().toISOString()

};


data.orders.push(order);


/* WHATSAPP */

let message=
"THE BOSS LOUNGE\n"+
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
"\nTOTAL : "+
money(total);


const whatsappURL=
"https://wa.me/224628323057?text="+
encodeURIComponent(message);


window.open(
whatsappURL,
"_blank"
);


cart=[];

document
.getElementById("tableNumber")
.value="";


saveData();

}



/* =========================
   CAISSE
========================= */

function openCash(){

const amount=
Number(
document.getElementById("openingCash").value
)||0;


data.cash={

open:true,

opening:amount

};


saveData();

alert(
"Caisse ouverte avec "+
money(amount)
);

}


function closeCash(){

if(!data.cash.open){

alert("La caisse est déjà fermée.");

return;

}


data.cash={

open:false,

opening:0

};


saveData();

alert("Caisse clôturée.");

}



/* =========================
   DEPENSES
========================= */

function addExpense(){

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


if(!name || !amount){

alert(
"Veuillez remplir les informations."
);

return;

}


data.expenses.push({

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

}



/* =========================
   STOCK
========================= */

function updateStock(index,direction){

const quantity=
Number(
prompt(
direction>0
?"Quantité à ajouter :"
:"Quantité à sortir :",
"1"
)
);


if(!quantity || quantity<=0){

return;

}


data.products[index].stock
+=direction*quantity;


if(data.products[index].stock<0){

data.products[index].stock=0;

}


saveData();

}



/* =========================
   ACTUALISATION
========================= */

function refresh(){

loadProducts();


/* CA */

const revenue=
data.orders
.filter(order=>order.paid)
.reduce(
(sum,order)=>sum+order.total,
0
);


/* Pour la V1,
   les commandes peuvent être
   considérées comme ventes
*/

const allSales=
data.orders
.reduce(
(sum,order)=>sum+order.total,
0
);


const expenses=
data.expenses
.reduce(
(sum,item)=>sum+item.amount,
0
);


const profit=
allSales-expenses;


/* DASHBOARD */

document
.getElementById("dashboardCA")
.textContent=money(allSales);


document
.getElementById("dashboardSales")
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
.getElementById("dashboardOrders")
.textContent=
data.orders.length;


document
.getElementById("dashboardCash")
.textContent=
data.cash.open
?"OUVERTE"
:"FERMÉE";


/* COMPTABILITÉ */

document
.getElementById("accountingIncome")
.textContent=
money(allSales);


document
.getElementById("accountingExpense")
.textContent=
money(expenses);


document
.getElementById("accountingResult")
.textContent=
money(profit);


/* STOCK */

const stockTable=
document.getElementById("stockTable");

stockTable.innerHTML="";


data.products.forEach(
(product,index)=>{

const row=
document.createElement("tr");

const status=
product.stock<=product.minimum
?"<span class='alert'>⚠️ FAIBLE</span>"
:"<span class='success'>OK</span>";


row.innerHTML=`

<td>${product.name}</td>

<td>
${product.stock}
</td>

<td>
${product.minimum}
</td>

<td>

${status}

<br><br>

<button
class="gold"
onclick="updateStock(${index},1)">
+ Entrée
</button>

<button
class="dark"
onclick="updateStock(${index},-1)">
− Sortie
</button>

</td>

`;

stockTable.appendChild(row);

});


/* ALERTES */

const alerts=
data.products.filter(
p=>p.stock<=p.minimum
);


document
.getElementById("alerts")
.innerHTML=
alerts.length

?
alerts.map(
p=>`
<p class="alert">
⚠️ ${p.name} :
${p.stock} restant(s)
</p>
`
).join("")

:
"<p class='success'>Aucune alerte.</p>";


/* COMMANDES */

const ordersList=
document.getElementById("ordersList");


if(data.orders.length===0){

ordersList.innerHTML=
"Aucune commande.";

}else{

ordersList.innerHTML=
data.orders
.slice()
.reverse()
.slice(0,10)
.map(order=>`

<p>

<b>
Table ${order.table}
</b>

—

${money(order.total)}

<br>

<span class="badge">
${order.status}
</span>

</p>

`)
.join("");

}


/* CAISSE */

document
.getElementById("cashMessage")
.textContent=
data.cash.open

?
"Caisse ouverte — Fond : "+
money(data.cash.opening)

:
"Caisse fermée";

}



/* =========================
   HORLOGE
========================= */

function updateClock(){

document
.getElementById("clock")
.textContent=
new Date()
.toLocaleString("fr-FR");

}


setInterval(
updateClock,
1000
);


updateClock();

refresh();

</script>

</body>
</html>
