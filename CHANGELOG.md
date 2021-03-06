#jQuery tinyMap Changelog
###3.4.6
* markerWithLabel 參數可支援整數，表示只顯示以地圖中心為圓心的半徑範圍的 label。（需配合 Geometry libraries）

###3.4.5
* 修正使用字串地址建立標記時，若標記數量 > 10 個以上，會導致之後的標記消失的問題。(By Abraham)

###3.4.4
* 試做以亂數 offset 標記，避免相同位置的標記會造成無法分辨的問題。

###3.4.3
* 修正 modify 時 marker.text 無法作用的問題（若 marker.text 原本未設定，modify 之後會自動建立）。
* 修正 modify 時若未帶入 marker.addr 會造成標記消失的錯誤（移動至 0,0）。
* 修正 get 無法正確取得物件的錯誤。

###3.4.2
* 修正標記使用字串地址造成 Geocoding OVER_LIMIT_QUERY 變成無限循環的問題。

###3.4.1
* 暫時回復為 v3.3.20 使用的 modify 方法。

###3.4.0
* 修正使用 modify 方法時，部份參數無法沿用原始地圖設定而必須重新傳入的問題。
* 修正使用 modify 方法時，若帶入的參數包含圖層，會導致帶入的原生參數無法生效的錯誤。
* 修正異步載入 Googl Maps API 時，可能導致 withLabel, clusterer 無法正常使用的錯誤。
* 將 tinyMapConfigure.clusterer, withlabel 的預設網址修改為 Cloudflare CDN。

###3.3.20
* 修正 center 傳入的地址若不存在會導致 innerHTML 的 JS 錯誤。

###3.3.19
* 修正 marker.markerFitBounds 無法作用的問題。

###3.3.18
* 修正 direction.optimize 無效的錯誤。

###3.3.17
* 將圖層處理的流程移出 Map tilesloaded，避免綁定其他地圖事件時發生衝突。

###3.3.16
* 修改 marker 對於 infoWindow 事件的處理程序：
當設置 marker.text 且未設置 marker.event 的情況下，marker click 預設會綁定為開啟 infoWindow。
反之，當設置了 marker.event 時，infoWindow.open 就需要由使用者自行呼叫。
* 修正無法傳入 google.maps constants 的問題，現在只需以字串型態 'google.maps.constants' 傳入即可轉換。

###3.3.15
* 新增 marker.showLabel（default true） 屬性，可設置 label 預設是否顯示。

###3.3.14
* 移除已棄用的 adsense library 相關程式碼。
* 修正 markerControl 無限讀取標記的錯誤。

###3.3.13
* 修改 autoLocation 使用的 getCurrentPosition 為 watchPosition。

###3.3.12
* 新增 query 方法可查詢地址或座標，取代原本的 $.fn.tinyMapQuery。

###3.3.11
* 修正 marker label 在叢集（ MarkerClusterer）計算後不會隨著隱藏或顯示的問題。
* 修正程式碼以符合 JSHinet 驗證

###3.3.10
* 修正 circle, polygon, polyline 的 created 事件重複綁定的錯誤。

###3.3.9
* 因為 Geocoding API 需要 Server Key，所以暫時移除 tinyMapQuery 函數。
* 修正程式內部執行的 idle 改為 tilesloaded，避免外部設置 idle 後導致圖層無法正常繪製的錯誤。

###3.3.8
* 修正 get, clear 方法改為使用模糊比對的方式取得目標物件。
* 修正 Label 的程式碼，現在已經支援 text, visible... 等狀態更新。
* 新增 markerControl 參數，可輸出 HTMLSelectElement 的標記清單。
 
###3.3.7
* 修正 modify marker 時，移動位置後會閃爍以及事件重複綁定的錯誤。

###3.3.6
* 修正 modify marker 時，Label 會重複產生導致效能降低的錯誤。

###3.3.5
* 修正 modify marker 時，圖示無法修改的錯誤。

###3.3.4
* 修正 modify marker 時，若該 marker 未存在於地圖上卻不會新增的錯誤。
* 移除載入 API 時的 sensor 參數。

