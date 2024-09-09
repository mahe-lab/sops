
### protocol
- Protocol: add
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC
- Date: 8SEP2024
- Version: 2
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Ethidium bromide is mutagenic & carcinogenic
- Isopropanol, Ethanol, and QIAGEN buffers are toxic, volatile, flammable, and/or poisonous
- Gel excision with scalpels poses a risk of sharps injury

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Post-PCR bench

### references
- See QIAGEN handbook 

### emergency
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries if required

### cleanup
- Wipe down work surfaces with 70% isopropanol
- NOTE: Do not use isopropanol on instruments

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag/tub
- Dispose of gels in contaminated gel waste bucket

### maintenance
- Use ddH2O & kimwipes to clean imaging trays

### before_starting
- This SOP assumes an Agarose gel stained with Ethidium Bromide and that the necessary GelDoc Images/Reports have been generated
- Prepare one 1.5/2.0 mL labelled tube per band/specimen being excised
- Weigh each tube pre-excision in mg (W1) and enter

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
    <tr><td>Scan/enter Accession Number</td><td>W1 (mg)</td><td>W2 (mg)</td><td>Volume Buffer QG (uL)</td><td>Volume Isopropanol (uL)</td></tr>
</table>
<table id="table1">
    <tr><td><input type="text" size="100px" id="00"/></td> <td><input type="text" size="10px" id="01"/></td> <td><input type="text" size="10px" id="02"/></td><td><input readonly type="text" size="10px" id="03"/></td><td><input readonly type="text" size="10px" id="04"/></td></tr>
    
    <tr><td><input type="text" size="100px" id="10"/></td><td><input type="text" size="10px" id="11"/></td><td><input type="text" size="10px" id="12"/></td><td><input readonly type="text" size="10px" id="13"/></td><td><input readonly type="text" size="10px" id="14"/></td></tr>
</table>
<br>
<button type="button" onclick="addRows()">Add Rows</button>
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
        if(i == 0) {
            txt.setAttribute('size','100px');
        }
        else {
            txt.setAttribute('size','10px');
        }
        txt.setAttribute('id',`${trows}${i}`);
        if(i == tcols-2 || i == tcols-1) {
            txt.setAttribute('readonly','readonly')
        }
        var col = row.insertCell(i);
        col.appendChild(txt);
    }
}   
function calculate() {
    var count = 0;
    var table = document.getElementById('table1');
    var trows = table.rows.length;
    for (var i=0;i<trows;i++) {
        var W1 = parseFloat(document.getElementById(`${i}1`).value);
        var W2 = parseFloat(document.getElementById(`${i}2`).value);
        if( isNaN(W1) || isNaN(W2) || document.getElementById(`${i}0`).value == "") {}
        else {
            document.getElementById(`${i}3`).value = Math.ceil((W2-W1)/100)*300;
            document.getElementById(`${i}4`).value = Math.ceil((W2-W1)/100)*100;
        }
    }
}
</script>
</body>
</html>
~~~~

### procedures
1. Identify the specific bands to be excised relative to the GelDoc Image(s)
2. Re-image the gel with the fluorescent rulers placed to flank the band of interest (one ruler parallel to the height of the gel and one parallel to the width of the gel)
3. Re-image as necessary to ensure that the rulers are correctly placed
4. Use a fresh scalpel/razor to carefully cut out the band, ensuring that as little of the gel is excised as possible
5. Re-image as necessary to ensure that the band is correctly excised
6. Place the band in the appropriate tube
7. Weigh the filled tube (mg) and enter the value in column W2
8. Click calculate to determine the volume (uL) of buffer QG to add to each tube
9. Cap & incubate in Thermomixer at 50°C for 10 min
10. Add appropriate volume of isopropanol to the specimen and vortex briefly
11. Pipette into a QIAquick column (ensure the column is placed in a provided 2 mL collection tube); centrifuge at 13,000 rpm x 1 minute; discard the flow through. NOTE: The QIAquick column has a maximum volume of 800 uL.
12. If the volume from step 10 exceeds 800 uL, perform step 11 repeatedly until the full volume from step 10 has been passed through the column
13. Add 500 uL Buffer QG to the QIAquick column and centrifuge at 13,000 rpm x 1 minute; discard the flow through
14. Add 750 uL Buffer PE to the QIAquick column; allow the column to stand 5 minutes; centrifuge at 13,000 rpm x 1 minute; discard the flow through
15. Centrifuge the QIAquick column again at 13,000 rpm x 1 minute; discard the collection tube
16. Place the QIAquick column in a clean appropriately labelled 1.5 ml specimen tube
17. Add 50 uL Buffer EB to the center of the QIAquick column membrane; centrifuge at 13,000 rpm x 1 minute
18. Proceed to downstream workflow(s) or store in -20°C freezer
