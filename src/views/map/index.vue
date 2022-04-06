<template>
  <div class="">
    <div class="map_title">
      <h3>JSAPI Vue2地图组件示例</h3>
    </div>
    <div id="container" />
  </div>
</template>
<script>
import AMapLoader from '@amap/amap-jsapi-loader'

export default {
  name: 'Map',
  data() {
    return {
      map: null
    }
  },
  created() {

  },
  mounted() {
    this.initAMap()
  },
  methods: {

    initAMap() {
      AMapLoader.load({
        key: 'e2620d5327215a3e2a09ede88ec20a54', // 设置您的key
        // version: '2.0',
        plugins: ['AMap.ToolBar', 'AMap.Driving'],
        AMapUI: {
          version: '1.1',
          plugins: []

        },
        Loca: {
          // version: '2.0'
        }
      }).then((AMap) => {
        this.map = new AMap.Map('container', {
          pitch: 55,
          viewMode: '3D',
          zoom: 8,
          zooms: [2, 22],
          center: [120.622147, 31.307842]
        })

        var radius = 1000 * 100
        var xs = new AMap.Circle({
          center: [120.430106, 30.2347],
          radius: radius, // 半径
          borderWeight: 3,
          // strokeColor: '#FF33FF',
          strokeOpacity: 1,
          strokeWeight: 6,
          fillOpacity: 0.4,
          strokeStyle: 'dashed',
          strokeDasharray: [10, 10],
          // 线样式还支持 'dashed'
          // fillColor: '#1791fc',
          zIndex: 50
        })

        var wx = new AMap.Circle({
          center: [120.434006, 31.496557],
          radius: radius, // 半径
          borderWeight: 3,
          // strokeColor: '#FF33FF',
          strokeOpacity: 1,
          strokeWeight: 6,
          fillOpacity: 0.4,
          strokeStyle: 'dashed',
          strokeDasharray: [10, 10],
          // 线样式还支持 'dashed'
          // fillColor: '#1791fc',
          zIndex: 50
        })

        var hq = new AMap.Circle({
          center: [121.343125, 31.198072],
          radius: radius, // 半径
          borderWeight: 3,
          // strokeColor: '#FF33FF',
          strokeOpacity: 1,
          strokeWeight: 6,
          fillOpacity: 0.4,
          strokeStyle: 'dashed',
          strokeDasharray: [10, 10],
          // 线样式还支持 'dashed'
          // fillColor: '#1791fc',
          zIndex: 50
        })

        var tz = new AMap.Circle({
          center: [119.720115, 32.567203],
          radius: radius, // 半径
          borderWeight: 3,
          strokeColor: '#FF33FF',
          strokeOpacity: 1,
          strokeWeight: 6,
          fillOpacity: 0.4,
          strokeStyle: 'dashed',
          strokeDasharray: [10, 10],
          // 线样式还支持 'dashed'
          fillColor: '#1791fc',
          zIndex: 50
        })

        var nj = new AMap.Circle({
          center: [118.872107, 31.732209],
          radius: radius, // 半径
          borderWeight: 3,
          strokeColor: '#FF33FF',
          strokeOpacity: 1,
          strokeWeight: 6,
          fillOpacity: 0.4,
          strokeStyle: 'dashed',
          strokeDasharray: [10, 10],
          // 线样式还支持 'dashed'
          fillColor: '#1791fc',
          zIndex: 50
        })

        var cz = new AMap.Circle({
          center: [119.783973, 31.919484],
          radius: radius, // 半径
          borderWeight: 3,
          strokeColor: '#FF33FF',
          strokeOpacity: 1,
          strokeWeight: 6,
          fillOpacity: 0.4,
          strokeStyle: 'dashed',
          strokeDasharray: [10, 10],
          // 线样式还支持 'dashed'
          fillColor: '#1791fc',
          zIndex: 50
        })

        this.map.add(xs)
        this.map.add(wx)
        this.map.add(hq)
        this.map.add(tz)
        this.map.add(cz)
        this.map.add(nj)

        // 缩放地图到合适的视野级别
        this.map.setFitView([xs, wx, hq, cz, nj, tz])
      }).catch(e => {
        console.log(e)
      })
    }
  }

}
</script>
<style  scoped>
    .home_div{
        padding:0px;
        margin: 0px;
        width: 100%;
        height: 100%;
        position: relative;
    }
    #container{
        padding:0px;
        margin: 0px;
        width: 100%;
        height: 100%;
        position:absolute;
    }
    .map_title{
         position:absolute;
         z-index: 1;
         width: 100%;
         height: 50px;
         background-color: rgba(27, 25, 27, 0.884);

    }
    h3{
        position:absolute;
        left: 10px;
        z-index: 2;
        color: white;
    }
</style>
