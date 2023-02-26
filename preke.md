---
layout: main
permalink: /preke/
---
<script>  
    
    $(function(){
    
     document.getElementById("keywords").value = " "; 
     
     document.getElementById("clear").addEventListener("click", function(){
        document.getElementById('keywords').value = " "; 
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
      search.search(searchString);
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
          <button id="clear" type="button" class="btn btn-outline-danger" style="margin-top: 16px;">Kanselleer</button>
      </div>
    </div>
  </form>
</div>
<br/>
<h3 id="resultsHeader">Soekresultate(0)</h3>
<div id="results" class="grid-container"/>
