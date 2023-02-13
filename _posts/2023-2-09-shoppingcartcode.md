---
layout: post
description: 
categories: [markdown]
title: Dogs for Adoption Shopping Cart Code 
---

<html>
<head>
<style>

<div class="container">
		<!--  Shopping cart table wrapper  -->
		<div id="shopping-cart">
			<div class="txt-heading">
				<h1>Shopping cart</h1>
			</div>
			<a onClick="emptyCart()" id="btnEmpty">Empty Cart</a>
			<table class="tbl-cart" cellpadding="10" cellspacing="1">
				<thead>
					<tr>
						<th>Name</th>
						<th class='text-right' width="10%">Unit Price</th>
						<th class='text-right' width="5%">Quantity</th>
						<th class='text-right' width="10%">Sub Total</th>
					</tr>
				</thead>
				<!--  Cart table to load data on "add to cart" action -->
				<tbody id="cartTableBody">
				</tbody>
				<tfoot>
					<tr>
						<td class="text-right">Total:</td>
						<td id="itemCount" class="text-right" colspan="2"></td>
						<td id="totalAmount" class="text-right"></td>
					</tr>
				</tfoot>
			</table>
		</div>
		<!-- Product gallery shell to load HTML from JavaScript code -->
		<div id="product-grid">
			<div class="txt-heading">
				<h1>Products</h1>
			</div>
			<div id="product-item-container"></div>
</style>
</head>
<body>

<script>
  (document).ready(function() {
    var productItem = [{
        productName: "FinePix Pro2 3D Camera",
        price: "1800.00",
        photo: "camera.jpg"
      },
      {
        productName: "EXP Portable Hard Drive",
        price: "800.00",
        photo: "external-hard-drive.jpg"
      },
      {
        productName: "Luxury Ultra thin Wrist Watch",
        price: "500.00",
        photo: "laptop.jpg"
      },
      {
        productName: "XP 1155 Intel Core Laptop",
        price: "1000.00",
        photo: "watch.jpg"
      }];
    showProductGallery(productItem);
  });

  function showProductGallery(product) {
    //Iterate javascript shopping cart array
    var productHTML = "";
    product.forEach(function(item) {
      productHTML += '<div class="product-item">'+
            '<img src="product-images/' + item.photo + '">'+
            '<div class="productname">' + item.productName + '</div>'+
            '<div class="price">$<span>' + item.price + '</span></div>'+
            '<div class="cart-action">'+
              '<input type="text" class="product-quantity" name="quantity" value="1" size="2" />'+
              '<input type="submit" value="Add to Cart" class="add-to-cart" onClick="addToCart(this)" />'+
            '</div>'+
          '</div>';
          "<tr>";
      
    });
    ('#product-item-container').html(productHTML);
  }

  function addToCart(element) {
    var productParent = $(element).closest('div.product-item');

    var price = $(productParent).find('.price span').text();
    var productName = $(productParent).find('.productname').text();
    var quantity = $(productParent).find('.product-quantity').val();

    var cartItem = {
      productName: productName,
      price: price,
      quantity: quantity
    };
    var cartItemJSON = JSON.stringify(cartItem);

    var cartArray = new Array();
    // If javascript shopping cart session is not empty
    if (sessionStorage.getItem('shopping-cart')) {
      cartArray = JSON.parse(sessionStorage.getItem('shopping-cart'));
    }
    cartArray.push(cartItemJSON);

    var cartJSON = JSON.stringify(cartArray);
    sessionStorage.setItem('shopping-cart', cartJSON);
    showCartTable();

    function addToCart(element) {
	var productParent = $(element).closest('div.product-item');

	var price = $(productParent).find('.price span').text();
	var productName = $(productParent).find('.productname').text();
	var quantity = $(productParent).find('.product-quantity').val();

	var cartItem = {
		productName: productName,
		price: price,
		quantity: quantity
	};
	var cartItemJSON = JSON.stringify(cartItem);

	var cartArray = new Array();
	// If javascript shopping cart session is not empty
	if (sessionStorage.getItem('shopping-cart')) {
		cartArray = JSON.parse(sessionStorage.getItem('shopping-cart'));
	}
	cartArray.push(cartItemJSON);

	var cartJSON = JSON.stringify(cartArray);
	sessionStorage.setItem('shopping-cart', cartJSON);
	showCartTable();
}

function emptyCart() {
	if (sessionStorage.getItem('shopping-cart')) {
		// Clear JavaScript sessionStorage by index
		sessionStorage.removeItem('shopping-cart');
		showCartTable();
	}
}

function showCartTable() {
	var cartRowHTML = "";
	var itemCount = 0;
	var grandTotal = 0;

	var price = 0;
	var quantity = 0;
	var subTotal = 0;

	if (sessionStorage.getItem('shopping-cart')) {
		var shoppingCart = JSON.parse(sessionStorage.getItem('shopping-cart'));
		itemCount = shoppingCart.length;

		//Iterate javascript shopping cart array
		shoppingCart.forEach(function(item) {
			var cartItem = JSON.parse(item);
			price = parseFloat(cartItem.price);
			quantity = parseInt(cartItem.quantity);
			subTotal = price * quantity

			cartRowHTML += "<tr>" +
				"<td>" + cartItem.productName + "</td>" +
				"<td class='text-right'>$" + price.toFixed(2) + "</td>" +
				"<td class='text-right'>" + quantity + "</td>" +
				"<td class='text-right'>$" + subTotal.toFixed(2) + "</td>" +
				"</tr>";

			grandTotal += subTotal;
		});
	}

	('#cartTableBody').html(cartRowHTML);
	('#itemCount').text(itemCount);
	('#totalAmount').text("$" + grandTotal.toFixed(2));
</script>

