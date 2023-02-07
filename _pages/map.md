---
layout: default
permalink: /mapsapi/
title: Near Me Finder
search_exclude: true
---

<!--- This section is Cascading Style Sheet (CSS) and applies to HTML -->
<style>
/* "row style" is flexible size and aligns pictures in center */
.row {
  align-items: center;
  display: flex;
}
#map {
      height: 700px; /* The height is 400 pixels */
      width: 150%; /* The width is the width of the web page */
}

/* "column style" is one-third of the width with padding */
.column {
  flex: 33.33%;
  padding: 5px;
}
</style>

## Breaking News with Maps API
<div id="map"></div>

<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyChhAisKAHMljl0nrnmCOL4zm0Ek6KlK2U&callback=initMap&v=weekly" defer></script>
    
<script>                              
      // Initialize and add the map
      function initMap() {
        // The location of Borrego Springs
        var sd = { lat: 33.1005, lng: -116.3013 };
        // The map, centered at Uluru
        var map = new google.maps.Map(document.getElementById("map"), {
          zoom: 9,
          center: sd,
        });
           // Array of markers 
        var markers = [
          {
          coords : {lat: 32.7157, lng: -117.1611}, 
          content: '<p style="color:blue;">Padres FanFest mayhem: Long lines, crowded concourses, and delayed entry</p>' 
          },
          {
          coords : {lat: 33.4934, lng: -117.1488}, 
          content: '<p style="color:blue;">Temecula - Forklifts Stolen From Home Depot</p>'  
          }, 
          {
          coords : {lat: 33.6846, lng: -117.8265}, 
          content: '<p style="color:blue;">Long Beach State beats UC Irvine in OT</p> '  
          }, 
          {  
          coords : {lat: 32.7920, lng: -115.5631}, 
          content: '<p style="color:blue;"> El Centro will conduct a public hearing for new parks</p>'  
          }, 
          {
          coords : {lat: 33.8734, lng: -115.9010}, 
          content: '<p style="color:blue;">Backpacking Permits For Joshua Tree National Park Available Online</p>'  
          },
          {
          coords : {lat: 33.1192, lng: -117.0864}, 
          content: '<p style="color:blue;">Escondido council appoints Palomar College trustee to vacant seat</p>'  
          },
          {
          coords : {lat: 33.3286, lng: -115.8434}, 
          content: '<p style="color:blue;">Salton Sea reduced inflow, the lake is shrinking and rising in salinity.</p>'  
          },
	
        ];
      
        // Loop through markers 
        for(var i = 0; i < markers.length; i++) { 
          addMarker(markers[i]); 
        }
                                          
        // Add Marker Function 
        function addMarker(props){ 
          var marker =  new google.maps.Marker({ 
            position:props.coords, 
            map:map, 
          });
          // Check content 
          if(props.content) { 
               var infoWindow = new google.maps.InfoWindow({ 
              content:props.content 
               });
            infoWindow.open(map, marker);//display by default
            marker.addListener( 'click', function(){ 
              infoWindow.open(map, marker); 
            });
          }
        }                                          
      }

      window.initMap = initMap;
</script>
<br/>
<br/>
<br/>
<div id="map1"></div>
## Breaking News
> Click below to refresh News.

<br/>
<button name="button" onclick="getNews()" >Get the latest news!!!</button>

<br/>

- <p class="news2_style" id="news1">Click the above button to generate news.</p>
- <p class="news2_style" id="news2"></p>
- <p  class="news2_style" id="news3"></p>
- <p class="news2_style" id="news4"></p>
- <p  class="news2_style" id="news5"></p>

<script>
// Array of 15 news
var newsArray = [
"Bolsonaro supporters storm Brazilian Congress.",
"Kevin McCarthy is new speaker",
"Woman sentenced to three years in state prison for collecting $400,000 in viral GoFundMe scam",
"Ukraine denies Russian claim it killed 600 soldiers",
"Damar Hamlin: Buffalo Bills make stirring display in support of safety during victory",
"Worshippers in Tokyo plunge into ice bath to mark new year",
"Driver crashes and flips vehicle inside drive-through car wash",
"Brazilian police fire tear gas at Bolsonaro supporters",
"Deer rescued from frozen river in Wisconsin",
"Two years after Covid food still tastes rotten",
"Woman dies after thrown from horse at Florida rodeo",
"Dog rescued from frozen Quebec lake",
"DeSantis activates National Guard amid increase of migrant landings on Florida Keys",
"Amid unrest, Iran's hardliners turn their anger to France",
"Filipino Catholics hold big procession after pandemic eases",	
	
];
								       
