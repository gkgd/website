---
layout: main
permalink: /preke/
---
<script>  
    
    $(function(){
    
     document.getElementById("keywords").value = " "; 
     
     document.getElementById("clear").addEventListener("click", function(){
        document.getElementById('keywords').value = " ";
        document.getElementById('boek').value = "blank";
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
      
      var selBoek = document.getElementById("boek");
      var inpText = document.getElementById("keywords");
      var searchString = inpText.value;
      if(selBoek.value !== "blank"){
        if(searchString === "" || searchString === " "){
            searchString = selBoek.value
        }else{
            searchString += " " + selBoek.value
        }
      }
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
      <div class="col-25">
        <label for="boek">Skrifgedeelte</label>
      </div>
      <div class="col-75">
        <select id="boek" name="boek" onchange="onSearch()">
          <option value="blank"></option>
          <option value="Genesis">Genesis</option>
          <option value="Eksodus">Eksodus</option>
          <option value="Levitikus">Levitikus</option>
          <option value="Numeri">Numeri</option>
          <option value="Deuteronomium">Deuteronomium</option>
          <option value="Josua">Josua</option>
          <option value="Rigters">Rigters</option>
          <option value="Rut">Rut</option>
          <option value="1 Samuel">1 Samuel</option>
          <option value="2 Samuel">2 Samuel</option>
          <option value="1 Konings">1 Konings</option>
          <option value="2 Konings">2 Konings</option>
          <option value="1 Kronieke">1 Kronieke</option>
          <option value="2 Kronieke">2 Kronieke</option>
          <option value="Esra">Esra</option>
          <option value="Nehemia">Nehemia</option>
          <option value="Ester">Ester</option>
          <option value="Job">Job</option>
          <option value="Psalms">Psalms</option>
          <option value="Spreuke van Salomo">Spreuke van Salomo</option>
          <option value="Prediker">Prediker</option>
          <option value="Hooglied van Salomo">Hooglied van Salomo</option>
          <option value="Jesaja">Jesaja</option>
          <option value="Jeremia">Jeremia</option>
          <option value="Klaagliedere van Jeremia">Klaagliedere van Jeremia</option>
          <option value="Esegi??l">Esegi??l</option>
          <option value="Dani??l">Dani??l</option>
          <option value="Hosea">Hosea</option>
          <option value="Jo??l">Jo??l</option>
          <option value="Amos">Amos</option>
          <option value="Obadja">Obadja</option>
          <option value="Jona">Jona</option>
          <option value="Miga">Miga</option>
          <option value="Nahum">Nahum</option>
          <option value="Habakuk">Habakuk</option>
          <option value="Sefanja">Sefanja</option>
          <option value="Haggai">Haggai</option>
          <option value="Sagaria">Sagaria</option>
          <option value="Maleagi">Maleagi</option>
          <option value="Matteus">Matteus</option>
          <option value="Markus">Markus</option>
          <option value="Lukas">Lukas</option>
          <option value="Johannes">Johannes</option>
          <option value="Die handelinge van die apostels">Die handelinge van die apostels</option>
          <option value="Romeine">Romeine</option>
          <option value="1 Korinti??rs ">1 Korinti??rs </option>
          <option value="2 Korinti??rs">2 Korinti??rs</option>
          <option value="Galasi??rs">Galasi??rs</option>
          <option value="Effesi??rs">Effesi??rs</option>
          <option value="Filippense">Filippense</option>
          <option value="Kolossense">Kolossense</option>
          <option value="1 Tessalonisense">1 Tessalonisense</option>
          <option value="2 Tessalonisense">2 Tessalonisense</option>
          <option value="1 Timoteus">1 Timoteus</option>
          <option value="2 Timoteus">2 Timoteus</option>
          <option value="Titus ">Titus </option>
          <option value="Filemon">Filemon</option>
          <option value="Hebre??rs">Hebre??rs</option>
          <option value="Jakobus">Jakobus</option>
          <option value="1 Petrus">1 Petrus</option>
          <option value="2 Petrus">2 Petrus</option>
          <option value="1 Johannes">1 Johannes</option>
          <option value="2 Johannes">2 Johannes</option>
          <option value="3 Johannes">3 Johannes</option>
          <option value="Judas">Judas</option>
          <option value="Die openbaring">Die openbaring</option>
        </select>
      </div>  
    </div> 
    <div class="row">
      <div class="col-25">
        <label for="keywords">Sleutelwoorde</label>
      </div>
      <div class="col-75">
        <input type="text" id="keywords" name="keywords" placeholder="Soek vir sleatelwoorde hier..." oninput="onSearch()">
      </div>
    </div>
    <div class="row">
      <div class="col-25">
        &nbsp;
      </div>
      <div class="col-75"> 
          <button id="clear" type="button" class="btn btn-outline-danger">Kanselleer</button>
      </div>
    </div>
  </form>
</div>
<br/>
<h3 id="resultsHeader">Soekresultate(0)</h3>
<div id="results" class="grid-container"/>
