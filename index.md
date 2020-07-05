---
layout: page
title:  "Rinick's Deep Mess"
---

---
<script>
(()=>{
  let lan = window.localStorage.language;
  if (lan) {
      if (lan === 'en') {
        window.location.replace("/en/");
      }
  } else {
    let hasZh = window.navigator.language.startsWith('zh');
    let hasOther = false;
    if (!hasZh) {
      for (let str of window.navigator.languages) {
        if (str.startsWith('zh')) {
          hasZh = true;
        } else if (!str.startsWith('en')) {
          hasOther = true;
        }
      }
      if (!hasZh || hasOther) {
        window.location.replace("/en/");
      }
    }
  }
})();
</script>

| ------------- | ------------- | ------------- |
| [![](images/icon/namerena.png)](/zh/namerena/) | [名字竞技场](/zh/namerena/) <br /> 基于文本的对战游戏，战斗的过程由输入的名字决定，固定的输入有固定的对战结果 |
| [![](images/icon/hashdown.png)](/zh/hashdown/) | [Hashdown](/zh/hashdown/) <br /> 文本编码和压缩的工具，可以在有限的字符内储存更多的文本信息 |
| [![](images/icon/virus.png)](/zh/virus.html) | [Virus细胞自动机](/zh/virus.html) <br /> 基于GLSL的4状态细胞自动机 |