// this function is called upon button click
function getNews() {
	var time = new Date().getMilliseconds(); //get current time
	var arrayIndex = time % 15; // get the arrray index value < 15
	document.getElementById("news1").innerHTML = newsArray[arrayIndex++]; // replace the p element news 
	if (arrayIndex == 15) {
	    arrayIndex = 0
	} 
	document.getElementById("news2").innerHTML = newsArray[arrayIndex++]; // replace the p element news 
        if (arrayIndex == 15) {
	    arrayIndex = 0
	} 								      								      
	document.getElementById("news3").innerHTML = newsArray[arrayIndex++]; // replace the p element news 
        if (arrayIndex == 15) {
	    arrayIndex = 0
	} 								      								      
      	document.getElementById("news4").innerHTML = newsArray[arrayIndex++]; // replace the p element news 
        if (arrayIndex == 15) {
	    arrayIndex = 0
	} 								      								      
	document.getElementById("news5").innerHTML = newsArray[arrayIndex++]; // replace the p element news 

}
								      				      
			      								   
</script>
	
	
<br/>
<br/>
<br/>

## Click below for latest US Police Chase News 
<a href="https://twitter.com/pcalive">US Police Chase News</a> 
<br/>
<br/>
<br/>	
## Click below for latest San Diego Police Capture News 
<a href="https://twitter.com/SanDiegoPD?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor">San Diego Police Capture News </a> 

<br/><br/><br/>
##  Signup for more Breaking News 
<br/>
<table>
  <thead>
  <tr>
    <th>News</th>
    <th>Network</th>
    <th>Actions</th>
  </tr>
  </thead>
  <tbody id="table">
    <!-- javascript generated data -->
  </tbody>
</table>

<br/>
##  Add Breaking News and Network Details: 

<table>
    <tr>
        <th><label for="name">Breaking News</label></th>
        <th><label for="email">Network</label></th>
    </tr>
    <tr>
        <td><input type="text" name="name" id="name" required></td>
        <td><input type="email" name="email" id="email" placeholder="abc@xyz.org" required></td>
        <td ><button onclick="createUser()">Create</button></td>
    </tr>
</table>

<script>

// Static json, this can be used to test data prior to API and Mo
jsonStr = '[{"_name": "Bolsonaro supporters storm Brazilian Congress.", "_uid": "CNN"}, {"_name": "Kevin McCarthy is new speaker", "_uid": "Fox"}, {"_name": "Woman sentenced to three years in state prison for collecting $400,000 in viral GoFundMe scam", "_uid": "ABC"}, {"_name": "Ukraine denies Russian claim it killed 600 soldiers", "_uid": "NBC"}, {"_name": "Damar Hamlin: Buffalo Bills make stirring display in support of safety during victory", "_uid": "BBC"}]';
	
glob = 1;

function createUser() {
var Table = document.getElementById("table");
Table.innerHTML = "";

    name = document.getElementById("name").value;
    email = document.getElementById("email").value;

    // Convert JSON string to JSON object
    data = JSON.parse(jsonStr);
    
    //str = 
    //TO push new element
    //data.push({"_name": "Thomas3", "_uid": "t8test"});
    data.push({ "_name" : name, "_uid": email});
    
    jsonStr = JSON.stringify(data);
    
    
    //data = JSON.parse(jsonStr);
    //showRows(data);
    showTable();

}
    
function showRows(data) {
// prepare HTML result container for new output
    const table = document.getElementById("table");
    
    data.forEach(user => {
    // build a row for each user
    const tr = document.createElement("tr");

    // td's to build out each column of data
    const name = document.createElement("td");
    const id = document.createElement("td");
    const action = document.createElement("td");
           
    // add content from user data          
    name.innerHTML = user._name; 
    id.innerHTML = user._uid; 

    // add action for update button
    var updateBtn = document.createElement('input');
    updateBtn.type = "button";
    updateBtn.className = "button";
    updateBtn.value = "Update";
    updateBtn.style = "margin-right:16px";
    updateBtn.onclick = function () {
      alert("Update: " + user._uid);
    };
    action.appendChild(updateBtn);

    // add action for delete button
    var deleteBtn = document.createElement('input');
    deleteBtn.type = "button";
    deleteBtn.className = "button";
    deleteBtn.value = "Delete";
    deleteBtn.style = "margin-right:16px"
    deleteBtn.onclick = function () {
      alert("Delete: " + user._uid);
    };
    action.appendChild(deleteBtn);  

    // add data to row
    tr.appendChild(name);
    tr.appendChild(id);
    tr.appendChild(action);

    // add row to table
    table.appendChild(tr);
  });
    
}

function showTable() {

    // Convert JSON string to JSON object
    data1 = JSON.parse(jsonStr);
    
    strName = "_name"
    strNameValue = "nameName"
    strUser = "_uid"
    strUserValue = "uidValue" + glob
    
    //data.push({ "_name" : strNameValue, "_uid": strUserValue});
    //TO push new element
    //data.push({"_name": "Thomas3", "_uid": "t8"});
    //jsonStr = JSON.stringify(data);
    
    //data = JSON.parse(jsonStr);
    showRows(data1);
}

showTable();
</script>