###3.3.3.1
* 修正 modify.direction 無法作用的錯誤。

###3.3.3
* 修正 marker modify 時 newLabel, newLabelCSS 無法作用的錯誤。

###3.3.2
* 將所有外部 API 都使用 HTTPS 協定載入。
* 重構 direction 的處理程序。
* 移除 $.fn.tinyMapDistance 公用方法。
* 新增 direction.requestExtra(Object) 參數，以使用 DirectionService Request 的原生參數。
* 新增 direction.renderAll(bool) 參數，可以繪製單一路徑內的多種走法（須配合原生 provideRouteAlternatives 參數）。
 
###3.3.1
* 修正 規劃路徑使用自訂圖示時，起點圖示會同時出現中繼點圖示的錯誤。

###3.3.0
* 重構 marker 的處理程序。
* 重構 getKML 的處理程序。
* 新增 getKML 輸出 polygon, circle 圖層的支援。
* 新增 marker.infoWindowOptions 的原生事件處理。

###3.2.19
* 新增 Direction event.created，觸發於路徑建立時，並回傳 directionsDisplay, response 參數。

###3.2.18
* 修正建立或修改 marker 時，原生屬性失效的問題。

###3.2.17
* 修正 marker.icon 可能會產生 setIcon 錯誤的問題。

###3.2.16
* 修正若啟用 markerCluster 時，標記的 Label 並不會納入叢集計算的問題。

###3.2.15
* 修正 places.location 無法使用陣列、物件及字串格式的問題。

###3.2.14
* 因應 Google Maps API v3.21 新增的 MarkerLabel，原 label, css 更名為 newLabel, newLabelCSS。

###3.2.13
* 修正無法清除 places 物件的問題。

###3.2.12
* 修正 modify 無法新增 places 圖層的錯誤。
* 新增 places.callback(Function) 參數，回傳取得的地方資訊 JSON。

###3.2.11
* 新增 markerWithLabel(bool) 參數，可設置是否載入 MarkerWithLabel 的參數。
* 最佳化 MarkerClusterer 的建立程序。

###3.2.10
* 新增 get 方法的參數 cluster, bound 以取得 cluster 以及 bound 物件。
* 更換 MarkerClusterer 函式庫為 MarkerClustererPlus 版本。

###3.2.9
 * 新增 marker.infoWindowOptions 可自訂 infoWindow 的原生屬性。
 * 新增 adsense 可在地圖上顯示 Adsense 廣告。
 * 新增 close 方法可關閉所有或指定圖層的 infoWindow。

###3.2.8
* 修正 get,clear 方法無法以索引值正確取得圖層的錯誤。
* 修正 created 方法回傳的物件順序以符合原生 API 的規則，現在 created.this 已指向 layer 本身。

###3.2.7
* 修正 panTo 方法不能進行 Chain 操作的問題。
* 新增 get 方法可傳入 'map' 取得地圖物件。

###3.2.6
* 修正 clear 方法無法清除以字串參數傳入的圖層的錯誤。
* 新增 clear callback 於清除完成後執行。

###3.2.5
* 修正 marker, polyline, polygon, circle 在 created 事件內無法取得已建立圖層的錯誤。

###3.2.4
* 修正可能會造成無限迴圈的錯誤。

###3.2.3
* 新增 get 方法第二個參數可直接傳入 'marker' 或 'marker,direction' 等字串，以簡化取得的方式。
* 修正 clear 方法無法完整移除圖層的問題。
* 修正 get 方法回傳格式的問題。

###3.2.2
* 新增 autoLocation 參數可以傳入 Function callback。
* 新增 get 方法可獲取（指定的）marker, polyline, circle... 等圖層。

###3.2.1
* 修正 direction.optimize 若設為 false，waypoint（中繼點）的順序無法依照原始順序的錯誤。

###3.2.0.2
* 修正 marker.text 設置後無法開啟 infoWindow 的錯誤。

###3.2.0.1
* 修正 clear 無法清除圖層的錯誤。

