---
layout: categories
permalink: /map/
title: Near Me Finder
search_exclude: true
---
<!--- CSS Styling Sheet-->
<style>

.row {
  align-items: center;
  display: flex;
}
#map {
      height: 700px; /* The height is 400 pixels */
      width: 150%; /* The width is the width of the web page */
}

.column {
  flex: 33.33%;
  padding: 5px;
}
</style>

## Near Me Finder
<div id="map"></div>

<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyD0erTF9F5UoSk6YZ4wIWNg0j7vbkSXGcw&callback=initMap&v=weekly" defer></script>
    
<script>                              
      // Initialize and add the map
      function initMap() {
        // The location of Borrego Springs
        var sd = { lat: 33.1005, lng: -116.3013 };

        var map = new google.maps.Map(document.getElementById("map"), {
          zoom: 9,
          center: sd,
        });

        var markers = [
          {
          coords : {lat: 32.832809, lng: -117.271271}, 
          content: '<p style="color:blue;">House 1-La Jolla</p>' 
          },
          {
          coords : {lat: 32.999780, lng: -117.257200}, 
          content: '<p style="color:blue;">House 2-North Pacific Beach</p>'  
          }, 
          {
          coords : {lat: 32.713631, lng: -117.155602}, 
          content: '<p style="color:blue;">House 3-Downtown San Diego</p> '  
          }, 
          {  
          coords : {lat: 33.158350, lng: -117.032630}, 
          content: '<p style="color:blue;"> Daves Hot Chicken (Food)</p>'  
          }, 
          {
          coords : {lat: 32.912239, lng: -117.147217}, 
          content: '<p style="color:blue;">Raising Canes (Food)</p>'  
          },
          {
          coords : {lat: 32.769939, lng: -117.251091}, 
          content: '<p style="color:blue;">Belmont Park (Activity)</p>'  
          },
          {
          coords : {lat: 33.010290, lng: -116.947480}, 
          content: '<p style="color:blue;">Potato Chip Rock (Activity)</p>'  
          },
	
        ];
      
        // Loop through markers 
        for(var i = 0; i < markers.length; i++) { 
          addMarker(markers[i]); 
        }
                                          
        // Add Marker 
        function addMarker(props){ 
          var marker =  new google.maps.Marker({ 
            position:props.coords, 
            map:map, 
          });

          if(props.content) { 
               var infoWindow = new google.maps.InfoWindow({ 
              content:props.content 
               });
            infoWindow.open(map, marker);
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