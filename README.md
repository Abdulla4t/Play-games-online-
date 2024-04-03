<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ECommerce-ShoppingCart | Korsat X Parmaga</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"> 


<style type="text/css">
    /* Google Fonts  */
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap');

    /* Globals  */
    * {
        font-family: 'Poppins', sans-serif;
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        list-style: none;
        text-decoration: none;
        scroll-behavior: smooth;
        scroll-padding: 2rem;
    }

    /* Variables  */
    :root {
        --main-color: #fd4646;
        --sec-color: #4946fd;
        --text-color: #171427;
        --bg-color: #fff;
    }

    ::selection {
        color: var(--text-color);
        background-color: var(--main-color);
    }

    .container {
        max-width: 1068px;
        margin: auto;
        width: 100%;
    }

    section {
        padding: 4rem 0 3rem;
    }

    body {
        color:#fff;
        background: #333;
    }

    img {
        width: 100%;
    }

    /* =======================================  */
    /* HEADER  */
    header {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        background-color: var(--bg-color);
        box-shadow: 0 1px 4px hsl(0 4% 15% / 10%);
        z-index: 100;
    }

    .nav {
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 20px 0;
    }

    .logo {
        font-size: 1.1rem;
        font-weight: 600;
        color: var(--sec-color);
        text-transform: uppercase;
    }

    .logo span {
        color: var(--main-color);
        font-weight: 700;
    }

    #cart-icon {
        font-size: 1.8rem;
        cursor: pointer;
    }

    /* CART  */
    .cart {
        position: fixed;
        top: 0;
        right: 0;
        right: -100%;
        width: 360px;
        height: 100vh;
        overflow-y: auto;
        overflow-x: hidden;
        padding: 20px;
        background-color: var(--bg-color);
        box-shadow: -2px solid 4px hsl(0 4% 15% / 10%);
        border: 1px solid var(--main-color);
        transition: 1.5s;
    }

    .cart.active {
        right: 0;
        transition: .5s;
    }

    .cart-title {
        text-align: center;
        font-size: 1.5rem;
        font-weight: 600;
        margin-top: 2rem;
    }

    .cart-box {
        display: grid;
        grid-template-columns: 32% 50% 18%;
        align-items: center;
        gap: 1rem;
        margin-top: 1rem;
    }

    .cart-img {
        width: 100px;
        height: 100px;
        object-fit: contain;
        padding: 10px;
    }

    .detail-box {
        display: grid;
        row-gap: .5rem;
    }

    .cart-product-title {
        font-size: 1rem;
        text-transform: uppercase;
    }

    .cart-price {
        font-weight: 500;
    }

    .cart-quantity {
        border: 1px solid var(--text-color);
        outline-color: var(--main-color);
        width: 2.4rem;
        text-align: center;
        font-size: 1rem;
    }

    .cart-remove {
        font-size: 24px;
        color: var(--main-color);
        cursor: pointer;
    }

    .total {
        display: flex;
        justify-content: flex-end;
        margin-top: 1.5rem;
        border-top: 1px solid var(--text-color);
    }

    .total-title {
        font-size: 1rem;
        font-weight: 600;
    }

    .total-price {
        margin-left: .5rem;
    }

    .btn-buy {
        display: flex;
        margin: 1.5rem auto 0 auto;
        padding: 12px 20px;
        border: none;
        background-color: var(--sec-color);
        color: var(--bg-color);
        font-size: 1rem;
        font-weight: 500;
        cursor: pointer;
    }

    .btn-buy:hover {
        background-color: var(--text-color);
    }

    #cart-close {
        position: absolute;
        top: 1rem;
        right: .8rem;
        font-size: 2rem;
        color: var(--text-color);
        cursor: pointer;
    }

    /* SHOP SECTION  */
    .shop {
        margin-top: 2rem;
    }

    .section-title {
        font-size: 1.5rem;
        font-weight: 600;
        text-align: center;
        margin-bottom: 1.5rem;
        font-size:40px
    }

    .shop-content {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(220px, auto));
        gap: 1.5rem;
    }

    .product-box {
        position: relative;
    }

    .product-box:hover {
        padding: 10px;
        border: 3px solid #fff;
        transition: .4s;
    }

    .product-img {
        width: 100%;
        aspect-ratio: 1/1;
        object-fit: cover;
        margin-bottom: .5rem;
    }

    .product-title {
        font-size: 1.1rem;
        font-weight: 600;
        text-transform: uppercase;
        margin-bottom: .5rem;
    }

    .product-price {
        font-weight: 500;
    }

    .add-cart {
        position: absolute;
        bottom: 0;
        right: 0;
        background-color: var(--text-color);
        color: var(--bg-color);
        padding: 10px;
        cursor: pointer;
    }

    .add-cart:hover {
        background-color: hsl(249, 32%, 17%);
    }

    /* ================ RESPONSIVE & BREAKPOINTS ============= */
    @media (max-width: 1080px) {
        .nav {
            padding: 15px;
        }

        .container {
            width: 90%;
        }

            section {
                padding: 3rem 0 2rem;
            }

            .shop {
                margin-top: 2rem;
            }
        }

        /* For Medium Devices */
        @media (max-width: 400px) {
            .nav {
                padding: 11px;
            }

            .logo {
                font-size: 1rem;
            }

            .cart {
                width: 320px;
            }
        }

        /* For Small Devices */
        @media (max-width: 360px) {
            .shop {
                margin-top: 1rem;
            }

            .cart {
                width: 280px;
            }
        }

