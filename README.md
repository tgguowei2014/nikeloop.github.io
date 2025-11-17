<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>全屏图片切换</title>
  <style>
    /* 清除所有默认样式和滚动条 */
    * {
      margin: 0;
      padding: 0;
      overflow: hidden;
    }
    
    body, html {
      width: 100%;
      height: 100%;
    }
    
    /* 图片容器占满整个屏幕 */
    .image-container {
      width: 100vw;
      height: 100vh;
      position: relative;
    }
    
    /* 单张图片样式 */
    .image-slide {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      opacity: 0;
      transition: opacity 0.5s ease-in-out;
      pointer-events: none;
    }
    
    /* 显示中的图片 */
    .image-slide.active {
      opacity: 1;
      pointer-events: auto;
    }
    
    /* 图片自适应全屏 */
    .image-slide img {
      width: 100%;
      height: 100%;
      object-fit: cover; /* 保持比例并铺满屏幕 */
      cursor: pointer;
      transition: transform 0.3s ease;
    }
    
    /* 悬停效果 */
    .image-slide img:hover {
      transform: scale(1.02);
    }
  </style>
</head>
<body>
  <div class="image-container">
    <!-- 图片1 -->
    <div class="image-slide active">
      <img src="https://p11-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/573a14cdab39437bb70abaa30be23020.jpg~tplv-a9rns2rl98-24-95-exif:960:960.image?rcl=20251117230853395F06C5840F272ACC77&rk3s=8e244e95&rrcfp=8a172a1a&x-expires=1763996934&x-signature=TYdXWEcyoUpQ4dP47552zkcbDwk%3D" 
           alt="图片1">
    </div>
    
    <!-- 图片2 -->
    <div class="image-slide">
      <img src="https://p11-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/ced4e08eaf1e404496bc27e45e8b03d0.jpg~tplv-a9rns2rl98-24-95-exif:960:960.image?rcl=20251117230853395F06C5840F272ACC77&rk3s=8e244e95&rrcfp=8a172a1a&x-expires=1763996934&x-signature=%2Bpdtfyx1aQxCy3X%2FbFJlPXBXYAQ%3D" 
           alt="图片2">
    </div>
    
    <!-- 图片3 -->
    <div class="image-slide">
      <img src="https://p11-flow-imagex-download-sign.byteimg.com/tos-cn-i-a9rns2rl98/784c84fec36445c4a2e1456f6fe171ec.jpg~tplv-a9rns2rl98-24-95-exif:960:960.image?rcl=20251117230853395F06C5840F272ACC77&rk3s=8e244e95&rrcfp=8a172a1a&x-expires=1763996934&x-signature=sCKCHtcF29vhsZgZp06T1HTpQAc%3D" 
           alt="图片3">
    </div>
  </div>

  <script>
    // 获取所有图片元素
    const slides = document.querySelectorAll('.image-slide');
    const images = document.querySelectorAll('.image-slide img');
    let currentIndex = 0;
    const totalImages = slides.length;
    
    // 切换到下一张图片
    function nextSlide() {
      // 移除当前图片的active类
      slides[currentIndex].classList.remove('active');
      
      // 计算下一张索引，最后一张返回0
      currentIndex = (currentIndex + 1) % totalImages;
      
      // 给下一张图片添加active类
      slides[currentIndex].classList.add('active');
    }
    
    // 给所有图片添加点击事件
    images.forEach(img => {
      img.addEventListener('click', nextSlide);
    });
  </script>
</body>
</html>
