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

<a href="https://haeryny.github.io/teamteam/availabledogs/"><img src="https://cdn-icons-png.flaticon.com/512/70/70021.png" alt="shopping cart" style="width:42px;height:42px;"></a>

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
    <img src="https://dl5zpyw5k3jeb.cloudfront.net/photos/pets/59442857/1/?bust=1674344452" alt="Denim Jeans" width="200" height="250">
    <h1>Joe</h1>
    <p class="price">$200</p>
    <p> Labrador Retriever Blend </p>
    <p><button>Learn More</button></p>
  </div>
  <div class="card">
    <img src="https://www.dogbreedinfo.com/images31/ShepweilerGermanShepherdRottweilerMixedBreedDogMarshall2HalfYearsOld1.jpg" alt="Denim Jeans" width="200" height="250">
    <h1>Bean</h1>
    <p class="price">$180</p>
    <p>Shepherd-Rottweiler Blend</p>
    <p><button>Learn More</button></p>
  </div>
  <div class="card">
  <img src="https://dl5zpyw5k3jeb.cloudfront.net/photos/pets/55604262/2/?bust=1652662246&width=720" alt="Denim Jeans" width="200" height="250">
  <h1>Harry</h1>
  <p class="price">$160</p>
  <p>Hound-Terrier Blend</p>
  <p><button>Learn More</button></p>
</div>

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
  <img src="https://goldenbondrescue.com/wp-content/uploads/2022/11/Cody-3791.jpg" alt="Denim Jeans" width="200" height="250">
  <h1>Honey</h1>
  <p class="price">$200</p>
  <p>Retriever Blend</p>
  <p><button>Learn More</button></p>
</div>
  <div class="card">
    <img src="https://dl5zpyw5k3jeb.cloudfront.net/photos/pets/48740896/1/?bust=1626106588" alt="Denim Jeans" width="200" height="250">
    <h1>George</h1>
    <p class="price">$250</p>
    <p>Retriever Blend</p>
    <p><button>Learn More</button></p>
  </div>
  <div class="card">
  <img src="https://i.pinimg.com/originals/6c/a6/30/6ca630545577914ec9394e8742b4539a.jpg" alt="Denim Jeans" width="200" height="250">
  <h1>Julie</h1>
  <p class="price">$250</p>
  <p>Black Mouth Cur Blend</p>
  <p><button>Learn More</button></p>
</div>

<!-- Script is layed out in a sequence (no function) and will execute when page is loaded -->
<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("myMenu");

  // prepare fetch options
  const url = "http://fluffyfriendfinder.nighthawkcodingsociety.com/api/users/";
  const headers = {
    method: 'GET', // *GET, POST, PUT, DELETE, etc.
    mode: 'cors', // no-cors, *cors, same-origin
    cache: 'default', // *default, no-cache, reload, force-cache, only-if-cached
    credentials: 'omit', // include, *same-origin, omit
    headers: {
      'Content-Type': 'application/json'
      // 'Content-Type': 'application/x-www-form-urlencoded',
    },
  };

  // fetch the API
  fetch(url, headers)
    // response is a RESTful "promise" on any successful fetch
    .then(response => {
      // check for response errors
      if (response.status !== 200) {
          const errorMsg = 'Database response error: ' + response.status;
          console.log(errorMsg);
          return;
      }
      // valid response will have json data
      response.json().then(data => {
          console.log(data);

          document.getElementById("name").innerHTML = data.name;
          document.getElementById("uid").innerHTML = data.uid;
          document.getElementById("breed").innerHTML = data.breed;
          document.getElementById("sex").innerHTML = data.sex;
          document.getElementById("dob").innerHTML = data.dob;
          document.getElementById("price").innerHTML = data.price;

          for (const row of data) {
            console.log(row);

            // tr for each row
            const tr = document.createElement("tr");
            // td for each column
            const name = document.createElement("td");
            const uid = document.createElement("td");
            const breed = document.createElement("td");
            const sex = document.createElement("td");
            const dob = document.createElement("td");
            const price = document.createElement("td");

            // data is specific to the API
            name.innerHTML = row.name;
            uid.innerHTML = row.uid; 
            breed.innerHTML = row.breed; 
            sex.innerHTML = row.sex; 
            dob.innerHTML = row.dob; 
            price.innerHTML = row.price; 

            // this builds td's into tr
            tr.appendChild(name);
            tr.appendChild(uid);
            tr.appendChild(breed);
            tr.appendChild(sex);
            tr.appendChild(dob);
            tr.appendChild(price);

            // add HTML to container
            resultContainer.appendChild(tr);
          }
      })
  })
  // catch fetch errors (ie ACCESS to server blocked)
  .catch(err => {
    console.error(err);
    const tr = document.createElement("tr");
    const td = document.createElement("td");
    td.innerHTML = err;
    tr.appendChild(td);
    resultContainer.appendChild(tr);
  });
</script>

