---
{"dg-publish":true,"permalink":"/admin/sam-s-play-ground/","updated":"2025-12-30T11:20:44.814+00:00"}
---


```javascript
const svgImage = document.getElementById("svgImage");
const svgContainer = document.getElementById("svgContainer");

var viewBox = {x:0,y:0,w:svgImage.clientWidth,h:svgImage.clientHeight};
svgImage.setAttribute('viewBox', `${viewBox.x} ${viewBox.y} ${viewBox.w} ${viewBox.h}`);
const svgSize = {w:svgImage.clientWidth,h:svgImage.clientHeight};
var isPanning = false;
var startPoint = {x:0,y:0};
var endPoint = {x:0,y:0};;
var scale = 1;

svgContainer.onmousewheel = function(e) {
   e.preventDefault();
   var w = viewBox.w;
   var h = viewBox.h;
   var mx = e.offsetX;//mouse x  
   var my = e.offsetY;    
   var dw = w*Math.sign(e.deltaY)*0.05;
   var dh = h*Math.sign(e.deltaY)*0.05;
   var dx = dw*mx/svgSize.w;
   var dy = dh*my/svgSize.h;
   viewBox = {x:viewBox.x+dx,y:viewBox.y+dy,w:viewBox.w-dw,h:viewBox.h-dh};
   scale = svgSize.w/viewBox.w;
   zoomValue.innerText = `${Math.round(scale*100)/100}`;
   svgImage.setAttribute('viewBox', `${viewBox.x} ${viewBox.y} ${viewBox.w} ${viewBox.h}`);
}


svgContainer.onmousedown = function(e){
   isPanning = true;
   startPoint = {x:e.x,y:e.y};   
}

svgContainer.onmousemove = function(e){
   if (isPanning){
  endPoint = {x:e.x,y:e.y};
  var dx = (startPoint.x - endPoint.x)/scale;
  var dy = (startPoint.y - endPoint.y)/scale;
  var movedViewBox = {x:viewBox.x+dx,y:viewBox.y+dy,w:viewBox.w,h:viewBox.h};
  svgImage.setAttribute('viewBox', `${movedViewBox.x} ${movedViewBox.y} ${movedViewBox.w} ${movedViewBox.h}`);
   }
}

svgContainer.onmouseup = function(e){
   if (isPanning){ 
  endPoint = {x:e.x,y:e.y};
  var dx = (startPoint.x - endPoint.x)/scale;
  var dy = (startPoint.y - endPoint.y)/scale;
  viewBox = {x:viewBox.x+dx,y:viewBox.y+dy,w:viewBox.w,h:viewBox.h};
  svgImage.setAttribute('viewBox', `${viewBox.x} ${viewBox.y} ${viewBox.w} ${viewBox.h}`);
  isPanning = false;
   }
}

svgContainer.onmouseleave = function(e){
 isPanning = false;
}
```

```xml
<span id="zoomValue">1</span>
<div id="svgContainer">
<svg id="svgImage" height="964" width="767">
    <g  class="vx-group vx-tree" transform="translate(20, 70)">
        <g class="vx-group" transform="translate(0, 70)">
            <g class="vx-group" transform="translate(0, 0)">
                <path class="vx-link-vertical" d="M451.5,0C451.5,233.5,451.5,233.5,451.5,467" percent="0.5" stroke="#f7f7f3" stroke-width="1" stroke-opacity="0.2" fill="none"></path>
            </g>
            <g class="vx-group" transform="translate(0, 0)">
                <g class="vx-group" transform="translate(451.5, 0)" opacity="1">
                    <g class="vx-group node__container" transform="translate(0, 0)">
                        <svg class="" x="0" y="0" style="overflow: visible;">
                            <polygon points="25.98076211353316,-14.999999999999998 25.98076211353316,14.999999999999998 1.83697019872103e-15,30 -25.98076211353316,14.999999999999998 -25.980762113533157,-15.000000000000004 -5.510910596163089e-15,-30" class="node__hexagon"></polygon>
                        </svg>
                        <g class="vx-group node__business-unit" transform="translate(0, 0)">
                            <use xlink:href="#icon-BusinessUnit"></use>
                        </g>
                        <g class="hierarchy-label__container" transform="translate(0, -40)">
                           <path class="" d="
                              M 0.0078125, 5.15625
                              L 34.64882865137755,25.156249999999996 
                              M -0.9921875, 5.15625 
                              L -34.63320365137754,25.156249999999996
                              H -65.8515625 
                              a8,8 0 0 1 -8,-8  
                              V -47.15625 
                              a8,8 0 0 1 8,-8 H 65.8515625 a8,8 0 0 1 8,8 
                              L 73.8515625, 17.156249999999996  
                              a8,8 0 0 1 -8,8 
                              L 34.64882865137755, 25.156249999999996 
                              Z 
                             "></path>
     			          <svg x="0" y="0" style="overflow: visible;">
     			              <text class="hierarchy-label__item__name" width="150" y="-25" x="0" text-anchor="middle" style="pointer-events: none;">
     			                  <tspan x="0" dy="0em">Finance</tspan>
     			              </text>
     			          </svg>
             			  <svg x="0" y="0" style="overflow: visible;">
             			      <text class="hierarchy-label__item__type" width="150" y="-5" x="0" text-anchor="middle" style="pointer-events: none;">
             			          <tspan x="0" dy="0.71em">Business Unit</tspan>
             			      </text>
             			  </svg>
                       </g>
                   </g>
               </g>
           </g>
       </g>
   </g>
   </svg>
</div>
```