a{
  background :#000;
  color:#fff;
  padding: 5px 10px;
  border: 2px solid #fff;
border-radius:10px 
}
a:hover{
  background :#fff;
color:#000;
padding: 5px 10px;
border: 2px solid #000;
border-radius:10px
}
header{
background :#36386d 
}
.nav container .e{
font-size:20px;
}
.nav container .e img {
boder-radiuse:10px 
}
    </style>
    
    <!-- styles  -->
    <link rel="stylesheet" href="assets/css/style.css">
</head>

<body>
    <!-- HEADER  -->
    <header>
        <!-- NAV  -->
        <div class="nav container">
            <a href="#" class="logo"><span>A</span>bdulla</a>
<a href="Play games online by Abdulla2.html" ><i class="fas fa-sun"></i></a>
            <!-- CART ICON  -->
            
        </div>
    </header>


    <!-- SHOP SECTION  -->
    <section class="shop container">
        <h2 class="section-title">play games online </h2>

        <!-- CONTENT  -->
        <div class="shop-content">
            <!-- BOX 1 -->
            <div class="product-box">
                         <img src="1.png" alt="" class="product-img">
                         
                <h2 class="product-title">X O Game</h2>
            <a href="https://j9r0iafvnpij7acukstlwa.on.drv.tw/Game%20/o%20x%20game.html">Play Now</a>
            </div>
            <!-- BOX 2 -->
            <div class="product-box">
                         <img src="2.png" alt="" class="product-img">
                         
                         <h2 class="product-title">Snake Game</h2>
                <a href="https://j9r0iafvnpij7acukstlwa.on.drv.tw/Game /sanke.html">Play Now</a>
            </div>
            <!-- BOX 3 -->
            <div class="product-box">
<img src="3.png" alt="" class="product-img">
      
                <h2 class="product-title">Shoter Game</h2>
                <a href="https://j9r0iafvnpij7acukstlwa.on.drv.tw/Game /text.html">Play Now</a>
            </div>
            <!-- BOX 4 -->
            <div class="product-box">
                <img src="4.png" alt="" class="product-img">
                
                <h2 class="product-title">2048 Game</h2>
                <a href="https://j9r0iafvnpij7acukstlwa.on.drv.tw/Game /text1.html">Play Now</a>
            </div>
            
            <!-- BOX 4 -->
            <div class="product-box">
            <img src="5.png" alt="" class="product-img">
            
            <h2 class="product-title">pipe Game</h2>
            <a href="https://j9r0iafvnpij7acukstlwa.on.drv.tw/Game /gggg.html">Play Now</a>
            </div>
            
        </div>
    </section>

    <!-- link js  -->
    <script src="assets/js/main.js">
      // OPEN & CLOSE CART
