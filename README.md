# CSS-shape-yinyang

这是一个纯 CSS 实现的阴阳八卦图形

[阴阳八卦](http://upload-images.jianshu.io/upload_images/9617841-58e3a8a32a7290ac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 方案1：
HTML：

    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <title>Yin Yang</title>
        <link rel="stylesheet" href="./css/style.css">
    </head>
    <body>
    <div class="yin-yang">
        <div class='white-inner'></div>
        <div class='black-inner'></div>
    </div>
    <p>乾为一，兑为二，离为三，震为四，巽为五，坎为六，艮为七，坤为八</p>
    </body>
    </html>

css：

    body{
        background-color: #aaa;
    }
    .yin-yang{
        width: 96px;
        height: 48px;
        background: #fff;
        border-color: #000;
        border-style: solid;
        border-width: 0 0 50px 0;
        border-radius: 50%;
        position: relative;
        margin:100px auto 40px;
        animation: spin 4s infinite linear;
    }
    .white-inner{
        width:12px;
        height:12px;
        background:#fff;
        border-radius:50%;
        border:18px solid #000;
        position:absolute;
        top:50%;
        left:0;
    }
    .black-inner{
        width:12px;
        height:12px;
        background:#000;
        border-radius:50%;
        border:18px solid #fff;
        position:absolute;
        top:50%;
        left:50%;
    }
    @keyframes spin{
        0%{ transform: rotate(0deg); }
        100%{ transform: rotate(360deg); }
    }
    p{
        color: #fff;
        text-align: center;
    }

# 方案2：
HTML：

    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <title>Yin Yang</title>
        <link rel="stylesheet" href="./css/style.css">
    </head>
    <body>
        <div class="yin-yang"></div>
        <p>乾为一，兑为二，离为三，震为四，巽为五，坎为六，艮为七，坤为八</p>
    </body>
    </html>

css：

    body{
        background-color: #aaa;
    }
    #yin-yang {
        width: 96px;
        height: 48px;
        background: #fff;
        border-color: #000;
        border-style: solid;
        border-width:0 0 50px 0;
        border-radius: 100%;
        position: relative;
    margin:100px auto 40px;
        animation: spin 4s infinite linear;
    }

    #yin-yang:before {
        content: "";
        position: absolute;
        top: 50%;
        left: 0;
        background: #fff;
        border: 18px solid #000;
        border-radius: 100%;
        width: 12px;
        height: 12px;
    }

    #yin-yang:after {
        content: "";
        position: absolute;
        top: 50%;
        left: 50%;
        background: #000;
        border: 18px solid #fff;
        border-radius:100%;
        width: 12px;
        height: 12px;
    }
    @keyframes spin{
        0%{ transform: rotate(0deg); }
        100%{ transform: rotate(360deg); }
    }
    p{
        color: #fff;
        text-align: center;
    }

# 方案3
HTML：

    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <title>Yin Yang</title>
        <link rel="stylesheet" href="./css/style.css">
    </head>
    <body>
        <div id="yin-yang">

        </div>
        <p>乾为一，兑为二，离为三，震为四，巽为五，坎为六，艮为七，坤为八</p>
    </body>
    </html>

css：

    body{
        background-color: #aaa;
    }
    #yin-yang{
        width: 200px;
        height: 200px;
        background: linear-gradient(to bottom, #ffffff 0%,#ffffff 50%,#000000 51%,#000000 100%);
        border-color: #000;
        border-radius: 50%;
        position: relative;
        margin:100px auto 40px;
        animation: spin 4s infinite linear;
    }
    #yin-yang::before{
        content: '';
        width:100px;
        height:100px;
        background: radial-gradient(ellipse at center, #ffffff 0%,#ffffff 20%,#000000 20%,#000000 100%); 
    border-radius: 50%;
        position:absolute;
        top:25%;
        left:0;
    }
    #yin-yang::after{
        content: '';
        width:100px;
        height:100px;
        background: radial-gradient(ellipse at center, #000000 0%,#000000 20%,#ffffff 20%,#ffffff 100%); 
    border-radius: 50%;
        position:absolute;
        top:25%;
        right:0;
    }
    @keyframes spin{
        0%{ transform: rotate(0deg); }
        100%{ transform: rotate(360deg); }
    }
    p{
        color: #fff;
        text-align: center;
    }
