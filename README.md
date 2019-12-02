<!DOCTYPE html>
<html>
<head>
<meta name=”viewport” content=”initial-scale=1.0, user-scalable=no” />
<style type=”text/css”>
html { height: 100% }
body { height: 100%; margin: 0; padding: 0 }
#map_canvas { height: 100% }
</style>

<script”
src=”http://maps.googleapis.com/maps/api/js?key=AIzaSyBH_mFZo48zD0WYLgG04KYNfPs1oWJS07o&sensor=false”>
</script>

</head>

<body>
<div id=”map” style=”width: 500px; height: 400px;”></div>

<script>
var locations = [
['Audiotech Music Store' <br>\'R Av. Manoel Goulart, 756 - Uep1-S.1, Pres. Prudente - SP' <br>
<a href="https://goo.gl/maps/XAdWJCZJQ1AnLRcd7">Como chegar</a>,
-22.124049, -51.391554],
['Atmosfera Musical' <br>\'R. São Luiz, 1214 - Centro - Marília - SP'<br>
<a href="https://goo.gl/maps/sP98otD6Zb96x9Jz7">Como chegar</a>,
-22.212846, -49.952233],
['Vitoria Som Holambra' <br>\'R. Campo do Pouso, 751 - Centro, Holambra - SP'<br>
<a href="https://goo.gl/maps/YcvfAKSefKeovKfH8">Como chegar</a>,   
-22.632290, -47.055485],
['Fábrica do Som' <br>\'Rua Barão de Mota Paes, 234-286 - Centro, Espírito Santo do Pinhal - SP'<br>
<a href="https://goo.gl/maps/mQ4pERY4xZph7RbQ9">Como chegar</a>,
-22.193493, -46.751039],
];

var map = new google.maps.Map(document.getElementById(‘map’), {
zoom: 10,
center: new google.maps.LatLng(-23.497351, -46.621821),
});

map.setOptions({styles: styles});

var infowindow = new google.maps.InfoWindow();

var marker, i;

for (i = 0; i < locations.length; i++) {
marker = new google.maps.Marker({
position: new google.maps.LatLng(locations[i][1], locations[i][2]),
label: locations[i][3],
icon: {
path: google.maps.SymbolPath.FORWARD_CLOSED_ARROW,
strokeColor: locations[i][4],
scale: 6
},
map: map
});

google.maps.event.addListener(marker, ‘click’, (function(marker, i) {
return function() {
infowindow.setContent(locations[i][0]);
infowindow.open(map, marker);
}
})(marker, i));
}
</script>\
</script>
</body>
</html>
