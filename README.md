<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>图片轮播切换</title>
    <style>
        body {
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: #f0f0f0;
        }
        .image-container {
            position: relative;
        }
        img {
            max-width: 100%;
            max-height: 80vh;
            border: 5px solid white;
            box-shadow: 0 0 15px rgba(0,0,0,0.2);
            cursor: pointer;
            transition: transform 0.3s ease;
        }
        img:hover {
            transform: scale(1.02);
        }
        .info {
            position: fixed;
            bottom: 20px;
            color: #666;
            font-family: Arial, sans-serif;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <div class="image-container">
        <!-- 图片容器 -->
        <img id="currentImage" src="" alt="轮播图片">
    </div>
    <div class="info">点击图片切换到下一张</div>

    <script>
        // 图片URL列表
        const images = [
            "https://p11-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/573a14cdab39437bb70abaa30be23020.jpg~tplv-a9rns2rl98-24-95-exif:960:960.image?rcl=20251117230853395F06C5840F272ACC77&rk3s=8e244e95&rrcfp=8a172a1a&x-expires=1763996934&x-signature=TYdXWEcyoUpQ4dP47552zkcbDwk%3D",
            "https://p11-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/ced4e08eaf1e404496bc27e45e8b03d0.jpg~tplv-a9rns2rl98-24-95-exif:960:960.image?rcl=20251117230853395F06C5840F272ACC77&rk3s=8e244e95&rrcfp=8a172a1a&x-expires=1763996934&x-signature=%2Bpdtfyx1aQxCy3X%2FbFJlPXBXYAQ%3D",
            "https://p11-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/784c84fec36445c4a2e1456f6fe171ec.jpg~tplv-a9rns2rl98-24-95-exif:960:960.image?rcl=20251117230853395F06C5840F272ACC77&rk3s=8e244e95&rrcfp=8a172a1a&x-expires=1763996934&x-signature=sCKCHtcF29vhsZgZp06T1HTpQAc%3D"
        ];
        
        // 当前显示的图片索引
        let currentIndex = 0;
        const imageElement = document.getElementById('currentImage');

        // 初始化显示第一张图片
        function showCurrentImage() {
            imageElement.src = images[currentIndex];
        }

        // 切换到下一张图片
        function nextImage() {
            currentIndex = (currentIndex + 1) % images.length;
            showCurrentImage();
        }

        // 绑定点击事件
        imageElement.addEventListener('click', nextImage);

        // 初始化
        showCurrentImage();
    </script>
</body>
</html>