###3.2.0
* 變更 已不需手動引入 Google Maps API 以及 markerclusterer.js。
* 新增 direction 原生 API 屬性的支援。
* 新增 direction.waypoint.icon 屬性，讓每個中繼點都能設置不同的圖示。
* 新增 instance.getDirectionsInfo 方法可取得地圖上所有路徑規劃的資訊（距離、時間）。
* 新增 geolocation 參數以設置 navigator.geolocation。
* 新增 Places Service API。
* 新增 marker.cluster 參數可設置該標記是否加入叢集。
* 新增 kml 支援原生屬性。
* 新增 $.fn.tinyMapQuery 公用方法可轉換地址（經緯座標）為經緯座標（地址）。
* 新增 $.fn.tinyMapDistance 公用方法可計算多個地點之間的距離。
* 新增 clear 方法可指定欲清除的圖層 ID 或順序編號。
* 新增 created 事件，適用 polyline, polygon, circle, marker 等圖層，於建立時執行。
* 修正 destroy 沒有作用的問題。
* 修正 markerCluster 無法設置 maxZoom, gridSize... 等原生屬性的問題。
 
###3.1.7
* 修正 marker 使用字串位置並綁定 idle 事件時 markerFitBounds 會無效的錯誤。
* 修正使用  markerclusterer 時，clear 方法無法移除 marker 的錯誤。

###3.1.6
* 修正執行 modify 時，若傳入的 marker 設有 id 且 addr 為地址字串，會導致該標記消失的錯誤。

###3.1.5
* 修正 direction.waypoint.text 無法設置的錯誤。
* 新增 direction.color 路徑顏色值的設置。

###3.1.4
* 修正前一版本 markerCluster 參數失去作用的錯誤。

###3.1.3
* 修正使用 modify 建立 marker 時，第一個 marker 會建立兩次的錯誤。

###3.1.2
* 修正 polyline 無法綁定事件的錯誤。
* 修正 modify marker 若 marker.id 不存在，則需要設置 forceInsert: true 才會新增至地圖。

###3.1.1
* 修正繪製多個 polygon 時，第二個 polygon 之後的選項沒有作用的錯誤。

###3.1.0
* 捨棄老舊瀏覽器（IE6,7,8）的支援，程式碼改用 javascript 原生語法。
* 修正 modify 無法設置 markerFitBounds 的問題。

###3.0.1
* 修正 modify 大量 marker 時造成效能低落甚至當機的問題。
* 修正 marker.label 未設置時，使用 modify 會無法加入文字層的問題。
* 修正 modify marker 不會套入文字層 css 的錯誤。

###3.0.0
* 新增 getKML 方法，可以將目前地圖上的圖層輸出為 KML。
* 修正 modify marker 如果傳入的 id 不存在時不會新增至地圖的錯誤。

###2.9.9
* polyline, polygon 參數改為陣列型態以支援繪製多組線條和幾何圖形（感謝 karry chang 修正)

###2.9.8
* 新增 google.maps.MapOptions 原生屬性的支援，例如 backgroundColor, heading...。
* 修正 direction.waypoint.text 無法正確設置的錯誤。
* 修正 modify 方法無法變更 streetView 的錯誤。

###2.9.7
* 修正無法建立 marker 的錯誤。
* 現在 marker, polyline, polygon, circle 除了原有參數以外，也支援了原生參數，並可以綁定所有原生事件。

###2.9.6
* 現在 marker.icon 已經可以完整支援 Icon 以及 Symbol 了。
* 修正 direction.waypoint 無法使用 [[lat, lng]...] 格式的錯誤。
* 新增 streetView 參數，可設置更詳細的街景選項及綁定事件。
* 移除 showStreetView 參數（由 streetView.visible 取代）。

###2.9.5
* 清除及修正冗餘的程式碼。
* 修正 modify 方法無法綁定地圖事件的問題。
* 修改 kml 參數支援陣列型態 (string|Array)，可同時顯示多組 KML 軌跡檔，並取消原物件型態的參數。
* 新增 direction.event 綁定事件。
* 新增 destroy 方法可移除地圖。

###2.9.4
* 修正 clear 方法無法清除 規劃路徑 (direction) 自訂圖示的錯誤。

###2.9.3
* 新增 direction.icon 參數可設置 from, to, waypoint 的自訂 icon url。

