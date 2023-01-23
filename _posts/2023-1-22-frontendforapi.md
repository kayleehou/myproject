---
layout: post
description: frontend for create and read endpoints 
categories: [markdown]
title: Frontend for API 

---
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body {
  font-family: Arial, Helvetica, sans-serif;
}

* {
  box-sizing: border-box;
}

/* Create a column layout with Flexbox */
.row {
  display: flex;
}

/* Left column (menu) */
.left {
  flex: 35%;
  padding: 15px 0;
}

.left h2 {
  padding-left: 8px;
}

/* Right column (page content) */
.right {
  flex: 65%;
  padding: 15px;
}

/* Style the search box */
#mySearch {
  width: 100%;
  font-size: 18px;
  padding: 11px;
  border: 1px solid #ddd;
}

/* Style the navigation menu inside the left column */
#myMenu {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

#myMenu li a {
  padding: 12px;
  text-decoration: none;
  color: black;
  display: block
}

#myMenu li a:hover {
  background-color: #4f5359;
}
</style>

<html>
<head>
<style>
.button {
  background-color: #040404;
  border: none;
  color: rgb(0, 0, 0);
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 10px 2px;
  cursor: pointer;
}
</style>
</head>
<body>


<a href="https://kayleehou.github.io/escaperoom/2022/11/02/mcuhome.html" class="button">Click to Return Home</a>

</body>
</html>

</head>
<body>

<h1 style="font-family:'Courier New'; text-align:center; font-size: 50px">Marvel Searchbar</h1>
<p style="font-family:'Courier New'; text-align:center; font-size: 18px">Start to type for a specific Marvel comic or character inside the search bar to "filter" the search options.</p>
</body>
</html>


<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
</head>
<body>

<div class="row">
  <div class="left" style="background-color:#3d413e;">
    <h2>Menu</h2>
    <input type="text" id="mySearch" onkeyup="myFunction()" placeholder="Search.." title="Type in a category">
    <ul id="myMenu">
      <!-- <li><a href="https://marvelcinematicuniverse.fandom.com/wiki/Agents_of_S.H.I.E.L.D.:_The_Chase">Agents of S.H.I.E.L.D.: The Chase</a></li>
      <li><a href="https://marvelcinematicuniverse.fandom.com/wiki/Ant-Man_-_Scott_Lang:_Small_Time">Ant-Man - Scott Lang: Small Time</a></li>
      <li><a href="https://marvelcinematicuniverse.fandom.com/wiki/Ant-Man_and_the_Wasp_Prelude">Ant-Man and the Wasp Prelude</a></li>
      <li><a href="https://marvelcinematicuniverse.fandom.com/wiki/Ant-Man_Prelude">Ant-Man Prelude</a></li>
      <li><a href="https://marvelcinematicuniverse.fandom.com/wiki/Ant-Man:_Larger_Than_Life">Ant-Man: Larger Than Life</a></li>
      <li><a href="https://marvelcinematicuniverse.fandom.com/wiki/Avengers:_Age_of_Ultron_Prelude_-_This_Scepter%27d_Isle">Avengers: Age of Ultron Prelude - This Scepter'd Isle</a></li>
      <li><a href="https://marvelcinematicuniverse.fandom.com/wiki/Avengers:_Age_of_Ultron:_Episode_0">Avengers: Age of Ultron: Episode 0</a></li>
      <li><a href="https://marvelcinematicuniverse.fandom.com/wiki/Avengers:_Endgame_Prelude">Avengers: Endgame Prelude</a></li> -->
    </ul>
  </div>
  
  <div class="right" style="background-color:#3d413e;">
    <h2>Learn More!</h2>
    <p>Happy Searching! </p>
  </div>
</div>

<script>
function myFunction() {
  var input, filter, ul, li, a, i;
  input = document.getElementById("mySearch");
  filter = input.value.toUpperCase();
  ul = document.getElementById("myMenu");
  li = ul.getElementsByTagName("li");
  for (i = 0; i < li.length; i++) {
    a = li[i].getElementsByTagName("a")[0];
    if (a.innerHTML.toUpperCase().indexOf(filter) > -1) {
      li[i].style.display = "";
    } else {
      li[i].style.display = "none";
    }
  }
}
</script>

<!-- Script is layed out in a sequence (no function) and will execute when page is loaded -->
<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("myMenu");

  // prepare fetch options
  const url = "http://172.22.157.142:8086/api/users/";
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

          for (const row of data) {
            console.log(row);

            // li for each row
            const li = document.createElement("li"); 
            
            // a for each li
            const a = document.createElement("a");
            a.setAttribute("href", row.link);
            a.innerHTML = row.title;
            li.appendChild(a);


            // add li to result
            resultContainer.appendChild(li);
          }
      })
  })
  // catch fetch errors (ie ACCESS to server blocked)
  .catch(err => {
    console.error(err);
  });
</script>
