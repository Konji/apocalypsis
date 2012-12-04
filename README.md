// ==UserScript==
// @name        test
// @namespace   test
// @description test
// @include     /^http://apocalypsis.org/strategie*/
// @version     1
// ==/UserScript==


var calcule = function(){

}

var form='<form name="formulaire" style="margin:0px;display:block;background:url(/images/backgrounds/back_black.png);"">\
<p>Capacité offensive : <input name="saisie1" type="text" ></p>\
<p>Nombre d\'unites : <input name="saisie2" type="text" ></p>\
<p>Attaque : <input name="saisie3" type="text" ></p>\
<p>Vitesse : <input name="saisie4" type="text" ></p>\
<input id="boutton" type="button" value="calculer">\
</form>';
document.getElementById('unit_list').innerHTML += form;


document.getElementById('boutton').addEventListener('click', function() {
  var value1 = document.forms["formulaire"].elements["saisie1"].value;
	var value2 = document.forms["formulaire"].elements["saisie2"].value;
	var value3 = document.forms["formulaire"].elements["saisie3"].value;
	var value4 = document.forms["formulaire"].elements["saisie4"].value;
	var result = (value1/5)*value2*value3*(Math.pow(value4,0.55));
	result = Math.round(result);
	document.getElementById('unit_list').innerHTML += '<p>Valeur offensive : '+result+'.';
}, true);