###2.9.2
* 修正 marker 的地址解析結果會覆寫 addr 參數的問題。

###2.9.1
* 新增 direction 下列參數: fromText, toText, 以及 waypoints.text，可設置各導航點的顯示名稱。

###2.9.0
* 修正 modify marker 時，無法正確設置 text, icon, title, event 的問題。

###2.8.9
* 改善程式碼。
* 現在 tinyMap.center, marker.addr, circle.center, direction.to, direction.from, direction.waypoint
* 已支援多種格式輸入，例如 'lat, lng', [lat, lng], {lat: 'lat', lng: 'lng'}

###2.8.8
* 新增 styles 參數 (string|Array) 可自訂地圖的視覺化選項。目前內建 'greyscale' 灰階可用。

###2.8.7
* 點選未設置 text 參數的 marker 時，地圖上已不會出現多餘的 infoWindow。

###2.8.6
* 參數 center 現在可以支援陣列 [lat, lng] 以及物件 {'lat': 'LAT', 'lng': 'LNG'} 格式的資料了。
* 修正 interval 沒有發生作用的問題。
* 使用 clear 方法時若沒有傳入圖層參數，現在會刪除所有圖層。

###2.8.5
* 路徑規劃新增 direction.autoViewport (bool 預設 true) 參數可設置是否要自動縮放該路線資訊。

###2.8.4
* 修正若 markerFitBounds 設為 true 則有部份的 marker 點選時無法開啟 infoWindow 的錯誤。
* 加入 infoWindowAutoClose (bool) 參數，可設置是否在點選標記時自動關閉其他已開啟的 infoWindow。

###2.8.3
* 修正使用地址及 id 建立標記之後無法再用 id 去操作的錯誤。

###2.8.2
* 新增 autoLocation (bool) 參數設置是否自動取得用戶位置為中心點。

###2.8.1
* 修正 polyline 無法清除的錯誤。

###2.8.0
* 新增參數 polyline.snap(boolean), polyline.getDistance(function)。
* polyline.snap 若為 true 則線條會貼近道路繪製（近似路線規劃功能）。
* polyline.getDistance 可以返回已繪製線條的距離

###2.7.6
* 修正使用 modify marker 可能會影響效能的錯誤。

###2.7.5
* 加入 showStreetView 參數切換是否顯示街景。

###2.7.4
* 修正使用 modify 變更 marker 時，markerCluster 無法作用的問題。

###2.7.3
* 修正使用 modify 時傳入的 marker 無法新增的錯誤。

###2.7.2
* 修正使用 modify 傳入大量 marker 時造成的效能問題及 Label 位置不會跟著更新的錯誤。

###2.7.1
* 修正 clear 方法若使用陣列參數無作用的錯誤。
* 新增 marker.id 參數，作用於使用 modify 方法傳入新的 markers 時，若有已存在的 marker id，則更新標記而不是重新建立。可避免使用 clear 再 modify 造成的閃爍以及 infoWindow 也會移除再重建的問題。

###2.7.0
* 新增 marker.title 參數以解決使用 marker.text 做為預設提示文字的問題。
* 修改 marker.event 參數以支援更多事件。
* 新增 event 參數以自訂地圖事件。

###2.6.7
* 修正 markerCluster 沒有作用的錯誤。

###2.6.6
* 修正: 若建立大量以地址查詢的 marker 時，fitBounds 及 markercluster 可能無法運作的問題。
* 修正: marker text 會過濾 HTML 的問題。
* 修正: 大量呼叫 modify 方法可能會佔用過多記憶體的問題。

###2.6.5
* 新增 direction.panel 參數以顯示導航資訊面板

###2.6.4
* 修正 marker 無法設置的錯誤。
* 修正若 marker 使用文字地址設置時 fitbounds, cluster 會無法作用的錯誤。
* 新增 disableDoubleClickZoom 參數可設置是否雙擊縮放地圖。

###2.6.3
* 修正 disableDefaultUI 無法作用的錯誤。

###2.6.2
* 現在 modify 方法不只能異動圖層，也可以修改所有的地圖選項。

