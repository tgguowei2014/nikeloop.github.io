<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>图片轮播</title>
    <style>
        .image-container {
            text-align: center;
            margin-top: 50px;
        }
        .image-item {
            display: none; /* 默认隐藏所有图片 */
            max-width: 80%;
            height: auto;
            cursor: pointer; /* 显示手型光标提示可点击 */
        }
        .image-item.active {
            display: block; /* 只显示当前激活的图片 */
        }
    </style>
</head>
<body>
    <div class="image-container">
        <!-- 图片列表 -->
        <img src="https://p11-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/573a14cdab39437bb70abaa30be23020.jpg~tplv-a9rns2rl98-24-95-exif:960:960.image?rcl=20251117230853395F06C5840F272ACC77&rk3s=8e244e95&rrcfp=8a172a1a&x-expires=1763996934&x-signature=TYdXWEcyoUpQ4dP47552zkcbDwk%3D" 
             class="image-item active" alt="图片1">
        
        <img src="https://p11-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/ced4e08eaf1e404496bc27e45e8b03d0.jpg~tplv-a9rns2rl98-24-95-exif:960:960.image?rcl=20251117230853395F06C5840F272ACC77&rk3s=8e244e95&rrcfp=8a172a1a&x-expires=1763996934&x-signature=%2Bpdtfyx1aQxCy3X%2FbFJlPXBXYAQ%3D" 
             class="image-item" alt="图片2">
        
        <img src="https://p11-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/784c84fec36445c4a2e1456f6fe171ec.jpg~tplv-a9rns2rl98-24-95-exif:960:960.image?rcl=20251117230853395F06C5840F272ACC77&rk3s=8e244e95&rrcfp=8a172a1a&x-expires=1763996934&x-signature=sCKCHtcF29vhsZgZp06T1HTpQAc%3D" 
             class="image-item" alt="图片3">
    </div>

    <script>
        // 获取所有图片元素
        const images = document.querySelectorAll('.image-item');
        let currentIndex = 0; // 当前显示图片的索引

        // 为每张图片添加点击事件
        images.forEach((img, index) => {
            img.addEventListener('click', () => {
                // 隐藏当前图片
                images[currentIndex].classList.remove('active');
                
                // 计算下一张图片索引（最后一张点击后返回第一张）
                currentIndex = (currentIndex + 1) % images.length;
                
                // 显示下一张图片
                images[currentIndex].classList.add('active');
            });
        });
    </script>
</body>
</html>
