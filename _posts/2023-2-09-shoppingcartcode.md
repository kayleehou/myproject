---
layout: post
description: 
categories: [markdown]
title: Dogs for Adoption Shopping Cart Code 
---
<html>
    <head>
        </header>
        <section class="container content-section">
            <div class="shop-dogs">
                <div class="shop-dog">
                    <span class="dog-name">Album 1</span>
                    <img class="dog-pic" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTUaFH2Bv2Ic7HloYmvMV-gPG2w-7hytvP2EXz3YVww&s">
                    <div class="shop-dog-details">
                        <span class="shop-dog-price">$12.99</span>
                        <button class="cart-button" type="button">ADD TO CART</button>
                    </div>
                </div>
                <div class="shop-dog">
                    <span class="dog-name">Album 2</span>
                    <img class="dog-pic" src="Images/Album 2.png">
                    <div class="shop-dog-details">
                        <span class="shop-dog-price">$14.99</span>
                        <button class="cart-button"type="button">ADD TO CART</button>
                    </div>
                </div>
                <div class="shop-dog">
                    <span class="dog-name">Album 3</span>
                    <img class="dog-pic" src="Images/Album 3.png">
                    <div class="shop-dog-details">
                        <span class="shop-dog-price">$9.99</span>
                        <button class="cart-button" type="button">ADD TO CART</button>
                    </div>
                </div>
                <div class="shop-dog">
                    <span class="dog-name">Album 4</span>
                    <img class="dog-pic" src="Images/Album 4.png">
                    <div class="shop-dog-details">
                        <span class="shop-dog-price">$19.99</span>
                        <button class="cart-button" type="button">ADD TO CART</button>
                    </div>
                </div>
            </div>
        </section>
        <section class="container content-section">
            <div class="shop-dogs">
                <div class="shop-dog">
                    <span class="dog-name">T-Shirt</span>
                    <img class="dog-pic" src="Images/Shirt.png">
                    <div class="shop-dog-details">
                        <span class="shop-dog-price">$19.99</span>
                        <button class="cart-button" type="button">ADD TO CART</button>
                    </div>
                </div>
                <div class="shop-dog">
                    <span class="dog-name">Coffee Cup</span>
                    <img class="dog-pic" src="Images/Cofee.png">
                    <div class="shop-dog-details">
                        <span class="shop-dog-price">$6.99</span>
                        <button class="cart-button" type="button">ADD TO CART</button>
                    </div>
                </div>
            </div>
        </section>
        <section class="container content-section">
            <h2 class="section-header">CART</h2>
            <div class="cart-row">
                <span class="cart-dog cart-header cart-column">dog</span>
                <span class="cart-price cart-header cart-column">PRICE</span>
                <span class="cart-quantity cart-header cart-column">QUANTITY</span>
            </div>
            <div class="cart-dogs">
            </div>
            <div class="cart-total">
                <strong class="cart-total-title">Total</strong>
                <span class="cart-total-price">$0</span>
            </div>
            <button class="purchase-button" type="button">PURCHASE</button>
    </body>
</html>
<script>
if (document.readyState == 'loading') {
    document.addEventListener('DOMContentLoaded', ready)
} else {
    ready()
}
function ready() {
    var removeCartdogButtons = document.getElementsByClassName('btn-danger')
    for (var i = 0; i < removeCartdogButtons.length; i++) {
        var button = removeCartdogButtons[i]
        button.addEventListener('click', removeCartdog)
    }
	var quantityInputs = document.getElementsByClassName('cart-quantity-input')
    for (var i = 0; i < quantityInputs.length; i++) {
        var input = quantityInputs[i]
        input.addEventListener('change', quantityChanged)
    }
    var addToCartButtons = document.getElementsByClassName('shop-dog-button')
    for (var i = 0; i < addToCartButtons.length; i++) {
        var button = addToCartButtons[i]
        button.addEventListener('click', addToCartClicked)
    }
    document.getElementsByClassName('btn-purchase')[0].addEventListener('click', purchaseClicked)
}
function purchaseClicked() {
    alert('Thank you for your purchase')
    var cartdogs = document.getElementsByClassName('cart-dogs')[0]
    while (cartdogs.hasChildNodes()) {
        cartdogs.removeChild(cartdogs.firstChild)
    }
    updateCartTotal()
}
function removeCartdog(event) {
    var buttonClicked = event.target
    buttonClicked.parentElement.parentElement.remove()
    updateCartTotal()
}
function quantityChanged(event) {
    var input = event.target
    if (isNaN(input.value) || input.value <= 0) {
        input.value = 1
    }
    updateCartTotal()
}
function addToCartClicked(event) {
    var button = event.target
    var shopdog = button.parentElement.parentElement
    var title = shopdog.getElementsByClassName('dog-name')[0].innerText
    var price = shopdog.getElementsByClassName('shop-dog-price')[0].innerText
    var imageSrc = shopdog.getElementsByClassName('dog-pic')[0].src
    adddogToCart(title, price, imageSrc)
    updateCartTotal()
}
function adddogToCart(title, price, imageSrc) {
    var cartRow = document.createElement('div')
    cartRow.classList.add('cart-row')
    var cartdogs = document.getElementsByClassName('cart-dogs')[0]
    var cartdogNames = cartdogs.getElementsByClassName('cart-dog-title')
    for (var i = 0; i < cartdogNames.length; i++) {
        if (cartdogNames[i].innerText == title) {
            alert('This dog is already added to the cart')
            return
        }
    }
    var cartRowContents = `
        <div class="cart-dog cart-column">
            <img class="cart-dog-image" src="${imageSrc}" width="100" height="100">
            <span class="cart-dog-title">${title}</span>
        </div>
        <span class="cart-price cart-column">${price}</span>
        <div class="cart-quantity cart-column">
            <input class="cart-quantity-input" type="number" value="1">
            <button class="btn btn-danger" type="button">REMOVE</button>
        </div>`
    cartRow.innerHTML = cartRowContents
    cartdogs.append(cartRow)
    cartRow.getElementsByClassName('btn-danger')[0].addEventListener('click', removeCartdog)
    cartRow.getElementsByClassName('cart-quantity-input')[0].addEventListener('change', quantityChanged)
}
function updateCartTotal() {
    var cartdogContainer = document.getElementsByClassName('cart-dogs')[0]
    var cartRows = cartdogContainer.getElementsByClassName('cart-row')
    var total = 0
    for (var i = 0; i < cartRows.length; i++) {
        var cartRow = cartRows[i]
        var priceElement = cartRow.getElementsByClassName('cart-price')[0]
        var quantityElement = cartRow.getElementsByClassName('cart-quantity-input')[0]
        var price = parseFloat(priceElement.innerText.replace('$', ''))
        var quantity = quantityElement.value
        total = total + (price * quantity)
    }
    total = Math.round(total * 100) / 100
    document.getElementsByClassName('cart-total-price')[0].innerText = '$' + total
}
</script>

</body>
</html>
