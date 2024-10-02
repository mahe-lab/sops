
### protocol
- Protocol: Tissue Transfer for Extraction
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC
- Version: 2
- Version Date: 30MAY2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- MountQuick is toxic, volatile, flammable, and poisonous. See SDS
- Scrape-blades/glass slides may cause sharps injury

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Fumehood

### references
- Technical notes can be found here: https://mahe-lab.github.io/sops/MAHELAB_SOP_Assets/1-s2.0-S0023683723000041-mmc1.pdf

### emergency
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries as required

### cleanup
- Wipe down work surfaces with 70% isopropanol
- NOTE: Do not use isopropanol on instruments

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag/tub
- Xylene/ethanol should be disposed of in chemical waste container (fumehood)
- Sharps disposal: U of C approved biohazard bucket (benchtop)

### maintenance
- add

### before_starting
- Setup a 60°C oven/incubator
- Identify the donor slide(s); if required, accession the specimen(s)
- Scan/type in the accession numbers and enter slide weights below for record keeping
- If applicable, encircle the area(s) being transferred using a tungsten pen on the slide UNDERsurface
- If applicable, soak the original slide(s) in xylene until coverslip(s) is/are easily removed without damage to the tissue section(s)
- Run the slide(s) through several xylene soaks to ensure removal of residual mounting media as required
- Allow slide(s) to dry in fume hood for 30-60 minutes after xylene soaks

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
    <tr><td>Scan/enter Accession Number</td><td>Pre-Transfer Weight (mg)</td><td>Post-Transfer Weight (mg)</td><td>Calculated Tissue Weight (mg)</td></tr>
</table>
<table id="table1">
    <tr><td><input type="text" size="10px" id="00"/></td> <td><input type="text" size="10px" id="01"/></td> <td><input type="text" size="10px" id="02"/></td><td><input readonly type="text" size="10px" id="03"/></td></tr>
    
    <tr><td><input type="text" size="10px" id="10"/></td><td><input type="text" size="10px" id="11"/></td><td><input type="text" size="10px" id="12"/></td><td><input readonly type="text" size="10px" id="13"/></td></tr>
</table>
<br>
<button type="button" class="button" onclick="addRows()">Add Rows</button>
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
        if(i == tcols-1) {
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
            document.getElementById(`${i}3`).value = W1-W2;
        }
    }
}
</script>
</body>
</html>
~~~~
### procedures
1. Label one specimen tube per series of slides/sections being combined
2. Weigh the slide(s) and record this value in the Pre-transfer weight field above
3. Apply Mount-Quick over the area(s) of interest. Use sufficient Mount-Quick to form a meniscus over the entire area of interest. Use an applicator stick to spread the Mount-Quick evenly over the area of interest if required.
4. Place slide in a flat horizontal position (metal slide tray) in a 60°C oven for EXACTLY 1 hour (longer will cause excess hardening).
5. Gently peel off the Mount-Quick gel layer with a disposable blade/scalpel
6. Place the peel in a labelled specimen tube (if extracting RNA/DNA, this should be an eppendorf tube; if needing accurate post-processing volume, use a 1 mL glass volumetric flask)
7. Weigh the slide(s) and record this value in the Post-transfer weight field above
8. Donor slides can be re-coverslipped, or disposed of in sharps container
9. Proceed to… QIAamp DNA Extraction from FFPE Materials (Slides or Scrolls/Curls) OR RNA Extraction from FFPE Materials (Slides or Scrolls/Curls) OR Protein Extraction from FFPE Materials (Slides or Scrolls/Curls) OR Other extraction process
