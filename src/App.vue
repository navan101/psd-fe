<template>
  <div id="app">
    <div>
      <button @click="fetchData">fetch</button>
      <!-- <img
        class="imgSrc"
        src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAABQBAMAAAB8P++eAAAAMFBMVEX////7+/vr6+vNzc2qqqplywBWrQD/Y5T/JTf+AADmAABeeEQvNydqAAAGBAMAAAGoF14oAAAEBUlEQVR42u2WTUwUVxzA/2925LIojsyqCLtMqSQeFJeFROPHstjdNkZdkaiX9mRTovYgSYNFE43Rg5IeNG5SqyaVcGzXkvTm7hZWq9bKriAYYzSLBI3WAplp0jY2kV3fzPuYGcBxD/bmO0zevPeb//f7v0FQ5EDvwf8LFG89ixYDol9Wo+smKal2sHF6kM6q7qbE5tY03d7SHR6ygiuvwY1txkzIlPaD3NQ4Zryk/PCP1wKibBlI97dq+idXUxqgcEkVnruS/smRpuWaCbrHU5pc/wyTQsata0U77wVBTlRP9UNkT9oE61K9AHL9VERbeTVurMjNm54mqrFw8CwKmWBfpf6V2Dx/TdxN3YjMf2JwIEZ8JnjnEbEjvLAQZ1EKlxkciJ9UcdD1Z5ztDmgsgPIrMkWtMgfd41xOYXZOIjUcLB3tdchypHWIgb5k2gH0nE0zMHjRCRTLWxgY/VQrDuybcAQ/DDEwmwEn8COlSDBcTUE0GXcEjRzqoDDhDH7sfccg2szAt9hogjBFQFRmDyd9N1VTEFegXXKEVKQFJHEUd0DSKhLthIm0HSQpnNdCNizgq147GP0m7QTygNMye6NqM9ekwlG4kLI5I4cMZ+bVhMA8MwX1rw9oIjakAYX6jXlBRRJ4BF6PwmRSfQyLFhJwWy/IG8khKuirljODG0DfGAd3qCBNEol5vCqFAxqYLeUyB0H2A2Q0DspRD3BQfJEc5KBl6KprG6pNEPqqfkKzOQBsha2bQeVw6g3nSySaGYgb99ylhsLDLVYQ3E+oozOGHKzVbCBs+HkuUm6ivd4E0ZYeNTPTTrn51+0wA9TJgpZVLeaV1y+4yS8c64W0/AcFTBCHK/fFEMwFAmo4KRldE0ZxsF8cGbTuzYqHtOz8t6e8TMk5CcjNSC+kdcfgPyag9AoDhUQARmvAcIiAW3v0JzWJg64BJXdBQ21+/b4zwMqRW5dA2h3I7+onYJd+Y4i3FbyMxz4hxE7hS2MBdSq6Fgq6Bny/dxv6Sk76COj6Yz91ZG8dToQ7oYNCqu4QjX9FK5UoPt/PXO701mruhwcxGP2ecahzzxBtUtlzLHclsXtBA6wc+a2brlUc8TCvg5cPM7LiaOPT8Y4ub3bpAbqy+MQ18xRmvIe5nr83YXDt8Nca0/GveWniSHByybEVwx1dD1ccYB/6yF8DTaGcYLFA391o6DjjohaWfKXQ/xCWazmhPDhNbYf2WH4fse9zhRUkLwrXlUD+9iVD5HR77KWheclxkqsZ1bM+pqcWZ2xVe0zXjPb6pyO8IK1l5trcA7mLKuo48+VpQG0BuPmZeTbs9Vi+9oQyqv6Ieyou4FybU+HqRS4o+TH1VG7MvgFFjvfguwFfA4FobmCxcnTPAAAAAElFTkSuQmCC"
      />-->
      <canvas id="canvas" width="600" height="600"></canvas>
      <!-- <fabric-canvas
      :height="600"
      :width="500"
    >
      <fabric-rectangle></fabric-rectangle>
      </fabric-canvas>-->
    </div>
  </div>
</template>

<script>
// import vueFabricWrapper from "vue-fabric-wrapper";
import { fabric } from "fabric";
import Axios from "axios";
// import dataJson from "../public/data-test-2.json";

export default {
  name: "App",
  // components: {
  //   FabricCanvas: vueFabricWrapper.FabricCanvas,
  //   FabricRectangle: vueFabricWrapper.FabricRectangle
  // },
  mounted() {
    // console.log(dataJson);
    // initialize fabric canvas and assign to global windows object for debug
  
    // canvas.loadFromJSON(dataJson, canvas.renderAll.bind(canvas), function (
    //   o,
    //   object
    // ) {
    //   fabric.log(o, object);
    // });

    // var canvas = new fabric.Canvas("canvas");

    // let link = "http://localhost:3000/public/images/Rectangle 1_2.png";

    // let width = 739;
    // let height = 742;

    // var hRatio = width / 3000;
    // var vRatio = height / 2250;
    // var ratio = Math.min(hRatio, vRatio);
    // var centerShift_x = (canvas.width - width * ratio) / 2;
    // var centerShift_y = (canvas.height - height * ratio) / 2;
    // console.log(ratio)
    // fabric.Image.fromURL(link, function (img) {
    //   img.set({
    //     top: centerShift_y,
    //     left: centerShift_x,
    //   });

    //   img.scaleToWidth(600 * ratio);
    //   img.scaleToHeight(600 * ratio);

    //   canvas.add(img);
    // });


    //  link = "http://localhost:3000/public/images/Layer 0_4.png";
    //  width = 3000;
    //  height = 2250;
    //  hRatio = width / 3000;
    //  vRatio = height / 2250;
    //  ratio = Math.min(hRatio, vRatio);
    //  centerShift_x = (canvas.width - width * ratio) / 2;
    //  centerShift_y = (canvas.height - height * ratio) / 2;
     
    // fabric.Image.fromURL(link, function (img) {
    //   img.set({
    //     top: centerShift_y,
    //     left: centerShift_x,
    //   });

    //   img.scaleToWidth(600 * ratio);
    //   img.scaleToHeight(600 * ratio);

    //   canvas.add(img);
    // });


  },
  methods: {
    fetchData() {
      Axios.get("http://localhost:3000/psd").then(({ data }) => {
        console.log(data);
        var canvas = new fabric.Canvas("canvas");
        // data = data.sort(p => p.layerEnd)
        data = data.sort((p) => {
          return p.layerEnd;
        });
        // console.log(data[1]);
        // let p = data[4];
        let width = 3000
        let height = 2250
        data.forEach((p) => {
        var hRatio =  p.width /width;
        var vRatio =  p.height /height;
        var ratio = Math.min(hRatio, vRatio);
        var centerShift_x = (canvas.width - p.width * ratio) / 2;
        var centerShift_y = (canvas.height - p.height * ratio) / 2;
        // console.log(centerShift_y);
        // console.log(centerShift_x);
        fabric.Image.fromURL(p.image, function (img) {
          img.set({
            top: centerShift_y,
            left: centerShift_x,
          });

          img.scaleToWidth(600 * ratio);
          img.scaleToHeight(600 * ratio);
          canvas.add(img);
        });
        });
      });
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#app > div {
  position: relative;
  widows: 100%;
  height: 100vh;
}
.canvas-container {
  position: fixed;
  top: 50%;
  left: 50%;
  /* bring your own prefixes */
  transform: translate(-50%, -50%);
  background-color: #f3efee;
}
</style>
