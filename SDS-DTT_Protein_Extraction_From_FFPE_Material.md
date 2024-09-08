### protocol_header
- Protocol: SDS-DTT Protein Extraction From FFPE Material
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC
- Date: 5SEPT2024
- Version: 2
- Approver: ermahe@ucalgary.ca

### authorization
- Requires completion of site specific safety training
- Requires pre-authorization by PI

### hazards
- Xylene, DTT and ethanol are toxic, volatile, flammable, and/or poisonous.
- SDS is a potent solvent
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
- NA

### emergency
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- Contact emergency services and log any injuries

### cleanup
- Benchtop/fumehood surface wipedown with 70% isopropanol

### waste
- Xylene/ethanol should be disposed of in chemical waste container (fume hood)
- Dispose of sharps (blades and slides) in yellow biohazard tubs (NOT biohazard bags)
- Dispose of tips/tubes in biohazard bags or tubs

### maintenance
- NA

### before_starting
- Ensure specimens are accessioned and that sufficient labelled tubes are available
- If required, make 1M Tris stock: Dissolve 121 g Tris base in 800 ml ddH2O; warm to dissolve as required; adjust to desired pH with concentrated HCl (approximately 42 mL HCl is needed to achieve pH 8.0 solution); top up to 1L total volume with ddH2O
- If required, make 10x SDS-Tris Stock: Dissolve 40 g SDS in ~80 mL of 1M Tris solution; warm to dissolve as required; add additional 1M Tris up to 100 mL; store at 4°C
- If required, make 1M DTT Stock: Slowly dissolve 1.55 g of DTT in 10 mL ddH2O, dispense into Eppendorf tubes in 1-mL aliquots, and store in the dark (eg wrapped in foil) at -20°C
- Enter the accession numbers of the specimens in the table below to calculate the required volumes of reagents required

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
<table id="table0">
	<tr><td>Scan/enter the specimen accession numbers:</td><td></tr>
</table>
<table id="table1">
	<tr><td><input type="text" size="10px" id="00"/></td><td><input type="text" size="10px" id="01"/></td><td><input type="text" size="10px" id="02"/></td><td><input type="text" size="10px" id="03"/></td></tr>
	<tr><td><input type="text" size="10px" id="10"/></td><td><input type="text" size="10px" id="11"/></td><td><input type="text" size="10px" id="12"/></td><td><input type="text" size="10px" id="13"/></td></tr>
</table>
<br>
<button type="button" onclick="addRows()">Add Rows</button>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
	<tr><td></td><td></td></tr>
	<tr><td>Working Solution Preparation</td><td></td></tr>
	<tr><td>Volume of required Working Solution Assuming ~10 mg of tissue per sample (uL):</td>
	<td><input readonly type="text" size="10px" id="TotalVol"/></td></tr>
<!--- calculation: --->
	<tr><td>Volume of 10x SDS-Tris Stock Required for Working Solution (uL):</td>
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
<!--- calculation: --->
	<tr><td>Volume of 1M DTT Required for Working Solution (uL):</td>
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
<!--- calculation: --->
	<tr><td>Volume of ddH2O Required for Working Solution (uL):</td>
	<td><input readonly type="text" size="10px" id="calc3"/></td></tr>
</table>
<br>
<button type="button" onclick="calculate()">Calculate</button>
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
	document.getElementById('TotalVol').value = (110 * (count)).toFixed(1);
        document.getElementById('calc1').value = (11 * (count)).toFixed(1);
        document.getElementById('calc2').value = (11 * (count)).toFixed(1);
        document.getElementById('calc3').value = (88 * (count)).toFixed(1);
    }
}
</script>
</body>
</html>
~~~~
### procedures
1. IF CURLS/SCROLLS ARE PROVIDED: Ensure the tube(s) are correctly labelled; move to step 5
2. IF SLIDES ARE PROVIDED:
3. If coverslipped, soak with xylene in a Coplin jar in fume hood for ~4 hours; use gentle traction (applied using forceps or another slide) to remove the coverslip
4. Use fresh blade to scrape off the materials into a labelled 1.5 mL microfuge tube
5. In the fumehood, add 1 ml xylene per labelled tube containing the FFPE tissue materials.
6. Vortex 10 s and incubate 5 min at RT
7. Centrifuge 3 min at 16,000 × g at RT and pipette off the supernatant
8. In the fumehood, add 1 ml xylene per labelled tube containing the FFPE tissue materials.
9. Vortex 10 s and incubate 5 min at RT
10. Centrifuge 3 min at 16,000 × g at RT and pipette off the supernatant
11. In the fumehood, add 1 ml 100 % ethanol per tube
12. Vortex 10 s and incubate 5 min at RT
13. Centrifuge 3 min at 16,000 × g at RT and pipette off the supernatant
14. In the fumehood, add 1 ml 95 % ethanol per tube.
15. Vortex 10 s and incubate 5 min at RT
16. Centrifuge 3 min at 16,000 × g at RT and pipette off the supernatant
17. In the fumehood, add 1 ml 70 % ethanol per tube.
18. Vortex 10 s and incubate 5 min at RT
19. Centrifuge 3 min at 16,000 × g at RT and pipette off the supernatant
20. Spin down, remove all remaining supernatant and let the tube stand open in the hood for 5 min to dry the pellet
21. Add ~100 μL extraction buffer per ~10 mg tissue and gently pipette up & down to dissolve
22. Incubate at 100 °C for 20 min at 500 rpm in the thermomixer
23. Incubate at 60 °C for 2 h at 500 rpm in the thermomixer
24. Centrifuge for 10 min at 16,000 × g, collect the extracted protein supernatant and transfer it to a clean labelled tube
25. Proceed to Qubit protein quantitation; store extracts at −20°C
