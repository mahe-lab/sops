
### protocol
- Protocol: Reverse Transcription (NEB Protocol)
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC083402
- Version: 1
- Version Date: 1MAY2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Ensure that the dead-air box is closed shut prior to engaging UV treatment

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Dead-air isolation box
- Post-PCR Bench Thermocycler

### references
- See NEB protocol reference:

### emergency
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries if required

### cleanup
- Wipe down work surfaces with 70% isopropanol
- 5 minute Dead-air UV exposure

### waste
- Tips/Tubes should be disposed of in biohazard bags

### maintenance
- ...insert details here...

### before_starting
- Obtain some ice and place in the dead-air box ice box; the aluminum tube tray can be chilled in the dead-air box ice box
- Obtain sufficient tubes/strips to accomodate the specimens; label the tubes/strips appropriately
- Run 5 minute Dead-air UV exposure
- AFTER UV pre-treatment, identify the specimens for RT (scan/enter the specimen accession numbers below), as well as the necessary NEB reagents. Gently warm these on ice until ready to make the RT working solution.

### calculator
~~~~
<table id="table1">
    <tr><td>Accession number:</td><td>RNA Concentration (ug/uL):</td></tr>
    <tr><td><input type="text" size="10px" id="110" placeholder=""/></td><td><input type="text" size="10px" id="111" placeholder=""/></tr>
    <tr><td><input type="text" size="10px" id="120" placeholder=""/></td><td><input type="text" size="10px" id="121" placeholder=""/></tr>
    <tr><td><input type="text" size="10px" id="130" placeholder=""/></td><td><input type="text" size="10px" id="131" placeholder=""/></tr>
    <tr><td><input type="text" size="10px" id="140" placeholder=""/></td><td><input type="text" size="10px" id="141" placeholder=""/></tr>
</table>
<br>
<button type="button" class="button" onclick="addRow()">Add Row</button><button type="button" class="button" onclick="deleteRow()">Remove Row</button>
<br><br>
<!--- insert the necessary calculations here.--->
<table id="table2">
    <tr><td>RTWS Calculations:</td><td></td></tr>
    <tr><td>Volume of NEB 10X Isothermal Amplification Buffer (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc1"/></td></tr>
    <tr><td>Volume of NEB dNTP Mix (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc2"/></td></tr>
    <tr><td>Volume of NEB Random Primer Mix (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc3"/></td></tr>
<tr><td>Volume of NEB Murine RNase Inhibitor (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc4"/></td></tr>
<tr><td>Volume of NEB WarmStart RTx Reverse Transcriptase (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc5"/></td></tr>
</table>
<br>
<button type="button" class="button" onclick="calculate()">Calculate Reagent Volumes</button>
<br><br>
<button type="button" class="button" onclick="addCalcTable()">Add/Reload Calculation Table</button>
<br><br>
<script type='text/javascript'>
function addRow() {
    document.getElementById('table3').style="visibility:hidden";
    document.getElementById('calc1').value = "";
    document.getElementById('calc2').value = "";
    document.getElementById('calc3').value = "";
    document.getElementById('calc4').value = "";
    var table1 = document.getElementById('table1');
    var trows = table1.rows.length;
    var row = table1.insertRow(trows);
    var txtAcc = document.createElement('input'); txtAcc.setAttribute('type','text'); txtAcc.setAttribute('size','10px'); txtAcc.setAttribute('id',`1${trows}0`); var col = row.insertCell(0); col.appendChild(txtAcc);
    var txtWt = document.createElement('input'); txtWt.setAttribute('type','text'); txtWt.setAttribute('size','10px'); txtWt.setAttribute('id',`1${trows}1`); var col = row.insertCell(1); col.appendChild(txtWt);
}
function deleteRow() {
    document.getElementById('table3').style="visibility:hidden";
    document.getElementById('calc1').value = "";
    document.getElementById('calc2').value = "";
    document.getElementById('calc3').value = "";
    document.getElementById('calc4').value = "";
    var table1 = document.getElementById('table1');
    var trows = table1.rows.length;
    if(trows>1) { table1.deleteRow(-1); }
}
function calculate() {
    document.getElementById('table3').style="visibility:hidden";
    var count = 0;
    var table1 = document.getElementById('table1');
    var trows = table1.rows.length;
    var tcols = table1.rows[1].cells.length;
    for(var i=1;i<trows;i++) {
        var accText = document.getElementById('1'+`${i}`+'0').value;
        var wtText = parseFloat(document.getElementById('1'+`${i}`+'1').value);
        if( accText != '' && !isNaN(wtText) ) {
            count++;
        }
    }
    if(count == (trows-1)) {
        document.getElementById('calc1').value = (2.5 * count ).toFixed(1);
        document.getElementById('calc2').value = (200 * ( 16 + count )).toFixed(1);
        document.getElementById('calc3').value = (10 * ( 16 + count )).toFixed(1);
        document.getElementById('calc4').value = (10 * ( 16 + count )).toFixed(1);
        document.getElementById('calc5').value = (10 * ( 16 + count )).toFixed(1);
    }
}
~~~~

### procedures
1. Using the above calculator, prepare the RT working solution (WS). Return NEB reagents to the freezer.
2. Pipette out the required water for each reaction per the above calculator
3. Pipette 5.75 uL of RTWS into each tube
4. Pipette out the required specimen volumes into each respective tube; gently pipette up and down to ensure that the solutions are well mixed, ensuring not to cross-contaminate
5. Keep the specimens on ice until ready to proceed to the thermocycler
6. Run the NEB WarmStart RTx program: 5 minutes at 25°C for annealing; 10 minutes at 55°C for synthesis; 10 minutes at 80°C for heat inactivation
7. Store cDNA products in -20°C freezer until ready for downstream use
