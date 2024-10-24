
### protocol
- Protocol: RNA Extraction from FFPE (Slides or Scrolls/Curls) or Tissue Transfer Materials (QIAGEN RNeasy)
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC083402
- Version: 1
- Version Date: 14FEB2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Xylene, Ethanol, and Qiagen buffers are toxic, volatile, flammable, and/or poisonous
- Scrape-blades/glass slides may cause sharps injury
- Thermomixer may cause thermal injury

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Fumehood
- Pre-PCR bench

### references
- QIAGEN RNEasy FFPE Handbook: 

### emergency
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries

### cleanup
- Benchtop/fumehood surface wipedown with 70% isopropanol

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag
- Xylene/ethanol should be disposed of in chemical waste container (fumehood)
- QIAGEN reagent/flow through should be disposed of in aqueous chemical waste
- Sharps disposal: use approved biohazard bucket

### maintenance
- Wipe surfaces down with 70% isopropanol
- Do not use isopropanol on instruments

### before_starting
- Ensure that sufficient Xylene, 100% Ethanol, buffer PKD, Proteinase K, DNase I, DNase booster, buffer RBC, buffer RPE and RNase-free (DEPC) water available
- 
- DNase I stock solution (from QIAGEN DNase I kit): Dissolve lyophilized DNase I (1500 Kunitz units) in 550 μl RNase-free water
- DNase 1 stock solution can be kept for 9+ months at -20C 
-  
- Obtain fresh scrape blades (one per specimen)
- Extra 2 mL microfuge tubes, RNeasy columns and elution (specimen collection) tubes are required
- Enter specimen accession numbers below and use the calculator to calculate the required reagent volumes

### calculator
~~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<link rel="stylesheet" href="mahe-lab_style.css">
		<title>Working Solution Calculator</title>
	</head>
<body>
<!---configure reagent prep details here, with calculations based on the table inputs below--->
<table id="table1">
	<tr><td>Scan/enter the specimen accession numbers:</td><td></tr>
	<tr><td><input type="text" size="10px" id="00"/></td><td><input type="text" size="10px" id="01"/></td><td><input type="text" size="10px" id="02"/></td><td><input type="text" size="10px" id="03"/></td></tr>
	<tr><td><input type="text" size="10px" id="10"/></td><td><input type="text" size="10px" id="11"/></td><td><input type="text" size="10px" id="12"/></td><td><input type="text" size="10px" id="13"/></td></tr>
</table>
<br>
<button type="button" class="button" onclick="addRows()">Add Rows</button>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
	<tr><td></td><td></td></tr>
	<tr><td>Volume of Xylene required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
	<tr><td>Volume of 100% Ethanol required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
	<tr><td></td><td></td></tr>
	<tr><td>Proteinase Working Solution:</td><td></td></tr>
	<tr><td>Volume of buffer PKD required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc3"/></td></tr>
	<tr><td>Volume of Proteinase K stock solution required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc4"/></td></tr>
	<tr><td></td><td></td></tr>
	<tr><td>DNase I Working Solution:</td><td></td></tr>
	<tr><td>Volume of DNase booster required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc5"/></td></tr>
	<tr><td>Volume of DNase I stock solution required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc6"/></td></tr>
	<tr><td></td><td></td></tr>
	<tr><td>Volume of buffer RBC required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc7"/></td></tr>
  	<tr><td>Volume of buffer RPE required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc8"/></td></tr>
   	<tr><td>Volume of RNase-free (DEPC) water equired (uL):</td>
	<td><input readonly type="text" size="10px" id="calc9"/></td></tr>
