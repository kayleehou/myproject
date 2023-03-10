---
layout: post
description: These homeless dogs need you!
categories: [markdown]
title: Dogs for Adoption
---

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
* {
  box-sizing: border-box;
}

.row {
  display: flex;
}

.column {
  flex: 33.33%;
  padding: 5px;
}
h1 {
  text-align: center;
}
h3 {
  text-align: center;
}
</style>
</head>
<body>


<html>
<head>
<style>
.card {
  color: #000000;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  max-width: 300px;
  margin: auto;
  text-align: center;
  font-family: arial;
}

.price {
  color: grey;
  font-size: 22px;
}

.card button {
  border: none;
  outline: 0;
  padding: 12px;
  color: white;
  background-color: #000000;
  text-align: center;
  cursor: pointer;
  width: 80%;
  font-size: 18px;
}

.card button:hover {
  opacity: 0.7;
}
</style>
</head>
<body>

<div class="row">
  <div class="card">
    <img id="img1" src="https://dl5zpyw5k3jeb.cloudfront.net/photos/pets/59442857/1/?bust=1674344452" alt="joe" width="200" height="250">
    <h1>Joe</h1>
    <p class="price">$200</p>
    <p> Labrador Retriever Blend </p>
    <p><button>Learn More</button></p>
  </div>
  <div class="card">
    <img id="img2" src="https://www.dogbreedinfo.com/images31/ShepweilerGermanShepherdRottweilerMixedBreedDogMarshall2HalfYearsOld1.jpg" alt="bean" width="200" height="250">
    <h1>Bean</h1>
    <p class="price">$180</p>
    <p>Shepherd-Rottweiler Blend</p>
    <p><button>Learn More</button></p>
  </div>
  <div class="card">
  <img id="img3" src="https://dl5zpyw5k3jeb.cloudfront.net/photos/pets/55604262/2/?bust=1652662246&width=720" alt="harry" width="200" height="250">
  <h1>Harry</h1>
  <p class="price">$160</p>
  <p>Hound-Terrier Blend</p>
  <p><button>Learn More</button></p>
</div>

<canvas id="canvas" style="display:none"></canvas>

<script>
  const img1 = document.querySelector('#img1');
  const img2 = document.querySelector('#img2');
  const img3 = document.querySelector('#img3');
  const canvas = document.querySelector('#canvas');
  const ctx = canvas.getContext('2d');

  function grayscale(img) {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    canvas.width = img.width;
    canvas.height = img.height;
    ctx.drawImage(img, 0, 0);
    const imageData = ctx.getImageData(0, 0, canvas.width, canvas.height);
    const pixels = imageData.data;
    
    for (let i = 0; i < pixels.length; i += 4) {
    const grayscaleValue = 0.2126 * pixels[i] + 0.7152 * pixels[i + 1] + 0.0722 * pixels[i + 2];
    pixels[i] = grayscaleValue;
    pixels[i + 1] = grayscaleValue;
    pixels[i + 2] = grayscaleValue;
    }
    ctx.putImageData(imageData, 0, 0);
    img.src = canvas.toDataURL();
  }