
### protocol
- Protocol: Iron Extraction & Quantification (Bone Marrow or Tissue)
- Faculty: Cumming School of Medicine
- Institute: Charbonneau Cancer Institute
- Site: Arthur J.E. Child Comprehensive Cancer Center, YC
- Version: 3
- Version Date: JUNE2024
- Approver: ermahe@ucalgary.ca

### authorization
- Requires Completion of Safety Training
- Requires Pre-Authorization by PI

### hazards
- Xylene is toxic, volatile, flammable, and poisonous
- HCl is a strong acid and will cause skin burns and damage clothing

### ppe
- Lab Coat
- Eye Protection
- Nitrile Gloves

### where
- Fumehood
- Pre-PCR bench if using MAHELAB plate reader

### references
-  https://github.com/mahe-lab/sops/MAHELAB_SOP_Assets/Sigma_IronKit_MAK472.pdf

### emergency
- Use spill kit to clean up small spills; Contact maintenance and log incident for large spills
- If skin/eye contact with chemicals, flush aggressively and continuously with water using an eyewash, sink or shower
- Contact emergency services and log any injuries as required

### cleanup
- Wipe down work surfaces with 70% isopropanol
- NOTE: Do not use isopropanol on instruments

### waste
- Tips/Tubes should be disposed of in yellow biohazard bag/tub
- Xylene should be disposed of in chemical waste container (fumehood)
- Sharps disposal: approved biohazard bucket

### maintenance
- Refer to plate reader literature for required maintenance steps

