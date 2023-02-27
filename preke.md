---
layout: main
permalink: /preke/
---
<script>  
    
    $(function(){
    
     document.getElementById("keywords").value = " "; 
     
     document.getElementById("clear").addEventListener("click", function(){
        document.getElementById('keywords').value = " ";
        document.getElementById('year').value = "all";
        document.getElementById('month').value = "all";
        document.getElementById('keywords').focus();
        onSearch();
     }); 
    
     var myElement = document.getElementById('results');
     if(window.addEventListener) {
        // Normal browsers
        myElement.addEventListener('DOMSubtreeModified', contentChanged, false);
     } else if(window.attachEvent) {
        // IE
        myElement.attachEvent('DOMSubtreeModified', contentChanged);
     }
     onSearch();
    
    }); 
    
    function contentChanged() { 
        totalResults = document.getElementById('results').children.length;
        header = document.getElementById('resultsHeader');
        if(header) header.innerHTML = "Soekresultate(" + totalResults + ")";
    }  
    
    function onSearch(sender){
       
      var inpText = document.getElementById("keywords");
      var searchString = inpText.value;   
      search.search(searchString, applyFilter.bind(this));
      var inputField = document.getElementById('keywords');
      if(inputField.value === "") inputField.value = " ";
    
    };
    
</script>  

## Ons YouTube Kanaal
Teken in op ons YouTube kanaal om toegang te kry na die preke soos hulle beskikbaar gestel word: 
<div class="g-ytsubscribe" data-channelid="UC0ZP4XfiYIW-CgGgnnmV-2Q" data-layout="default" data-count="hidden"></div>
<br/>

## Vorige Preke
Hier kan jy soek na spesifieke preke gebaseer op die text gedeelte en ander sleutelwoorde.
<br/>

<div class="filterContainer">
  <form action="#">
    <div class="row">
      <div class="col">
        <label for="keywords" style="margin-bottom: 0px; padding-bottom: 6px;">Skrifgedeeltes en Sleutelwoorde:</label>
        <input type="text" id="keywords" name="keywords" placeholder="Soek vir sleatelwoorde hier..." oninput="onSearch()">
      </div> 
    </div>
    <div class="row">
      <div class="col">
        <table style="width:100%">
          <tbody>
              <tr>
                <td>
                    <label for="year" style="margin-bottom: 0px; padding-bottom: 6px;">Jaar:</label>
                    <select name="year" id="year" onchange="onSearch()">
                        <option value="all">Alle Jare</option>
                        <option value="2023">2023</option>
                        <option value="2022">2022</option>
                        <option value="2021">2021</option>
                        <option value="2020">2020</option>
                        <option value="2019">2019</option>
                        <option value="2018">2018</option>
                    </select></td>
                <td style="padding-left: 16px;">
                    <label for="month" style="margin-bottom: 0px; padding-bottom: 6px;">Maand:</label>
                    <select name="month" id="month" onchange="onSearch()">
                      <option value="all">Alle Maande</option>
                      <option value="01">Januarie</option>
                      <option value="02">Februarie</option>
                      <option value="03">Maart</option>
                      <option value="04">April</option>
                      <option value="05">Mei</option>
                      <option value="06">Junie</option>
                      <option value="07">Julie</option>
                      <option value="08">Augustus</option>
                      <option value="09">September</option>
                      <option value="10">Oktober</option>
                      <option value="11">November</option>
                      <option value="12">Desember</option>
                    </select>
                  </td>  
                </tr> 
            </tbody>
          </table> 
      </div>
    </div> 
    <div class="row"> 
      <div class="col"> 
          <button id="clear" type="button" class="btn btn-outline-danger" style="margin-top: 16px;">Kanselleer</button>
      </div>
    </div>
  </form>
</div>
<br/>
<h3 id="resultsHeader">Soekresultate(0)</h3>
<div id="results" class="grid-container"/>
