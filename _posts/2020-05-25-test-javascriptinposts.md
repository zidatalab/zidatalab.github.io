---
author: Lars
layout: single
title:  "Test Javascript post"
---

# Check if Javascript is working

**Markdown**

*Zi Frühindikatoren für Deutschland Stand: <span id="ZICOVIDFI_Stand"></span> 0:00 Uhr*

- R-Wert: **<span id="ZICOVIDFI_RWert"></span>**
- Neue Fälle pro Tag: **<span id="ZICOVIDFI_FaelleproTag"></span>**
- Vorwarnzeit: **<span id="ZICOVIDFI_Vorwarnzeit">**
  
Weitere Informationen finden Sie [hier](https://zidatalab.github.io/covid19dashboard/Start)


<script>
var today = new Date();
var dd = String(today.getDate()).padStart(2, '0');
var mm = String(today.getMonth() + 1).padStart(2, '0'); //January is 0!
var yyyy = today.getFullYear();
today = dd+'.'+mm + '.' + yyyy;
document.getElementById("ZICOVIDFI_Stand").innerHTML=today;

var xmlhttp = new XMLHttpRequest();
xmlhttp.onreadystatechange = function() {
  if (this.readyState == 4 && this.status == 200) {
    var myObj = JSON.parse(this.responseText);
    document.getElementById("ZICOVIDFI_RWert").innerHTML = myObj[0].Wert;
    document.getElementById("ZICOVIDFI_FaelleproTag").innerHTML = myObj[1].Wert;
    document.getElementById("ZICOVIDFI_Vorwarnzeit").innerHTML = myObj[2].Wert;
  }
};
xmlhttp.open("GET", "https://raw.githubusercontent.com/zidatalab/covid19dashboard/master/data/frueindikatoren.json", true);
xmlhttp.send();
</script>
