
<style>
.language-container {
  position: relative;
  overflow: hidden;
  transition: height 0.3s ease-in-out;
}

.language-section {
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.3s ease-in-out;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  visibility: hidden;  /* 使用visibility替代display */
  pointer-events: none;  /* 禁用未激活内容的交互 */
}

.language-section.active {
  opacity: 1;
  transform: translateY(0);
  position: relative;
  visibility: visible;
  pointer-events: auto;
}
/* 禁用全局的 outline 和 text-decoration */
a, a:focus, a:active, a:focus-visible {
  outline: none !important;
  text-decoration: none !important;
  border: none !important;
  box-shadow: none !important;
}

</style>


<div class="language-container show-zh">

  
  <div id="zh-section" class="language-section active">

<br/> 

# 🌱 关于我

## 👋 你好, 我是 `@虹希`、`@Hongxiovo`

---
### 🎯 我的身份

✍️ 一名中国[🇨🇳]**<span  style="color:#6b66cc; "> 苦逼打工人 </span>**  
🍻 一名普通的**BiliBili UP主**   
🛠️ **Minecraft 玩家**   

---
### 🚀 目前重心

⚡ **正在学:** C++ | UE<br>
📚 **计划学:** 暂无(苦逼打工人哪来那么多时间安排)

---
### ❤️ 我的兴趣

🌐 **语言:** 日本语<br>
🎮 **游戏:** Minecraft<br>
🤖 **技术宅:** DIY硬件项目 | 服务器




---
### 🌐 使用语言
- [🇨🇳] **中文**
- [🇯🇵] 日语 




---

  </div>
  
  <div id="jp-section" class="language-section">
    
<br/>     


<script>
function switchLanguage(lang) {
    const container = document.querySelector('.language-container');
    const sections = container.querySelectorAll('.language-section');
    const newActive = document.getElementById(`${lang}-section`);
    
    if (!newActive) return;

    // 获取当前激活的部分
    const currentActive = container.querySelector('.language-section.active');
    
    if (currentActive) {
        // 淡出当前内容
        currentActive.style.opacity = '0';
        currentActive.style.transform = 'translateY(20px)';
        
        // 等待淡出动画完成后再切换
        setTimeout(() => {
            currentActive.classList.remove('active');
            
            // 准备新内容
            newActive.style.opacity = '0';
            newActive.style.transform = 'translateY(20px)';
            newActive.classList.add('active');
            
            // 触发重排以启动动画
            void newActive.offsetWidth;
            
            // 淡入新内容
            newActive.style.opacity = '1';
            newActive.style.transform = 'translateY(0)';
            
            // 调整容器高度
            container.style.height = `${newActive.scrollHeight}px`;
            
            setTimeout(() => {
                container.style.height = 'auto';
            }, 300);
        }, 300);
    } else {
        // 首次加载直接显示
        newActive.classList.add('active');
        newActive.style.opacity = '1';
        newActive.style.transform = 'translateY(0)';
    }
}

// 页面加载时默认显示英文
document.addEventListener('DOMContentLoaded', function() {
    switchLanguage('zh');
});
</script>