</table>
<br>
<button type="button" class="button" onclick="calculate()">Calculate</button>
<script type='text/javascript'>
function addRows() {
    var table = document.getElementById('table1');
    var trows = table.rows.length;
    var tcols = table.rows[0].cells.length;
    var row = table.insertRow(trows);
    for (var i=0;i<tcols;i++) {
	var txt = document.createElement('input')
	txt.setAttribute('type','text');
	txt.setAttribute('size','10px');
	txt.setAttribute('id',`${trows}${i}`);
	var col = row.insertCell(i);
	col.appendChild(txt);
    }
}	
function calculate() {
    var count = 0;
    var table = document.getElementById('table1');
    var trows = table.rows.length;
    var tcols = table.rows[0].cells.length;
    for (var i=0;i<trows;i++) {
        for (var j=0;j<tcols;j++) {
            var txtcontent = document.getElementById(`${i}${j}`).value;
            if(txtcontent != '') {
                count++;
            }
        }
    }
    //console.log(count)
    if(count>0) {
	document.getElementById('calc1').value = (1100 * (count)).toFixed(1); //xylene
        document.getElementById('calc2').value = (2200 * (count)).toFixed(1); //ethanol
        document.getElementById('calc3').value = (264 * (count)).toFixed(1); //buffer PKD
        document.getElementById('calc4').value = (11 * (count)).toFixed(1); //Proteinase K
        document.getElementById('calc5').value = (27.5 * (count)).toFixed(1); //DNase booster
        document.getElementById('calc6').value = (11 * (count)).toFixed(1); //DNase I
	document.getElementById('calc7').value = (550 * (count)).toFixed(1); //RBC
	document.getElementById('calc8').value = (1100 * (count)).toFixed(1); //RPE
	document.getElementById('calc9').value = (33 * (count)).toFixed(1); //RNAse free water
    }
}
</script>
</body>
</html>
~~~~

### procedures
1. Ensure that specimens are accessioned and that a sufficient number of labels are printed (usually 3 per specimen)
2. IF STARTING WITH CURLS/SCROLLS OR TISSUE TRANSFER MATERIAL: Ensure the tube(s) are correctly labelled; move to step 4
3. IF STARTING WITH SLIDES: If coverslipped, soak with xylene in a Coplin jar in fume hood for ~4 hours; use gentle traction (applied using forceps or another slide) to remove the coverslip; Use a fresh scrape blade to scrape off the materials into a labelled 2.0 mL microfuge tube
4. In the fumehood, add 1 ml xylene per tube
5. Cap, vortex well and incubate 5 min at RT
6. Centrifuge 2 min at 16,000 × g at RT and carefully pipette off the supernatant
7. Add 1000 uL 100% Ethanol
8. Vortex 10 s and incubate 5 min at RT
9. Centrifuge 3 min at 16,000 × g at RT and pipette off the supernatant
10. Let the tube stand open in the hood to dry the pellet
11. Add 250 μl Proteinase working solution, and mix by vortexing
12. Incubate at 56°C for 15 min at 500 rpm in the thermomixer
13. Incubate at 80 °C for 15 min at 500 rpm in the thermomixer
14. Incubate on ice for 3 min
15. Centrifuge for 15 min at 16,000 × g
16. Transfer supernatant to a new labelled microfuge tube
17. Add 35 uL DNase working solution booster buffer & 10 uL DNase 1 stock solution
18. Mix gently by inversion & incubate at RT for 15 minutes
19. Add 500 uL buffer RBC and vortex
20. Add 1000 uL 100% Ethanol & mix well by pipetting up and down. CAREFUL, TUBE WILL BE QUITE FULL!!
21. Prepare an appropriately labelled RNeasy Column (these will come packaged with a 2 mL waste collection tube)
22. Transfer 500 uL of the specimen from step 20 to the column
23. Centrifuge 15 sec at 10,000 × g
24. Discard flow-through in liquid waste
25. Repeat steps 22-24 until all the materials from step 20 are passed through the column
26. Add 500 μl Buffer RPE to the RNeasy spin column
27. Centrifuge for 15 s at 10,000 × g
28. Discard flow-through
29. Repeat steps 26-28 then transfer the column to a new labelle specimen (elution) tube
30. Carefully add 30 uL RNase-free water to the CENTER of the column. Avoid touching the walls/sides of the column with pipette tip
31. Centrifuge for 1 min at full speed to elute the RNA
32. Proceed to RNA quantification
33. Store specimen in -20C freezer
