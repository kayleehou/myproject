---
title: Database CRUD Frontend
layout: default
description: Create and read endpoints in frontend
---

<p>Database API</p>

<table>
  <thead>
  <tr>
    <th>First Name</th>
    <th> Last Name</th>
    <th>Extracurricular</th>
    <th>Hours Per Week</th>
    <th>Coach Name</th>
  </tr>
  </thead>
  <tbody id="result">
    <!-- javascript generated data -->
  </tbody>
</table>

<script>
  // prepare HTML result container for new output
  const resultContainer = document.getElementById("result");

  // prepare fetch options
  const url = "http://172.22.157.142:8086/api/users/";
  const options = {
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
  fetch(url, options)
      // response is a RESTful "promise" on any successful fetch
    .then(response => {
      // check for response errors
      if (response.status !== 200) {
          const errorMsg = 'Database response error: ' + response.status;
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
            // tr and td element id's to build out for each row
            const tr = document.createElement("tr");
            const firstName = document.createElement("td");
            const lastName = document.createElement("td");
            const extracurricular = document.createElement("td")
            const hoursPerWeek = document.createElement("td");
            const coachName = document.createElement("td");
          

            // obtain data that is specific to the API
            firstName.innerHTML = data[row].firstName; 
            lastName.innerHTML = data[row].lastName; 
            extracurricular.innerHTML = data[row].extracurricular;
            hoursPerWeek.innerHTML = data[row].hoursPerWeek; 
            coachName.innerHTML = data[row].coachName; 

            // add HTML to container
            tr.appendChild(firstName);
            tr.appendChild(lastName);
            tr.appendChild(extracurricular);
            tr.appendChild(hoursPerWeek);
            tr.appendChild(coachName);

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