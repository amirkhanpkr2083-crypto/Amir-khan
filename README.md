# Amir-khan
Official website of Amir Pakur News
<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Amir Fashion Store</title>

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:Arial,sans-serif;
}
body{
  background:#fff8f0;
  color:#222;
}
header{
  background:linear-gradient(120deg,#ff416c,#ff8c42,#ffc107);
  color:white;
  padding:25px 15px;
  text-align:center;
}
header h1{font-size:30px;}
header p{margin-top:8px;}
nav{
  background:#5422a5;
  padding:14px;
  text-align:center;
  position:sticky;
  top:0;
  z-index:10;
}
nav a{
  color:white;
  text-decoration:none;
  margin:0 10px;
  font-weight:bold;
}
.hero{
  background:linear-gradient(120deg,#6a11cb,#ff416c);
  color:white;
  text-align:center;
  padding:55px 15px;
}
.hero h2{font-size:30px;margin-bottom:12px;}
.hero p{margin-bottom:20px;}
.hero button{
  background:#ffcf33;
  color:#222;
  border:0;
  padding:12px 25px;
  border-radius:25px;
  font-weight:bold;
  cursor:pointer;
}
.search{
  text-align:center;
  padding:22px 10px;
}
.search input{
  width:90%;
  max-width:450px;
  padding:13px;
  border:2px solid #ff416c;
  border-radius:25px;
  font-size:16px;
}
.categories{
  display:flex;
  justify-content:center;
  flex-wrap:wrap;
  gap:10px;
  padding:10px;
}
.categories button{
  border:0;
  padding:11px 18px;
  border-radius:20px;
  background:#6a11cb;
  color:white;
  cursor:pointer;
}
.categories button.active{
  background:#ff416c;
}
.section-title{
  text-align:center;
  padding:25px 10px;
  color:#6a11cb;
  font-size:25px;
}
.products{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(155px,1fr));
  gap:15px;
  padding:15px;
  max-width:1100px;
  margin:auto;
}
.product{
  background:white;
  border-radius:14px;
  overflow:hidden;
  box-shadow:0 3px 12px #0002;
  text-align:center;
  padding-bottom:15px;
}
.product img{
  width:100%;
  height:190px;
  object-fit:cover;
}
.product h3{
  font-size:16px;
  margin:10px 5px;
}
.price{
  color:#ff416c;
  font-size:19px;
  font-weight:bold;
  margin:8px;
}
.product button{
  background:#6a11cb;
  color:white;
  border:0;
  padding:10px 15px;
  border-radius:20px;
  cursor:pointer;
}
.cart{
  background:white;
  padding:20px;
  margin:25px auto;
  max-width:650px;
  width:94%;
  border-radius:15px;
  box-shadow:0 3px 12px #0002;
}
.cart h2{
  color:#6a11cb;
  margin-bottom:15px;
}
.cart-item{
  display:flex;
  justify-content:space-between;
  gap:10px;
  padding:10px 0;
  border-bottom:1px solid #ddd;
}
.cart-item button{
  padding:4px 9px;
  margin-left:4px;
  cursor:pointer;
}
.total{
  font-size:21px;
  font-weight:bold;
  color:#ff416c;
  margin:18px 0;
}
.order{
  width:100%;
  padding:14px;
  border:0;
  border-radius:25px;
  background:#13a84b;
  color:white;
  font-size:17px;
  font-weight:bold;
  cursor:pointer;
}
.about{
  background:#eee3ff;
  text-align:center;
  padding:35px 20px;
  line-height:1.8;
}
footer{
  background:#271044;
  color:white;
  text-align:center;
  padding:22px;
  line-height:2;
}
footer a{color:#ffcf33;}
@media(max-width:450px){
  nav a{margin:0 5px;font-size:13px;}
  header h1{font-size:25px;}
  .hero h2{font-size:25px;}
}
</style>
</head>

<body>

<header>
  <h1>👑 AMIR FASHION STORE</h1>
  <p>आपका अपना Fashion Shopping Store</p>
  <p>📍 Pakur, Jharkhand</p>
</header>

<nav>
  <a href="#home">Home</a>
  <a href="#shop">Shop</a>
  <a href="#cart">Cart</a>
  <a href="#about">About</a>
</nav>

<section class="hero" id="home">
  <h2>Welcome To Amir Fashion Store</h2>
  <p>नए Fashion, शानदार कपड़े और बेहतरीन कीमत!</p>
  <button onclick="document.getElementById('shop').scrollIntoView()">
    Shop Now 🛍️
  </button>
</section>

<div class="search">
  <input type="text" id="search"
  placeholder="🔍 कपड़े का नाम खोजें..."
  oninput="showProducts()">
</div>

<div class="categories">
  <button class="active" onclick="filterProducts('All',this)">All</button>
  <button onclick="filterProducts('Men',this)">Men</button>
  <button onclick="filterProducts('Women',this)">Women</button>
  <button onclick="filterProducts('Kids',this)">Kids</button>
</div>

<h2 class="section-title" id="shop">✨ Our Latest Collection ✨</h2>

<div class="products" id="products"></div>

<section class="cart" id="cart">
  <h2>🛒 Your Shopping Cart</h2>
  <div id="cartItems">अभी आपका Cart खाली है।</div>
  <div class="total">Total: ₹<span id="total">0</span></div>
  <button class="order" onclick="orderWhatsApp()">
    Order on WhatsApp
  </button>
</section>

<section class="about" id="about">
  <h2>About Amir Fashion Store</h2>
  <p>
    आपका स्वागत है Amir Fashion Store में।
    यहाँ आपको Men, Women और Kids के लिए
    शानदार Fashion Collection मिलेगा।
  </p>
  <h3>❤️ Thank You For Visiting ❤️</h3>
</section>

<footer>
  <h2>AMIR FASHION STORE</h2>
  <p>📍 Pakur, Jharkhand</p>
  <p>Fashion For Everyone</p>
  <p>© 2026 Amir Fashion Store</p>
</footer>

<script>
const products = [
 {
  name:"Men Stylish Shirt",
  price:499,
  category:"Men",
  image:"https://images.unsplash.com/photo-1603252110481-7ba873bf42ab?w=500"
 },
 {
  name:"Men Jeans",
  price:799,
  category:"Men",
  image:"https://images.unsplash.com/photo-1542272604-787c3835535d?w=500"
 },
 {
  name:"Men T-Shirt",
  price:349,
  category:"Men",
  image:"https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?w=500"
 },
 {
  name:"Women Dress",
  price:899,
  category:"Women",
  image:"https://images.unsplash.com/photo-1539008835657-9e8e9680c956?w=500"
 },
 {
  name:"Women Top",
  price:499,
  category:"Women",
  image:"https://images.unsplash.com/photo-1551163943-3f6a855d1153?w=500"
 },
 {
  name:"Women Fashion",
  price:999,
  category:"Women",
  image:"https://images.unsplash.com/photo-1483985988355-763728e1935b?w=500"
 },
 {
  name:"Kids Fashion Dress",
  price:399,
  category:"Kids",
  image:"https://images.unsplash.com/photo-1519238263530-99bdd11df2ea?w=500"
 },
 {
  name:"Kids T-Shirt",
  price:249,
  category:"Kids",
  image:"https://images.unsplash.com/photo-1503919005314-30d93d07d823?w=500"
 }
];

let selectedCategory="All";
let cart=[];

function showProducts(){
 const search=document.getElementById("search").value.toLowerCase();
 const container=document.getElementById("products");

 const filtered=products.filter(p=>
   (selectedCategory==="All" || p.category===selectedCategory) &&
   p.name.toLowerCase().includes(search)
 );

 container.innerHTML="";

 if(filtered.length===0){
   container.innerHTML="<p>कोई Product नहीं मिला।</p>";
   return;
 }

 filtered.forEach((p)=>{
   const index=products.indexOf(p);
   container.innerHTML+=`
    <div class="product">
      <img src="${p.image}" alt="${p.name}">
      <h3>${p.name}</h3>
      <div class="price">₹${p.price}</div>
      <button onclick="addToCart(${index})">
        Add To Cart +
      </button>
    </div>`;
 });
}

function filterProducts(category,btn){
 selectedCategory=category;
 document.querySelectorAll(".categories button")
 .forEach(b=>b.classList.remove("active"));
 btn.classList.add("active");
 showProducts();
}

function addToCart(index){
 const product=products[index];
 const existing=cart.find(item=>item.name===product.name);

 if(existing){
   existing.qty++;
 }else{
   cart.push({...product,qty:1});
 }

 updateCart();
}

function updateCart(){
 const container=document.getElementById("cartItems");
 let total=0;

 if(cart.length===0){
   container.innerHTML="अभी आपका Cart खाली है।";
 }else{
   container.innerHTML="";

   cart.forEach((item,index)=>{
     total+=item.price*item.qty;

     container.innerHTML+=`
      <div class="cart-item">
        <span>${item.name}<br>
        ₹${item.price} × ${item.qty}</span>
        <span>
          <button onclick="changeQty(${index},-1)">−</button>
          ${item.qty}
          <button onclick="changeQty(${index},1)">+</button>
        </span>
      </div>`;
   });
 }

 document.getElementById("total").innerText=total;
}

function changeQty(index,change){
 cart[index].qty+=change;

 if(cart[index].qty<=0){
   cart.splice(index,1);
 }

 updateCart();
}

function orderWhatsApp(){
 if(cart.length===0){
   alert("पहले Shopping Cart में Product जोड़ें!");
   return;
 }

 let message="Hello Amir Fashion Store! My Order:%0A";
 let total=0;

 cart.forEach(item=>{
   message+=`${item.name} x ${item.qty} = Rs. ${item.price*item.qty}%0A`;
   total+=item.price*item.qty;
 });

 message+=`Total Amount: Rs. ${total}`;

 // यहाँ अपना WhatsApp नंबर डालें
 const phone="919999999999";

 window.open(
  "https://wa.me/"+phone+"?text="+message,
  "_blank"
 );
}

showProducts();
</script>

</body>
</html>

