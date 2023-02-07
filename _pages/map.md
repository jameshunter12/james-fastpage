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

<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyD0erTF9F5UoSk6YZ4wIWNg0j7vbkSXGcw&callback=initMap&v=weekly" defer></script>
    
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