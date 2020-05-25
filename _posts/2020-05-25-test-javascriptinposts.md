---
author: Lars
layout: single
title:  "Test Javascript post"
---

Check if Javascript is working:

<div style="background-image: linear-gradient(#092f4d90, #092f4d90),url(https://www.kbv.de/images/contentbilder_m/header_corona_742.jpg); color: white;font-family: sans-serif;padding:1em;width: 350px;"><h3>Zi Frühindikatoren für Deutschland</h3><p>Stand: <span id="ZICOVIDFI_Stand"></span> 0:00 Uhr</p><p>R-Wert: <strong><span id="ZICOVIDFI_RWert"></span></strong><br>Neue Fälle pro Tag: <strong><span id="ZICOVIDFI_FaelleproTag"></span></strong><br>Vorwarnzeit: <strong><span id="ZICOVIDFI_Vorwarnzeit"></span> Tage</strong><br></p><p><span>Weitere Informationen finden Sie <a style="color:white;font-style: normal;"href="https://zidatalab.github.io/covid19dashboard/Start"><strong>hier<strong></a></span></p></div>

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