### before_starting
- Complete the tissue transfer SOP (https://mahe-lab.github.io/sops/sop_template.html?tissue_transfer_extraction.md)
- Ensure that the mount quick curls from a given case (might be multiple slides) are placed in a volumetric tube
- Ensure that there is sufficient 1M HCl & 1M NaOH on hand (use the calculator below)
- New stock 1M HCl can be made in a 100 mL graduated cylinder: add 8.3 mL 12M (37%) HCl; add ddH2O up to 100 mL and store in a 100 mL bottle; 100 mL 1M NaOH can be made using 4 g NaOH and carefully adding ddH2O up to 100 mL
- Remove the kit reagents (Reagent A, Reagent B and Reagent C as well as Iron standard) from the fridge and allow to warm to RT
- Prepare sufficient Working Solution (WS) using the calculator below; mix well by pipetting up and down

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
<table id="table1">
    <tr><td>Accession number:</td><td>Extracted tissue weight (mg):</td></tr>
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
    <tr><td>Reagent/Input Calculations:</td><td></td></tr>
    <tr><td>Required volume for each of 1M HCl and 1M NaOH (mL): </td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc1"/></td></tr>
    <tr><td>Required volume of Reagent A (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc2"/></td></tr>
    <tr><td>Required volume of Reagent B (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc3"/></td></tr>
<tr><td>Required volume of Reagent C (uL):</td>
<!--- calculation: --->
    <td><input readonly type="text" size="10px" id="calc4"/></td></tr>
</table>
<br>
<button type="button" class="button" onclick="calculate()">Calculate Reagent Volumes</button>
<br><br>
<button type="button" class="button" onclick="addCalcTable()">Add/Reload Calculation Table</button>
<br><br>
<table style="visibility:hidden" id="table3">
    <tr><td>Specimen/Accession number:</td><td>Extract weight (mg):</td><td>Extract Volume (mL):</td><td>Optical Density (Replicate 1):</td><td>Optical Density (Replicate 2):</td><td>Concentration (ug/mL):</td><td>g/g Calculation:</td></tr>
</table>
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
    }
}
function addCalcTable() {
    //empty the table if already filled
    var table3 = document.getElementById('table3');
    var t3rws = table3.rows.length;
    if(t3rws>1) {
        for(var i=1;i<t3rws;i++) {
            table3.deleteRow(-1);
        }
    }
    //turn on the table, but only if reagent calculations above have been done successfully...
    if( !isNaN(parseFloat(document.getElementById('calc1').value)) && !isNaN(parseFloat(document.getElementById('calc2').value)) && !isNaN(parseFloat(document.getElementById('calc3').value)) && !isNaN(parseFloat(document.getElementById('calc4').value)) ) {
        document.getElementById('table3').style="visibility:none";
        // add the rows for the 8 standards
        for(var i=1;i<=8;i++) {
            var row = table3.insertRow(i);
            var txtAcc = document.createElement('input'); txtAcc.setAttribute('type','text'); txtAcc.setAttribute('size','10px'); txtAcc.setAttribute('id',`3${i}0`); txtAcc.setAttribute('readonly', true); txtAcc.setAttribute('value','Standard '+`${i}`); var col = row.insertCell(0); col.appendChild(txtAcc); 
            var txtWt = document.createElement('input'); txtWt.setAttribute('type','text'); txtWt.setAttribute('size','10px'); txtWt.setAttribute('id',`3${i}1`); txtWt.setAttribute('readonly', true); txtWt.setAttribute('value','-'); var col = row.insertCell(1); col.appendChild(txtWt); 
            var txtVol = document.createElement('input'); txtVol.setAttribute('type','text'); txtVol.setAttribute('size','10px'); txtVol.setAttribute('id',`3${i}2`); txtVol.setAttribute('readonly', true); txtVol.setAttribute('value','-'); var col = row.insertCell(2); col.appendChild(txtVol); 
            var txtOD1 = document.createElement('input'); txtOD1.setAttribute('type','text'); txtOD1.setAttribute('size','10px'); txtOD1.setAttribute('id',`3${i}3`); var col = row.insertCell(3); col.appendChild(txtOD1); 
            var txtOD2 = document.createElement('input'); txtOD2.setAttribute('type','text'); txtOD2.setAttribute('size','10px'); txtOD2.setAttribute('id',`3${i}4`); var col = row.insertCell(4); col.appendChild(txtOD2);
            var txtCT = document.createElement('input'); txtCT.setAttribute('type','text'); txtCT.setAttribute('size','10px'); txtCT.setAttribute('id',`3${i}5`); var col = row.insertCell(5); col.appendChild(txtCT);
            var txtGG = document.createElement('input'); txtGG.setAttribute('type','text'); txtGG.setAttribute('size','10px'); txtGG.setAttribute('id',`3${i}6`); txtGG.setAttribute('readonly', true); txtGG.setAttribute('value','-'); var col = row.insertCell(6); col.appendChild(txtGG); 
        }
        //add rows for query specimens
        var table1 = document.getElementById('table1');
        var t1rws = table1.rows.length;
        var t3rws = table3.rows.length;
        for(var i=1;i<t1rws;i++) {
            var t3rwInd = i+t3rws-1;
            var row = table3.insertRow(t3rwInd);
            var txtAcc = document.createElement('input'); txtAcc.setAttribute('type','text'); txtAcc.setAttribute('size','10px'); txtAcc.setAttribute('id',`3${t3rwInd}0`); txtAcc.setAttribute('readonly', true); txtAcc.setAttribute('value', document.getElementById(`1${i}0`).value ); var col = row.insertCell(0); col.appendChild(txtAcc); 
            var txtWt = document.createElement('input'); txtWt.setAttribute('type','text'); txtWt.setAttribute('size','10px'); txtWt.setAttribute('id',`3${t3rwInd}1`); txtWt.setAttribute('readonly', true); txtWt.setAttribute('value',document.getElementById(`1${i}1`).value); var col = row.insertCell(1); col.appendChild(txtWt); 
            var txtVol = document.createElement('input'); txtVol.setAttribute('type','text'); txtVol.setAttribute('size','10px'); txtVol.setAttribute('id',`3${t3rwInd}2`); var col = row.insertCell(2); col.appendChild(txtVol); 
            var txtOD1 = document.createElement('input'); txtOD1.setAttribute('type','text'); txtOD1.setAttribute('size','10px'); txtOD1.setAttribute('id',`3${t3rwInd}3`); var col = row.insertCell(3); col.appendChild(txtOD1); 
            var txtOD2 = document.createElement('input'); txtOD2.setAttribute('type','text'); txtOD2.setAttribute('size','10px'); txtOD2.setAttribute('id',`3${t3rwInd}4`); var col = row.insertCell(4); col.appendChild(txtOD2);
            var txtCT = document.createElement('input'); txtCT.setAttribute('type','text'); txtCT.setAttribute('size','10px'); txtCT.setAttribute('id',`3${t3rwInd}5`); txtCT.setAttribute('readonly', true); var col = row.insertCell(5); col.appendChild(txtCT);
            var txtGG = document.createElement('input'); txtGG.setAttribute('type','text'); txtGG.setAttribute('size','10px'); txtGG.setAttribute('id',`3${t3rwInd}6`); txtGG.setAttribute('readonly', true); var col = row.insertCell(6); col.appendChild(txtGG); 
        }
        //add the calculateIron button
        var t3rws = table3.rows.length;
        var row = table3.insertRow(t3rws);
        var clckMe = document.createElement('button'); clckMe.textContent = 'Calculate Values'; var col = row.insertCell(0); col.appendChild(clckMe); 
        var cell1 = row.insertCell(1); cell1.innerHTML += 'Pearson Correlation: ';
        var txtPC = document.createElement('input'); txtPC.setAttribute('type','text'); txtPC.setAttribute('size','10px'); txtPC.setAttribute('id','pc'); txtPC.setAttribute('readonly', true); var col = row.insertCell(2); col.appendChild(txtPC);
        var cell3 = row.insertCell(3); cell3.innerHTML += 'Slope: ';
        var txtM = document.createElement('input'); txtM.setAttribute('type','text'); txtM.setAttribute('size','10px'); txtM.setAttribute('id','m'); txtM.setAttribute('readonly', true); var col = row.insertCell(4); col.appendChild(txtM);
        var cell5 = row.insertCell(5); cell5.innerHTML += 'Intercept: ';
        var txtB = document.createElement('input'); txtB.setAttribute('type','text'); txtB.setAttribute('size','10px'); txtB.setAttribute('id','b'); txtB.setAttribute('readonly', true); var col = row.insertCell(6); col.appendChild(txtB);
        clckMe.addEventListener('click', () => { checkItAll(); });
    }
    //validate table3 contents, calculate the regression, fill in missing concentrations and calculate g/g
    function checkItAll() {
        var table3 = document.getElementById('table3');
        var t3rws = table3.rows.length;
        var tf = true;
        //ensure that two OD replicates for each specimen are input, that each standard has a concentration entered and that extract volumes are provided for each query specimen
        for (var i=1;i<t3rws-1;i++) {
            if( isNaN(parseFloat(document.getElementById(`3${i}3`).value)) || isNaN(parseFloat(document.getElementById(`3${i}4`).value)) ) { tf = false; console.log('missing OD value(s)'); break; }
            if( i<=8 && isNaN(parseFloat(document.getElementById(`3${i}5`).value)) ) { tf = false; console.log('missing standard concentration value(s)'); break; }
            if( i>8 && isNaN(parseFloat(document.getElementById(`3${i}2`).value)) ) { tf = false; console.log('missing query specimen volume(s)'); break; }
        }
        if(tf) {
            y1 = []; y2 = []; x = [];
            //calculate average & standard deviation of OD replicates, and highlight CoV-extermis cases
            for(var i=1;i<=8;i++) {
                y1.push(parseFloat(document.getElementById(`3${i}3`).value));
                y2.push(parseFloat(document.getElementById(`3${i}4`).value));
                x.push(parseFloat(document.getElementById(`3${i}5`).value));
                const avg = (parseFloat(document.getElementById(`3${i}3`).value) + parseFloat(document.getElementById(`3${i}4`).value))/2;
                const stdev = Math.sqrt( (parseFloat(document.getElementById(`3${i}3`).value) - avg)**2 + (parseFloat(document.getElementById(`3${i}4`).value) - avg)**2 );
                if(stdev/avg > 0.1 ) { 
                    document.getElementById(`3${i}3`).style.color = '#f7da65'; //yellow/amber=hazard
                    document.getElementById(`3${i}4`).style.color = '#f7da65'; //yellow/amber=hazard
                }
            }
            //calculate pearson correlation, m and b
            const pCC = pearson(x.concat(x), y1.concat(y2));
            document.getElementById('pc').value = pCC;
            if(pCC<0.95) {
                document.getElementById('pc').style.color = '#f7da65'; //yellow/amber=hazard
            }
            const lSQ = findLineByLeastSquares(x.concat(x), y1.concat(y2));
            document.getElementById('m').value = lSQ[0];
            document.getElementById('b').value = lSQ[1];
            //calculate unknown concentrations & g/g
            for (var i=9;i<t3rws-1;i++) {
                const avg = (parseFloat(document.getElementById(`3${i}3`).value) + parseFloat(document.getElementById(`3${i}4`).value))/2;
                const stdev = Math.sqrt( (parseFloat(document.getElementById(`3${i}3`).value) - avg)**2 + (parseFloat(document.getElementById(`3${i}4`).value) - avg)**2 );
                if(stdev/avg > 0.1 ) { 
                    document.getElementById(`3${i}3`).style.color = '#f7da65'; //yellow/amber=hazard
                    document.getElementById(`3${i}4`).style.color = '#f7da65'; //yellow/amber=hazard
                }
                document.getElementById(`3${i}5`).value = (avg-lSQ[1])/lSQ[0];
                document.getElementById(`3${i}6`).value = ((((avg-lSQ[1])/lSQ[0])*document.getElementById(`3${i}2`).value)/1000)/document.getElementById(`3${i}1`).value;
                //flag out-of-bounds results
                if(avg < Math.min.apply(null,y1)) {
                    document.getElementById(`3${i}3`).style.color = '#dd0238'; //red=danger
                    document.getElementById(`3${i}4`).style.color = '#dd0238'; //red=danger
                    document.getElementById(`3${i}5`).style.color = '#dd0238'; //red=danger
                    document.getElementById(`3${i}6`).style.color = '#dd0238'; //red=danger
                }
            }
        }
    }
    function pearson(x, y) {
        let promedio = (lista) => { return lista.reduce((s, a) => s + a, 0) / lista.length };
        let n = x.length, prom_x = promedio(x) , prom_y = promedio(y);
        return (x.map( (e, i, r) => (r = {x:e, y:y[i]}) ).reduce( (s, a) => s + a.x * a.y, 0) - n * prom_x * prom_y) / 
        ((Math.sqrt(x.reduce( (s, a) => (s + a * a) , 0) - n * prom_x * prom_x)) *
        (Math.sqrt(y.reduce( (s, a) => (s + a * a) , 0) - n * prom_y * prom_y)));
    }
    function findLineByLeastSquares(values_x, values_y) {
        var x_sum = 0; var y_sum = 0; var xy_sum = 0; var xx_sum = 0; var count = 0; var x = 0; var y = 0;
        var values_length = values_x.length;
        if (values_length != values_y.length) {
            throw new Error('The parameters values_x and values_y need to have same size!');
        }
        if (values_length === 0) {
            return [ [], [] ];
        }
        for (let i = 0; i< values_length; i++) {
            x = values_x[i]; y = values_y[i]; x_sum+= x; y_sum+= y; xx_sum += x*x; xy_sum += x*y; count++;
        }
        var m = (count*xy_sum - x_sum*y_sum) / (count*xx_sum - x_sum*x_sum);
        var b = (y_sum/count) - (m*x_sum)/count;
        return [m, b];
    }
}
</script>
</body>
</html>
~~~~

### procedures
1. In the fumehood, dissolve the mount quick curls in the glass volumetric tubes with 500 uL xylene
2. Vortex gently and incubate 5 min at RT in the fumehood
3. When the gel has fully dissolved, spin gently in the Dade centrifuge on low x 2 minutes; NOTE: DO NOT USE the Eppendorf or other centrifuge, as these might fracture the flask!!
4. Carefully pipette off the supernatant (discard in the organic waste in fumehood) without disturbing the pellet
5. Allow the pellet to dry fully in the fumehood (can be left overnight, WITHOUT the stopper, to allow for xylene to evaporate completely)
6. Add 500 uL 1M HCl and pipette carefully but aggressively (20 passes) to re-suspend the pellet
7. Replace the stoppers and place the tube in the thermomixer set at 50°C with gentle rotation overnight
8. Carefully add additional 1M NaOH up to the exact 1 mL volume indicated on the volumetric tube; allow tubes to stand (with stoppers in place) at RT x 30 minutes
9. If not proceeding directly to quantification, the supernatant from step 8 can be stored in a labelled Eppendorf tube in the -20C freezer
10.	Prepare a 1000 µg/dL (10 µg/mL) Iron Standard by mixing 40 µL of the 10 mg/dL kit Iron standard with 360 µL ddH2O in an Eppendorf tube (label the tube “#1”)
11.	Prepare subsequent dilutions (mix well by pipetting up and down):
#2: 80 uL from #1 with 20 uL ddH2O (800 µg/dL iron; 8 µg/mL iron)
#3: 60 uL from #1 with 40 uL ddH2O (600 µg/dL iron; 6 µg/mL iron)
#4: 40 uL from #1 with 60 uL ddH2O (400 µg/dL iron; 4 µg/mL iron)
#5: 30 uL from #1 with 70 uL ddH2O (300 µg/dL iron; 3 µg/mL iron)
#6: 20 uL from #1 with 80 uL ddH2O (200 µg/dL iron; 2 µg/mL iron)
#7: 10 uL from #1 with 90 uL ddH2O (100 µg/dL iron; 1 µg/mL iron)
#8: 100 uL ddH2O (0 µg/dL iron; 0 µg/mL iron)
12.	Pipette 200 uL of WS into the wells of a 96-well optical plate (sufficient for each specimen and standard to be assessed in duplicate)
13.	Transfer 50 uL of each of the above standards and query specimens into the appropriate wells, with duplicates performed
14.	Tap the plate gently to mix and allow the plate to stand at RT for 40 minutes
15.	Read optical density (OD) at 590 nm using a platereader
16.	EITHER use the above calculator tool OR generate a standard curve in excel by plotting the OD of the reference specimens with their respective concentrations
17.	EITHER use the above calculator tool OR, from the standard curve, use the query specimen OD to calculate query specimen iron concentration (report the average of the duplicates as well as the standard deviation for each specimen)
18.	NOTE: if a query specimen OD exceeds the standard curve upper limit (ie is higher than the highest measurement on the standard curve) a dilution of the specimen will need to be re-run to confirm accuracy of the concentration
19.	NOTE: if a query specimen OD is less than the standard curve lower limit (ie is lower than the 0 µg/mL measurement on the standard curve), the specimen should be rejected and re-extraction will be required
20.	EITHER use the above calculator tool OR use the measured specimen iron weights and total weights to calculate the g/g (µg/µg) ratio for each specimen
