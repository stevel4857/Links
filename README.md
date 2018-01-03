# Links

Play Video Code
https://codepen.io/luiting57/pen/MrwVOm


https://hacks.mozilla.org/2017/10/multi-user-experiences-with-a-frame/
https://jsfiddle.net/donmccurdy/6b5j9p3y/
https://altspacevr.github.io/aframe/examples/
https://developer.mozilla.org/en-US/docs/Games/Techniques/3D_on_the_web/Building_up_a_basic_demo_with_A-Frame

Study A-Frame Core
https://github.com/aframevr/aframe/blob/v0.7.0/docs/components/light.md

JavaScript and how to modify properties, objects and scene elements

https://stackoverflow.com/questions/38880104/how-to-use-javascript-with-a-frame

Adding Real-Time Shadows

https://github.com/aframevr/aframe/blob/v0.7.0/docs/components/light.md


---------------------------

Video Code - look at = play look away=off
-------
<html>
<head>
<script src="https://aframe.io/releases/0.7.1/aframe.min.js"></script> 
</head>
<body>
<a-scene>
<a-assets>
<video id="video1" src="https://d1235ca2z646oc.cloudfront.net/videos/processed/1385/clouds_over_the_mountain_hd_stock_video.mp4-mobile.mp4" autoplay loop crossorigin="anonymous"></video>
</a-assets>
  <a-video id="green" src="#video1"  width="16" height="9" position="0 0 -20">
     <a-animation begin="mouseleave" attribute="material.color" from="white" to="gray" dur="1000"></a-animation>
    <a-animation begin="mouseenter" attribute="material.color" from="gray" to="white" dur="1000"></a-animation>
  </a-video>

  
  <!-- START CURSOR -->
  <a-camera look-controls wasd-controls" position="0 0 2">
    <a-cursor material='color:yellow' fuse='true'>
    </a-cursor>
  </a-camera>
  <!-- END CURSOR -->
  
  <a-videosphere id="sky" src="#video1" rotation="0 180 0"></a-videosphere>
    </a-scene>
                                                           <script>
    var vid = document.getElementById("video1");
vid.volume = 0.0;
vid.pause();

  document.querySelector('#green').addEventListener('click', function(){
  document.getElementById("sky").setAttribute("src","#video1"); 
  vid.volume = 0.1;
  vid.play();
  })
  document.querySelector('#green').addEventListener('mouseleave', function(){
  vid.volume = 0.0;
  vid.pause();
  })
 </script>
</body>
</html>
