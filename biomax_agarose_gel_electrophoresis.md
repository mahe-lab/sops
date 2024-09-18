
### protocol
- Protocol: BioMax Agarose Gel Electrophoresis
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC083402
- Version: 2
- Version Date: 7MAY2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Ethidium bromide is mutagenic & carcinogenic. See SDS
- Care must be taken to avoid electric shock when performing electrophoresis

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Make solutions in fumehood, as required
- Post-PCR Bench

### references
- See BioMax Manual: https://github.com/mahe-lab/sops/tree/main/MAHELAB_SOP_Assets/BioMax_QS710_Manual.pdf

### emergency
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries if required

### cleanup
- Wipe down work surfaces with 70% isopropanol
- NOTE: Do not use isopropanol on instruments

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag/tub

### maintenance
- Rinse electrophoresis equipment components with distilled water after use.
- Do not use universal cleaner or other detergents on gel apparatus (this may cause damage).

### before_starting
- If required, make 50xTAE stock:
- Prepare 0.5 M EDTA: 93.05 g of EDTA disodium salt (MW=372.24 g/mol); dissolve in 400 mL ddH2O and adjust the pH to 8; top up to 500 mL with ddH2O
- Weigh out 242 g of Tris-base (MW = 121.14 g/mol) and dissolve in ~700 mL of ddH2O; carefully add 57.1 mL of 100 % glacial acetic acid (in fumehood!) and 100 mL of 0.5 M EDTA (pH 8.0); adjust to a final volume of 1 L with ddH2O
- Prepare 1xTAE buffer: Small size gel: 400 mL required: 8 mL 50x stock in 392 mL ddH2O; Large size gel: 600 are required: 12 mL 50x stock in 588 mL ddH2O

### calculator
~~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<link rel="stylesheet" href="mahe-lab_style.css">
		<title>MAHELAB SOP Calculator</title>
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
<button type="button" class="button" onclick="addRows()">Add Rows</button>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
	<tr><td></td><td></td></tr>
	<tr><td>Reagent/Input Calculations:</td><td></td></tr>
	<tr><td>Total volume of required Working Solution (mL):</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
	<tr><td>Volume of *** reagent (uL) to make Working Solution:</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
	<tr><td>Volume of *** reagent (uL) to make Working Solution:</td>
<!--- calculation: --->
	<td><input readonly type="text" size="10px" id="calc3"/></td></tr>
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
        // uncomment and adjust here with correct calculations for the correct text boxes above:
        //
        // document.getElementById('calc1').value = (0.22 * ( 2 + count )).toFixed(1);
        
        // document.getElementById('calc2').value = (1.1 * ( 2 + count )).toFixed(1);

        // document.getElementById('calc3').value = (218.9 * ( 2 + count )).toFixed(1);
    }
}
</script>
</body>
</html>
~~~~
### procedures
1. Weigh out (in an Erlenmeyer flask) the appropriate amount of agarose
- For 1% Agarose in a small size gel: 0.5 g & 50 mL 1xTAE
- For 1% Agarose in a large size gel: 1.0 g & 100 mL 1xTAE
2. Microwave agarose slurry on high in 30 s increments until boiling
3. Allow agarose solution to cool to ~60C
4. Add Ethidium bromide:
- 25 uL for small gel
- 50 uL for large gel
5. Assemble gel cast apparatus and insert combs (one for small gel and 1-2 for large gel)
6. Pour in agarose; remove bubbles with a pipette tip; allow to cool for at least 30 minutes
7. Remove comb(s) and remove the cast gel base from the casting stand.
8. Place cast gel into the electrophoresis tray with wells closest to the black lead
9. Pour in sufficient 1xTAE to fully immerse the gel
10. On a 10 cm length of parafilm, mark out the gel specimens (including ladders) by number:
11. Pipette ~1 uL Gel-Red/Gel-Green/Loading-Buffer Dye onto each parafilm spot (use the same pipette tip)
12. Pipette ~6 uL of one of the molecular weight ladders (“Millipore Direct Load” or “Thermo TrackIt”) onto the corresponding spot
13. Dial up the pipette to 6-7 uL and draw up the mix; gently pipette into the first gel well
14. Pipette ~5 uL of each subsequent specimen onto the corresponding spot
15. Dial up the pipette to 6-7 uL and draw up the mix; gently pipette into the corresponding well
16. Once the gel is fully loaded, apply the electrophoresis cover, and run the gel at 100V for 60 minutes. Be sure to set the powerpack time to ensure auto-halt.
17. Proceed to imaging using the GelDoc EtBr protocol: Refer to GelDoc SOP
18. Disassemble and clean the apparatus appropriately
