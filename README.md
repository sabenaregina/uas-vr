<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="initial-scale=1.0,user-scalable=no,maximum-scale=1,width=device-width">
    <title>Gereja Lampung Virtual Reality Tour</title>
    <script src="./js/aframe/aframe.min.js"></script>
    <script src="./js/aframe/aframe-event-set-component.min.js"></script>
    <script src="./js/aframe/aframe-layout-component.min.js"></script>
    <script src="./js/aframe/aframe-template-component.min.js"></script>
    <script src="./js/aframe/aframe-proxy-event-component.min.js"></script>
</head>

<body>
    <a-scene>
        <a-assets>
            <audio id="click-sound" crossorigin="anonymous" src="./audio/click.ogg"></audio>
            <img id="gereja-01" crossorigin="anonymous" src="./assets/gbi.png">
            <img id="gereja-02" crossorigin="anonymous" src="./assets/gbir.png">
            <img id="gereja-03" crossorigin="anonymous" src="./assets/gbp.png">
            <img id="gereja-04" crossorigin="anonymous" src="./assets/ggp.png">
            <img id="gereja-05" crossorigin="anonymous" src="./assets/gkpi.png">
            <img id="gereja-06" crossorigin="anonymous" src="./assets/gkt.png">
            <img id="gereja-06" crossorigin="anonymous" src="./assets/mdc.png">
            <img id="gereja-08" crossorigin="anonymous" src="./assets/gmiimanuel.png ">
            <img id="gereja-09" crossorigin="anonymous" src="./assets/gpdim.png">
            <img id="gereja-10" crossorigin="anonymous" src="./assets/hki.png ">
            <img id="gereja-11" crossorigin="anonymous" src="./assets/gbkp.png">
            <img id="gereja-12" crossorigin="anonymous" src="./assets/santoyohanes.png ">
            <img id="gereja-13" crossorigin="anonymous" src="./assets/gbiaf.png">
            <img id="gereja-14" crossorigin="anonymous" src="./assets/gerejapentakosta.png">
            <img id="gereja-15" crossorigin="anonymous" src="./assets/gkpa.png">
            <img id="gereja-16" crossorigin="anonymous" src="./assets/gkps.png">
            <img id="gereja-17" crossorigin="anonymous" src="./assets/gktk.png">
            <img id="gereja-18" crossorigin="anonymous" src="./assets/gms.png ">
            <img id="gereja-19" crossorigin="anonymous" src="./assets/gys.png">
            <img id="gereja-20" crossorigin="anonymous" src="./assets/jki.png">
          



            <!-- Image link template to be reused. -->
            <script id="link" type="text/html">
                <a-entity class="link" geometry="primitive: sphere; radius: 0.5; rotation: 90 0 90"
                    material="shader: flat; src: ${thumb}" event-set__mouseenter="scale: 1.2 1.2 1"
                    event-set__mouseleave="scale: 1 1 1"
                    event-set__click="_target: #image-360; _delay: 300; material.src: ${src}"
                    proxy-event="event: click; to: #image-360; as: fade" sound="on: click; src: #click-sound">
                </a-entity>
            </script>
        </a-assets>

        <!-- Camera + cursor. -->
        <a-entity id="camera" camera look-controls>
            <a-cursor id="cursor" position="0 0 -5" geometry="primitive: ring; radiusInner: 0.05; radiusOuter: 0.1;"
                material="color: black; shader: flat" cursor="maxDistance: 30; fuse: true"
                animation__click="property: scale; from: 0.5 0.5 0.5; to: 1 1 1;startEvents: click; dur: 150;easing:easeInQuad;"
                animation__fusing="property: scale; from: 1 1 1; to: 0.5 0.5 0.5;startEvents: fusing; dur: 1000;easing:easeInQuad;"
                event-set__mouseenter="_event: mouseenter; color: springgreen"
                event-set__mouseleave="_event: mouseleave; color: black" raycaster="objects: .link"></a-cursor>
        </a-entity>
        <!-- 360-degree image. -->
        <a-sky id="image-360" radius="10" src="#gereja-01"
            animation__fade="property: components.material.material.color; type: color; from: #FFF; to: #000; dur: 300; startEvents: fade"
            animation__fadeback="property: components.material.material.color; type: color; from: #000; to: #FFF; dur: 300; startEvents: animationcomplete__fade">
        </a-sky>

        <!-- Image links. -->
        <a-text value="gereja" position="-5 -4 0.5" rotation="0 90 0"></a-text>
        <a-entity id="links" layout="type: line; margin: 1.5" position="-5 -3 1.5" rotation="-90 90 0">
            <a-entity template="src: #link" data-src="#gereja-01" data-thumb="#gereja-01"></a-entity>
            <a-entity template="src: #link" data-src="#gereja-02" data-thumb="#gereja-02"></a-entity>
            <a-entity template="src: #link" data-src="#gereja-03" data-thumb="#gereja-03"></a-entity>
        </a-entity>
        <a-text value="gereja" position="0 -4 -5" rotation="0 0 0"></a-text>
        <a-entity id="links" layout="type: line; margin: 1.5" position="-2 -3 -5" rotation="-90 0 0">
            <a-entity template="src: #link" data-src="#gereja-04" data-thumb="#gereja-04"></a-entity>
            <a-entity template="src: #link" data-src="#gereja-05" data-thumb="#gereja-05"></a-entity>
            <a-entity template="src: #link" data-src="#gereja-06" data-thumb="#gereja-06"></a-entity>
            <a-entity template="src: #link" data-src="#gereja-07" data-thumb="#gereja-07"></a-entity>
        </a-entity>
        <a-text value="gereja" position="5 -4 -0.5" rotation="0 -90 0"></a-text>
        <a-entity id="links" layout="type: line; margin: 1.5" position="5 -3 -1.5" rotation="-90 -90 0">
            <a-entity template="src: #link" data-src="#gereja-01" data-thumb="#gereja-01"></a-entity>
            <a-entity template="src: #link" data-src="#gereja-02" data-thumb="#gereja-02"></a-entity>
            <a-entity template="src: #link" data-src="#gereja-02" data-thumb="#gereja-03"></a-entity>
        </a-entity>
        <a-text value="gereja" position="0 -4 5" rotation="0 180 0"></a-text>
        <a-entity id="links" layout="type: line; margin: 1.5" position="0 -3 5" rotation="-90 180 0">
            <a-entity template="src: #link" data-src="#gereja-01" data-thumb="#gereja-01"></a-entity>
            <a-entity template="src: #link" data-src="#gereja-02" data-thumb="#gereja-02"></a-entity>
        </a-entity>

    </a-scene>
</body>

</html>