const cartIcon = document.querySelector("#cart-icon");
const cart = document.querySelector(".cart");
const closeCart = document.querySelector("#cart-close");

cartIcon.addEventListener("click", () => {
  cart.classList.add("active");
});

closeCart.addEventListener("click", () => {
  cart.classList.remove("active");
});

// Start when the document is ready
if (document.readyState == "loading") {
  document.addEventListener("DOMContentLoaded", start);
} else {
  start();
}

// =============== START ====================
function start() {
  addEvents();
}

// ============= UPDATE & RERENDER ===========
function update() {
  addEvents();
  updateTotal();
}

// =============== ADD EVENTS ===============
function addEvents() {
  // Remove items from cart
  let cartRemove_btns = document.querySelectorAll(".cart-remove");
  console.log(cartRemove_btns);
  cartRemove_btns.forEach((btn) => {
    btn.addEventListener("click", handle_removeCartItem);
  });

  // Change item quantity
  let cartQuantity_inputs = document.querySelectorAll(".cart-quantity");
  cartQuantity_inputs.forEach((input) => {
    input.addEventListener("change", handle_changeItemQuantity);
  });

  // Add item to cart
  let addCart_btns = document.querySelectorAll(".add-cart");
  addCart_btns.forEach((btn) => {
    btn.addEventListener("click", handle_addCartItem);
  });

  // Buy Order
  const buy_btn = document.querySelector(".btn-buy");
  buy_btn.addEventListener("click", handle_buyOrder);
}

// ============= HANDLE EVENTS FUNCTIONS =============
let itemsAdded = [];

function handle_addCartItem() {
  let product = this.parentElement;
  let title = product.querySelector(".product-title").innerHTML;
  let price = product.querySelector(".product-price").innerHTML;
  let imgSrc = product.querySelector(".product-img").src;
  console.log(title, price, imgSrc);

  let newToAdd = {
    title,
    price,
    imgSrc,
  };

  // handle item is already exist
  if (itemsAdded.find((el) => el.title == newToAdd.title)) {
    alert("This Item Is Already Exist!");
    return;
  } else {
    itemsAdded.push(newToAdd);
  }

  // Add product to cart
  let cartBoxElement = CartBoxComponent(title, price, imgSrc);
  let newNode = document.createElement("div");
  newNode.innerHTML = cartBoxElement;
  const cartContent = cart.querySelector(".cart-content");
  cartContent.appendChild(newNode);

  update();
}

function handle_removeCartItem() {
  this.parentElement.remove();
  itemsAdded = itemsAdded.filter(
    (el) =>
      el.title !=
      this.parentElement.querySelector(".cart-product-title").innerHTML
  );

  update();
}

function handle_changeItemQuantity() {
  if (isNaN(this.value) || this.value < 1) {
    this.value = 1;
  }
  this.value = Math.floor(this.value); // to keep it integer

  update();
}

function handle_buyOrder() {
  if (itemsAdded.length <= 0) {
    alert("There is No Order to Place Yet! \nPlease Make an Order first.");
    return;
  }
  const cartContent = cart.querySelector(".cart-content");
  cartContent.innerHTML = "";
  alert("Your Order is Placed Successfully :)");
  itemsAdded = [];

  update();
}

// =========== UPDATE & RERENDER FUNCTIONS =========
function updateTotal() {
  let cartBoxes = document.querySelectorAll(".cart-box");
  const totalElement = cart.querySelector(".total-price");
  let total = 0;
  cartBoxes.forEach((cartBox) => {
    let priceElement = cartBox.querySelector(".cart-price");
    let price = parseFloat(priceElement.innerHTML.replace("$", ""));
    let quantity = cartBox.querySelector(".cart-quantity").value;
    total += price * quantity;
  });

  // keep 2 digits after the decimal point
  total = total.toFixed(2);
  // or you can use also
  // total = Math.round(total * 100) / 100;

  totalElement.innerHTML = "$" + total;
}

// ============= HTML COMPONENTS =============
function CartBoxComponent(title, price, imgSrc) {
  return `
  </script >
  
    </body>
    </html >
