# 项目简介
arcgis api for flex 中或者说 Flex Viewer 中可以设置一个Graphic的symbol为[Red_glow.swf](https://github.com/Esri/arcgis-viewer-flex/blob/develop/src/assets/images/Red_glow.swf)。[Red_glow.swf](https://github.com/Esri/arcgis-viewer-flex/blob/develop/src/assets/images/Red_glow.swf)是一个闪烁的flash，可以在graphicLayer/featureLayer上形成闪烁强调效果。  

本项目实现了在arcgis api for javascript上同样的效果，采用了CSS3 svg animation。 只支持chrome、edge浏览器、Android 7.0（safari理论上应该支持），不支持IE（IE11也不行，主要是不支持svg动画）  
主要代码摘录如下，适用于SimpleMark
```CSS
#mapDiv_graphics_layer circle {
    /*width: 40px;
    height: 40px;
    margin: 100px auto;*/
    background-color: #333;

    border-radius: 100%;
    -webkit-animation: sk-scaleout 1.0s infinite  linear/*ease-in-out*/;
    animation: sk-scaleout 1.0s infinite  linear/*ease-in-out*/;
}

@-webkit-keyframes sk-scaleout {
    0% {
        -webkit-transform: scale(1.0);
        -webkit-transform-origin: 50% 50%;
    }
    100% {
        -webkit-transform: scale(2.0);
        -webkit-transform-origin: 50% 50%;
        opacity: 0;
    }
}

@keyframes sk-scannleout {
    0% {
        transform: scale(1.0);
        transform-origin: 50% 50%;
    }
    100% {
        transform: scale(2.0);
        transform-origin: 50% 50%;                
        opacity: 0;
    }
}
```