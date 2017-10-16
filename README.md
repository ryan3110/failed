# ryan3110.github.io

<html>
    <head>
    <script src="https://maps.google.com/maps/api/js?key=AIzaSyBti8vtXyYggEG4hkLi6T1rjnL6KqW00UE">var cur = 0;
var locations = [
    [
        "Harry Hickman Building",
        48.463761,
         -123.314096
    ],
    
    [
    		"Cornett Building",
        48.463910,
        -123.312916
    ],
    
    [
    		"Cunningham Building",
        48.462306,
        -123.312138
    ]
]

    var map = new google.maps.Map(document.getElementById('map'), {
      zoom: 15,
      center: new google.maps.LatLng(48.463649,  -123.311951),
      mapTypeId: google.maps.MapTypeId.ROADMAP
    });

    var infowindow = new google.maps.InfoWindow();

    var marker, i;

    for (i = 0; i < locations.length; i++) {  
      marker = new google.maps.Marker({
        position: new google.maps.LatLng(locations[i][1], locations[i][2]),
        map: map
      });

      google.maps.event.addListener(marker, 'click', (function(marker, i) {
        return function() {
          infowindow.setContent(locations[i][0] + "  " + locations [i][1]
          + "  " + locations [i][2] + " " + cur);
          cur++;
          infowindow.open(map, marker);
        }
      })(marker, i));
    }</script>
    </head>
  <body><div>
  <div id="map" style="width: 500px; height: 400px;"></div>
</div>
  </body>
  
  
  </html>