###2.6.1
* 修正使用 markerCluster 時，若頁面有多個地圖則標記會合併在 cluster 地圖上顯示的錯誤。

###2.6.0
* 加入 markerCluster 控制是否以 cluster 方式顯示標記

###2.5.9
* Marker.icon 參數現在可以指定 url, size 以及 anchor。
* 新增 marker.animation 參數以設定動畫效果。

###2.5.8
* 修正呼叫 clear方法無法清除路線規劃圖層的問題。

###2.5.7
* 修正 interval 參數無作用並導致 javascript error 的錯誤。

###2.5.5
* 修正 clear 方法會清除所有地圖圖層的錯誤。

###2.5.4
* 修正使用 center: '字串地址' 時會發生錯誤的問題。

###2.5.2
* 修正使用 modify 方法無法改變 zoom 縮放等級的錯誤。
* 修正使用 clear 方法無法清除 Label 的錯誤。

###2.5.1
* 新增 disableDefaultUI, maxZoom, minZoom, panControl, panControlOptions, streetViewControl, streetViewControlOptions 參數。

###2.5.0
* 廢除原有的 tinyMapPanTo, tinyMapModify, tinyMapClear 方法，改為由 tinyMap 以字串參數呼叫。
* 新增 interval 參數可以設定每次 geocoder 查詢的間隔秒數（毫秒）

###2.4.4
* 修正 marker 使用地址字串時發生的 geocoder 錯誤。

###2.4.3
* 修正使用 IE8（或以下版本）不支援 hasOwnProperty 導致出現 javascript 錯誤的問題。
* 現在 infoWindow 將寫入 marker 陣列內以方便外部存取。

###2.4.2
* 修正設置 markerFitBounds = true 時，地圖無法自動置中及縮放的錯誤。

###2.4.1
* 新增 tinyMapClear 方法可以在清除指定地圖上的圖層。

###2.4.0
* 新增 tinyMapModify 方法可以在指定地圖上動態加入標記、軌跡、繪製圖形等圖層。

###2.3.1
* 修正 marker 使用地址字串會造成無法顯示的錯誤。

###2.3.0
* 程式碼重構，提昇執行效能並縮小檔案。
* 呼叫 tinyMapPanTo 不再需要加上 data-tinyMap 屬性。

###2.2.9
* 新增 markerFitBounds (Bool) 參數，若為 true (預設) 則地圖將自動縮放及置中以顯示地圖標記。

###2.2.8
* 若 marker.addr 輸入值為陣列座標值時，將不使用 geocode 查詢位置，避免因 marker 數量太多導致無法一次全部顯示。

###2.2.7
* 加入 tinyMapPanTo 方法可移動地圖中心至指定的位置。

###2.2.6
* 修正若輸入的地址為座標時，自動使用精準模式進行定位。

###2.2.5
* 加入 KML 軌跡顯示功能

###2.2.4
* 修正因 Geocode 每秒請求限制，導致地圖數量無法顯示超過 12 個的錯誤。
* 加入 loading 參數可顯示地圖載入前顯示的自訂文字。

###2.2.3
* 修正因 Geocode 每秒請求限制導致 marker 數目無法超過 8-10 個的錯誤。

###2.2.2
* Marker 群組移除 display 參數，並加入 label 參數用以設定文字層的內文
* 修正路徑規劃功能的中途點順序會相反的錯誤
* 加入路徑規劃 optimize 參數表示是否最佳化路徑

###2.2.1
* 路徑規劃加入設置中途點的功能
* 加入查無地址可自訂錯誤訊息的參數

###2.2
* 加入可直接於地圖顯示 Marker 文字層的功能

###2.1
* 加入 polyline, polygon, circle 等繪製功能
* 改用 MIT 授權釋出

###2.0.1
* 修正當座標或地址無效時的未預期錯誤
* 若標記說明包含 HTML Code 時，icon title 將只保留文字而忽略任何標籤

###2.0
* 改用 Google Maps API v3 重寫

###1.0.1
* 修正部份程式錯誤以符合 JSLint
* 改以 Google AJAX API 呼叫 map

###1.0
* Release
