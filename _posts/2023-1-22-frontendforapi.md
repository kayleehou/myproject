---
title: Database CRUD Frontend
layout: default
description: Create and read endpoints in frontend
---

<p>Database API</p>

<table>
  <thead>
  <tr>
    <th>Name</th>
    <th>UID</th>
    <th>Breed</th>
    <th>Sex</th>
    <th>DOB</th>
    <th>Age</th>
    <th>Price</th>
  </tr>
  </thead>
  <tbody id="result">
    <!-- javascript generated data -->
  </tbody>
</table>

<p>Dog Info</p>

<form action="javascript:create_user()">
    <p><label>
        Name:
        <input type="text" name="name" id="name" required>
    </label></p>
    <p><label>
        User ID:
        <input type="text" name="uid" id="uid" required>
    </label></p>
    <p><label>
        Breed:
        <input type="text" name="breed" id="breed" required>
    </label></p>
    <p><label>
        Sex:
        <input type="text" name="sex" id="sex" required>
    </label></p>
    <p><label>
        Price:
        <input type="text" name="price" id="price" required>
    </label></p>
    <p><label>
        Date of Birth:
        <input type="date" name="dob" id="dob">
    </label></p>
    <p>
        <button>Create</button>
    </p>
</form>

<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("result");
  // prepare URL's to allow easy switch from deployment and localhost
  //const url = "http://localhost:8086/api/users"
  const url = "http://fluffyfriendfinder.nighthawkcodingsociety.com/api/users/"
  const create_fetch = url + '/create';
  const read_fetch = url + '/';

  // Load users on page entry
  read_users();


  // Display User Table, data is fetched from Backend Database
  function read_users() {
    // prepare fetch options
    const read_options = {
      method: 'GET', // *GET, POST, PUT, DELETE, etc.
      mode: 'cors', // no-cors, *cors, same-origin
      cache: 'default', // *default, no-cache, reload, force-cache, only-if-cached
      credentials: 'omit', // include, *same-origin, omit
      headers: {
        'Content-Type': 'application/json'
      },
    };

    // fetch the data from API
    fetch(read_fetch, read_options)
      // response is a RESTful "promise" on any successful fetch
      .then(response => {
        // check for response errors
        if (response.status !== 200) {
            const errorMsg = 'Database read error: ' + response.status;
            console.log(errorMsg);
            const tr = document.createElement("tr");
            const td = document.createElement("td");
            td.innerHTML = errorMsg;
            tr.appendChild(td);
            resultContainer.appendChild(tr);
            return;
        }
        // valid response will have json data
        response.json().then(data => {
            console.log(data);
            for (let row in data) {
              console.log(data[row]);
              add_row(data[row]);
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
  }

  function create_user(){
    //Validate Password (must be 6-20 characters in len)
    //verifyPassword("click");
    const body = {
        name: document.getElementById("name").value,
        uid: document.getElementById("uid").value,
        breed: document.getElementById("breed").value,
        sex: document.getElementById("sex").value,
        dob: document.getElementById("dob").value
        price: document.getElementById("price").value,
    };
    const requestOptions = {
        method: 'POST',
        body: JSON.stringify(body),
        headers: {
            "content-type": "application/json",
            'Authorization': 'Bearer my-token',
        },
    };

    // URL for Create API
    // Fetch API call to the database to create a new user
    fetch(create_fetch, requestOptions)
      .then(response => {
        // trap error response from Web API
        if (response.status !== 200) {
          const errorMsg = 'Database create error: ' + response.status;
          console.log(errorMsg);
          const tr = document.createElement("tr");
          const td = document.createElement("td");
          td.innerHTML = errorMsg;
          tr.appendChild(td);
          resultContainer.appendChild(tr);
          return;
        }
        // response contains valid result
        response.json().then(data => {
            console.log(data);
            //add a table row for the new/created userid
            add_row(data);
        })
    })
  }

  function add_row(data) {
    const tr = document.createElement("tr");
    const name = document.createElement("td");
    const uid = document.createElement("td");
    const breed = document.createElement("td")
    const sex = document.createElement("td");
    const dob = document.createElement("td");
    const age = document.createElement("td");
    const price = document.createElement("td");
  

    // obtain data that is specific to the API
    name.innerHTML = data.name; 
    uid.innerHTML = data.uid; 
    breed.innerHTML = data.breed;
    sex.innerHTML = data.sex; 
    dob.innerHTML = data.dob; 
    age.innerHTML = data.age; 
    price.innerHTML = data.price

    // add HTML to container
    tr.appendChild(name);
    tr.appendChild(uid);
    tr.appendChild(breed);
    tr.appendChild(sex);
    tr.appendChild(dob);
    tr.appendChild(age);
    tr.appendChild(price);

    resultContainer.appendChild(tr);
  }

</script>
