
### protocol
- Protocol: QIACUBE DNA Extraction from FFPE Tissues
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC083402
- Version: 1
- Version Date: 24FEB2025
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
- Pre-PCR Bench
- QIACUBE Room

### references
- QIAmp DNA from FFPE: https://github.com/mahe-lab/sops/blob/main/MAHELAB_SOP_Assets/QIAamp%20DNA%20FFPE.pdf
- QIAmp DNA from FFPE Protocol Sheet:
- QIACUBE Manual:  

### emergency
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries

### cleanup
- Benchtop/fumehood surface wipedown with 70% isopropanol

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag
- Xylene/ethanol should be disposed of in chemical waste container (fumehood)
- Sharps disposal: use approved biohazard bucket

### maintenance
- Wipe surfaces down with 70% isopropanol
- Do not use isopropanol on instruments

### before_starting
- A maximum of 12 specimens can be processed per run
- Rotor adapters, QIAmp columns and Qiagen elution tubes are required
- Obtain fresh scrape blades (one per specimen)
- 
- Ensure that sufficient Xylene, 100% Ethanol, Proteinase K, Buffers ATL, AL, AW1, AW2, and ATE are available
- 
- Enter specimen accession numbers below and use the calculator to calculate the required reagent volumes 

### calculator
~~~~
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<link rel="stylesheet" href="mahe-lab_style.css">
		<title>Reagent Calculator</title>
	</head>
<body>
<!---configure reagent prep details here, with calculations based on the table inputs below--->
<table id="table1">
	<tr><td><input type="text" size="10px" id="00"/></td><td><input type="text" size="10px" id="01"/></td><td><input type="text" size="10px" id="02"/></td><td><input type="text" size="10px" id="03"/></td></tr>
	<tr><td><input type="text" size="10px" id="10"/></td><td><input type="text" size="10px" id="11"/></td><td><input type="text" size="10px" id="12"/></td><td><input type="text" size="10px" id="13"/></td></tr>
  <tr><td><input type="text" size="10px" id="20"/></td><td><input type="text" size="10px" id="21"/></td><td><input type="text" size="10px" id="22"/></td><td><input type="text" size="10px" id="23"/></td></tr>
</table>
<br>
<!--- insert the necessary calculations here.--->
<table id="table2">
	<tr><td>Volume of Xylene required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc1"/></td></tr>
	<tr><td>Volume of 100% Ethanol required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc2"/></td></tr>
	<tr><td>Volume of Buffer ATL required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc3"/></td></tr>
	<tr><td>Volume of Proteinase K required (uL):</td>
	<td><input readonly type="text" size="10px" id="calc4"/></td></tr>
</table>
<br>
<button type="button" class="button" onclick="calculate()">Calculate</button>
<script type='text/javascript'>
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
	document.getElementById('calc1').value = (1100 * (count)).toFixed(1);
        document.getElementById('calc2').value = (1100 * (count)).toFixed(1);
	document.getElementById('calc3').value = (198 * (count)).toFixed(1);
        document.getElementById('calc4').value = (22 * (count)).toFixed(1);
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
4. In the fumehood, add 1000 uL xylene per tube
5. Cap, vortex well and incubate 5 min at RT
6. Centrifuge 5 min at 10,000 RPM at RT and carefully pipette off the supernatant
7. Add 1000 uL 100% Ethanol
8. Vortex 10 s and incubate 5 min at RT
9. Centrifuge 5 min at 10,000 RPM at RT and pipette off the supernatant
10. Let the tube stand open in the hood to dry the pellet (this may take 30 minutes or more)
11. Add 200uL of the ATL/Proteinase K working solution to each tube and reconstitue/mix
12. Incubate in the thermomixer at 56C for 1 hour
13. Remove the tubes and increase the thermomixer temperature to 90C
14. Incubate the tubes at 90C for 1 hour
15. Assemble the QIACUBE rotor adapters (use the Protocol Sheet linked above as a guide)
16. In the hole at the narrow end of the rotor adapter (facing left), place the QIAmp spin column and anchor the cap securely
17. The middle hole is left open/un-filled
18. In the hole at the wide end of the rotor adapeter, place one Qiagen collection tube (labelled); anchor the cap securely in the anchor facing down
19. Load the specimens (in even numbers) starting at the top of the specimen rack columns
20. Load the corresponding rotor adapters in the appropriate rotor positions
21. Load 2 racks of 1000 uL (normal; light gray) QIACUBE tips
22. Place QIACUBE reagent bottles into the correct slots: 2: AL; 3: 100% Ethanol; 4: AW1; 5: AW2; 6: ATE
23. Run the QIACUBE protocol
24. When complete, proceed to DNA quantification & store specimens in -20C specimen freezer
