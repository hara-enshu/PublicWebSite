
//地図の初期位置設定（松山）
var map = L.map('mapid', {
    center: [33.839165, 132.76564],
    zoom: 13,
});

//地図データ取得
var tileLayer = L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© <a href="http://osm.org/copyright">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>',
});tileLayer.addTo(map);

/* 
    ジオコーディング
    address : 住所データ or ランドマーク
    latlng[1] : 緯度
    latlng[0] : 経度
*/
function getLatLng1(){
    var address = $('#address1').val();
        $.ajax({
            url:'https://msearch.gsi.go.jp/address-search/AddressSearch?q=' + address,
            }).done(function(res, textStatus, jqXHR) {
            if( res.length ){
                var latlng = res[0].geometry.coordinates;
                $('#lat1').val(latlng[0]);
                $('#lng1').val(latlng[1]);
                L.marker([latlng[1],latlng[0]]).addTo(map);
            }
    }   );
}