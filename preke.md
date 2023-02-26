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
        document.getElementById('month').value = "month";
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
    
    function applyFilter(element){
        
        var filterYear = false;
        var filterMonth = false;
    
        var year = document.getElementById('year').value
        if(year !== undefined || year !== "all") filterYear = true;
 
        var month = document.getElementById('month').value
        if(month !== undefined || month !== "all") filterMonth = true;
    
        if(filterYear && !filterMonth) return element.year === document.getElementById('year').value;
        else if(!filterYear && filterMonth) return element.month === document.getElementById('month').value 
        else if(filterYear && filterMonth) return element.year === document.getElementById('year').value && element.month === document.getElementById('month').value
        else return true;
    }
    
    function onSearch(sender){
      
      var selYear = document.getElementById("year");
      var selMonth = document.getElementById("month");
      var inpText = document.getElementById("keywords");
      var searchString = inpText.value; 
      
      if(selYear.value !== "all"){
        if(searchString === "" || searchString === " "){
            searchString = selYear.value
        }else{
            searchString += " " + selYear.value
        }
      }
    
      if(selMonth.value !== "all"){
        if(searchString === "" || searchString === " "){
            searchString = selMonth.value
        }else{
            searchString += " " + selMonth.value
        }
      }
    
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
                        <option value="23">2023</option>
                        <option value="22">2022</option>
                        <option value="21">2021</option>
                        <option value="20">2020</option>
                        <option value="19">2019</option>
                        <option value="18">2018</option>
                    </select></td>
                <td style="padding-left: 16px;">
                    <label for="month" style="margin-bottom: 0px; padding-bottom: 6px;">Maand:</label>
                    <select name="month" id="month" onchange="onSearch()">
                      <option value="all">Alle Maande</option>
                      <option value="Jan">Januarie</option>
                      <option value="Feb">Februarie</option>
                      <option value="Mar">Maart</option>
                      <option value="Apr">April</option>
                      <option value="May">Mei</option>
                      <option value="Jun">Junie</option>
                      <option value="Jul">Julie</option>
                      <option value="Aug">Augustus</option>
                      <option value="Sep">September</option>
                      <option value="Oct">Oktober</option>
                      <option value="Nov">November</option>
                      <option value="Dec">Desember</option>
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
