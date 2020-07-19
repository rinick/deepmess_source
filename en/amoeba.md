---
layout: page_en
title:  "Rick's Game of Amoeba"
---

**Rick\'s Game of Amoeba** is a <a href="https://en.wikipedia.org/wiki/Cellular_automaton" target="_blank">Cellular Automaton</a> based on <a href="https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life" target="_blank">Game of Life</a>. It emulates Amoebas growing and devouring each other.


<style type="text/css">
  span.cell{
    display:inline-block;
    width:8px;
    height:8px;
    border:1px solid #000;
  }
  .black.cell{
    background: black;
  }

  .membrane.cell{
    background:#91d5ff;
  }
  .plasm.cell{
    background: #003a8c;
  }
  .core.cell{
    background: #096dd9;
  }

  .membrane1.cell{
    background:#ffa39e;
  }
  .plasm1.cell{
    background: #820014;
  }
  .core1.cell{
    background: #cf1322;
  }

  .virus.cell{
    background: #ff00ff;
  }
  .wall.cell{
    background: #ffffff;
  }

</style>

## 基本规则

<span class='cell black'></span> Empty Space<br/>
<span class='cell plasm'></span> / <span class='cell plasm1'></span> Plasm: Slowly grows.<br/>
<span class='cell membrane'></span> / <span class='cell membrane1'></span> Membrane：Quickly grows around plasm, can survive without plasm.<br/>
<span class='cell core'></span> / <span class='cell core1'></span> Core: Can only survive around plasm，can also destroy and rebuild membrane<br/>
<span class='cell wall'></span> Wall, block the growth of amoeba. the rules around wall are modified to optimize circuit emulation.<br/>
<span class='cell virus'></span> Virus, Occurered at intence battle area of blue and red, converts all amoebas around it into virus.<br/>
<br/>
Basic Rules: Count different types of neighbors in 8 adjacent cells and..<br/>
<span class='cell black'></span> / <span class='cell plasm'></span> ⇒ <span class='cell core'></span> when <span class='cell core'></span> = 3 <br/>
<span class='cell plasm'></span> ⇒ <span class='cell black'></span> when <span class='cell core'></span> > 3 | <span class='cell plasm'></span> = 0<br/>
<span class='cell core'></span> ⇒ <span class='cell black'></span> when <span class='cell plasm'></span> = 0<br/>
<span class='cell membrane'></span> ⇒ <span class='cell black'></span> when <span class='cell core'></span> > 1<br/>
<span class='cell black'></span> ⇒ <span class='cell membrane'></span> when <span class='cell membrane'></span> > 0 &amp; <span class='cell plasm'></span> > 0 &amp; <span class='cell core'></span> = 0<br/>
<span class='cell black'></span> ⇒ <span class='cell plasm'></span> when <span class='cell plasm'></span> = 3 | (3 > <span class='cell core'></span> > 0 &amp; <span class='cell plasm'></span> > 0)<br/>

------
Open the full web app to access more features（ Save / Load / Modify ）: 

<a href="/amoeba/#en" target="_blank">deepmess.com/amoeba/</a>

<iframe src="/amoeba/#en"  frameBorder="0" style="width:100%;height:752px">
<iframe>