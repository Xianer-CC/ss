<!DOCTYPE html>  
<html>  
<head>  
    <title>一键复制示例（Vue.js版）</title>  
    <script src="https://cdn.jsdelivr.net/npm/vue@2"></script>  
</head>  
<body>  
  
<div id="app">  
    <p>点击下面的按钮复制文本 "#无所畏惧777"。</p>  
    <p>{{ copyStatus }}</p> <!-- 使用 Vue 的数据绑定来显示状态 -->  
    <button @click="copyText">复制文本</button>  
</div>  
  
<script>  
new Vue({  
    el: '#app',  
    data: {  
        copyStatus: '' // 用于存储复制状态的数据  
    },  
    methods: {  
        copyText() {  
            var copyText = document.createElement("textarea");  
            copyText.value = "#无所畏惧777";  
            document.body.appendChild(copyText);  
            copyText.select();  
            document.execCommand("copy");  
            document.body.removeChild(copyText);  
  
            // 使用 Vue 的数据绑定来更新状态  
            this.copyStatus = '已复制！';  
  
            // 设置一个短暂的提示后消失  
            setTimeout(() => {  
                this.copyStatus = '';  
            }, 2000);  
        }  
    }  
});  
</script>  
  
</body>  
</html>
