---
layout: default
title: Resources
---
{% include navigation.html %}

I find myself coming back to these calculations over and over again. Some may find this useful too...

<div style="background: #f8f9fa; padding: 20px; border-radius: 8px; border: 1px solid #e9ecef; max-width: 500px; margin-bottom: 30px;">
  <h3 style="margin-top: 0;">Droplet Volume Calculator</h3>
  <p style="font-size: 0.9em; color: #555;">Convert measured droplet diameter under the microscope directly into volume.</p>
  
  <div style="margin-bottom: 15px;">
    <label for="dropDiameter" style="display: block; font-weight: bold; margin-bottom: 5px;">Droplet Diameter:</label>
    <div style="display: flex; gap: 10px;">
      <input type="number" id="dropDiameter" value="50" style="flex: 1; padding: 8px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box;">
      <select id="dropDiameterUnit" style="padding: 8px; border: 1px solid #ccc; border-radius: 4px; background: white;">
        <option value="um">μm</option>
        <option value="mm">mm</option>
      </select>
    </div>
  </div>

  <button onclick="calculateVolume()" style="background: #0366d6; color: white; border: none; padding: 10px 15px; border-radius: 4px; cursor: pointer; font-weight: bold; width: 100%;">Calculate Volume</button>

  <div id="volResults" style="margin-top: 20px; display: none; background: #fff; padding: 15px; border-radius: 4px; border: 1px solid #ddd;">
    <p style="color: #0366d6; font-size: 1.2em; margin-top: 0;"><strong>Volume:</strong></p>
    <p><strong><span id="volPLOut">0</span> pL</strong> (picoliters)</p>
    <p><strong><span id="volNLOut">0</span> nL</strong> (nanoliters)</p>
  </div>
</div>

<div style="background: #f8f9fa; padding: 20px; border-radius: 8px; border: 1px solid #e9ecef; max-width: 500px; margin-bottom: 30px;">
  <h3 style="margin-top: 0;">Droplet Yield & Frequency Calculator</h3>
  <p style="font-size: 0.9em; color: #555;">Calculate total droplet yield and generation rate (Hz) based on droplet diameter and dispersed phase flow rate.</p>
  
  <div style="margin-bottom: 10px;">
    <label for="dropDiaCount" style="display: block; font-weight: bold; margin-bottom: 5px;">Droplet Diameter:</label>
    <div style="display: flex; gap: 10px;">
      <input type="number" id="dropDiaCount" value="50" style="flex: 1; padding: 8px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box;">
      <select id="dropDiaUnitCount" style="padding: 8px; border: 1px solid #ccc; border-radius: 4px; background: white;">
        <option value="um">μm</option>
        <option value="mm">mm</option>
      </select>
    </div>
  </div>

  <div style="margin-bottom: 10px;">
    <label for="flowRate" style="display: block; font-weight: bold; margin-bottom: 5px;">Total Aqueous Flow Rate:</label>
    <div style="display: flex; gap: 10px;">
      <input type="number" id="flowRate" value="10" style="flex: 1; padding: 8px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box;">
      <select id="flowRateUnit" style="padding: 8px; border: 1px solid #ccc; border-radius: 4px; background: white;">
        <option value="uL/min">µL/min</option>
        <option value="uL/hr">µL/hr</option>
      </select>
    </div>
  </div>

  <div style="margin-bottom: 15px;">
    <label for="runTime" style="display: block; font-weight: bold; margin-bottom: 5px;">Run Time Duration:</label>
    <div style="display: flex; gap: 10px;">
      <input type="number" id="runTime" value="60" style="flex: 1; padding: 8px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box;">
      <select id="runTimeUnit" style="padding: 8px; border: 1px solid #ccc; border-radius: 4px; background: white;">
        <option value="min">Minutes</option>
        <option value="hr">Hours</option>
      </select>
    </div>
  </div>

  <button onclick="calculateYield()" style="background: #0366d6; color: white; border: none; padding: 10px 15px; border-radius: 4px; cursor: pointer; font-weight: bold; width: 100%;">Calculate Yield</button>

  <div id="countResults" style="margin-top: 20px; display: none; background: #fff; padding: 15px; border-radius: 4px; border: 1px solid #ddd;">
    <p style="color: #0366d6; font-size: 1.2em; margin-top: 0;"><strong>Total Droplets Generated:</strong></p>
    <p style="font-size: 1.4em; margin: 10px 0;"><strong><span id="totalDropletsFormatted">0</span></strong></p>
    <p style="color: #555; font-size: 0.9em;">Scientific: <span id="totalDropletsSci">0</span></p>
    <hr style="border-top: 1px solid #eee; margin: 15px 0;">
    <p style="color: #28a745; font-weight: bold;"><strong>Generation Rate:</strong> <span id="frequencyOut">0</span> Hz (droplets/sec)</p>
  </div>
</div>

<div style="background: #f8f9fa; padding: 20px; border-radius: 8px; border: 1px solid #e9ecef; max-width: 500px; margin-bottom: 30px;">
  <h3 style="margin-top: 0;">Poisson Droplet Loading Calculator</h3>
  <p style="font-size: 0.9em; color: #555;">Calculate the probability of single-cell encapsulation based on your cell concentration and droplet volume.</p>
  
  <div style="margin-bottom: 10px;">
    <label for="cellConc" style="display: block; font-weight: bold; margin-bottom: 5px;">Cell Concentration (cells/mL):</label>
    <input type="number" id="cellConc" value="1000000" style="width: 100%; padding: 8px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box;">
  </div>

  <div style="margin-bottom: 15px;">
    <label for="dropVol" style="display: block; font-weight: bold; margin-bottom: 5px;">Droplet Volume:</label>
    <div style="display: flex; gap: 10px;">
      <input type="number" id="dropVol" value="100" style="flex: 1; padding: 8px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box;">
      <select id="dropVolUnit" style="padding: 8px; border: 1px solid #ccc; border-radius: 4px; background: white;">
        <option value="pL">pL</option>
        <option value="nL">nL</option>
      </select>
    </div>
  </div>

  <button onclick="calculatePoisson()" style="background: #0366d6; color: white; border: none; padding: 10px 15px; border-radius: 4px; cursor: pointer; font-weight: bold; width: 100%;">Calculate Probabilities</button>

  <div id="results" style="margin-top: 20px; display: none; background: #fff; padding: 15px; border-radius: 4px; border: 1px solid #ddd;">
    <p><strong>Lambda (λ):</strong> <span id="lambdaOut">0</span> cells/drop</p>
    <hr style="border-top: 1px solid #eee; margin: 10px 0;">
    <p><strong>Empty (k=0):</strong> <span id="p0">0</span>%</p>
    <p style="color: #28a745; font-weight: bold;"><strong>Single Cell (k=1):</strong> <span id="p1">0</span>%</p>
    <p style="color: #d73a49; font-weight: bold;"><strong>Multiple Cells (k≥2):</strong> <span id="p2">0</span>%</p>
  </div>
</div>

<div style="background: #f8f9fa; padding: 20px; border-radius: 8px; border: 1px solid #e9ecef; max-width: 500px; margin-bottom: 30px;">
  <h3 style="margin-top: 0;">Double Poisson Co-Encapsulation Calculator</h3>
  <p style="font-size: 0.9em; color: #555;">Calculate the probability of perfectly pairing exactly one Cell A and one Cell B, plus all triplet+ states.</p>
  
  <div style="margin-bottom: 10px;">
    <label for="cellConcA" style="display: block; font-weight: bold; margin-bottom: 5px;">Cell A Concentration (cells/mL):</label>
    <input type="number" id="cellConcA" value="1000000" style="width: 100%; padding: 8px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box;">
  </div>

  <div style="margin-bottom: 10px;">
    <label for="cellConcB" style="display: block; font-weight: bold; margin-bottom: 5px;">Cell B Concentration (cells/mL):</label>
    <input type="number" id="cellConcB" value="1000000" style="width: 100%; padding: 8px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box;">
  </div>

  <div style="margin-bottom: 15px;">
    <label for="dropVolDouble" style="display: block; font-weight: bold; margin-bottom: 5px;">Droplet Volume:</label>
    <div style="display: flex; gap: 10px;">
      <input type="number" id="dropVolDouble" value="100" style="flex: 1; padding: 8px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box;">
      <select id="dropVolUnitDouble" style="padding: 8px; border: 1px solid #ccc; border-radius: 4px; background: white;">
        <option value="pL">pL</option>
        <option value="nL">nL</option>
      </select>
    </div>
  </div>

  <button onclick="calculateDoublePoisson()" style="background: #0366d6; color: white; border: none; padding: 10px 15px; border-radius: 4px; cursor: pointer; font-weight: bold; width: 100%;">Calculate Co-Encapsulation</button>

  <div id="doubleResults" style="margin-top: 20px; display: none; background: #fff; padding: 15px; border-radius: 4px; border: 1px solid #ddd;">
    <p><strong>Lambda A (λ<sub>A</sub>):</strong> <span id="lambdaAOut">0</span> cells/drop</p>
    <p><strong>Lambda B (λ<sub>B</sub>):</strong> <span id="lambdaBOut">0</span> cells/drop</p>
    <hr style="border-top: 1px solid #eee; margin: 10px 0;">
    <p><strong>Empty Droplet (0 cells):</strong> <span id="dpEmpty">0</span>%</p>
    <p><strong>Exactly 1 Cell A (Only):</strong> <span id="dpAOnly">0</span>%</p>
    <p><strong>Exactly 1 Cell B (Only):</strong> <span id="dpBOnly">0</span>%</p>
    <p style="color: #28a745; font-weight: bold; font-size: 1.1em; margin: 15px 0;"><strong>Perfect Pairing (1A + 1B):</strong> <span id="dpAB">0</span>%</p>
    <p style="color: #f39c12; font-weight: bold;"><strong>Doublet Cell A (2A + 0B):</strong> <span id="dpDoubleA">0</span>%</p>
    <p style="color: #f39c12; font-weight: bold;"><strong>Doublet Cell B (0A + 2B):</strong> <span id="dpDoubleB">0</span>%</p>
    <p style="color: #d73a49; font-weight: bold;"><strong>All Other Combos (Triplets+):</strong> <span id="dpMultiple">0</span>%</p>
  </div>
</div>

<script>
// Volume Logic
function calculateVolume() {
  let d = parseFloat(document.getElementById('dropDiameter').value);
  const unit = document.getElementById('dropDiameterUnit').value;
  
  // If mm is selected, convert to micrometers first to standardize the math
  if (unit === 'mm') {
    d = d * 1000;
  }
  
  const volUM3 = (Math.PI * Math.pow(d, 3)) / 6;
  const volPL = volUM3 / 1000;
  const volNL = volPL / 1000;
  
  document.getElementById('volPLOut').innerText = volPL > 10 ? volPL.toFixed(1) : volPL.toFixed(3);
  document.getElementById('volNLOut').innerText = volNL.toFixed(5);
  
  document.getElementById('volResults').style.display = 'block';
}

// Yield & Frequency Logic
function calculateYield() {
  let d = parseFloat(document.getElementById('dropDiaCount').value);
  const diaUnit = document.getElementById('dropDiaUnitCount').value;
  const flowRate = parseFloat(document.getElementById('flowRate').value);
  const flowRateUnit = document.getElementById('flowRateUnit').value;
  const time = parseFloat(document.getElementById('runTime').value);
  const timeUnit = document.getElementById('runTimeUnit').value;
  
  // Convert diameter to micrometers if mm is selected
  if (diaUnit === 'mm') {
    d = d * 1000;
  }
  
  // Calculate volume in cubic micrometers, then convert to picoliters
  const volUM3 = (Math.PI * Math.pow(d, 3)) / 6;
  const volPL = volUM3 / 1000;
  
  // Standardize Flow Rate to µL/min
  let flowRateULMin = flowRate;
  if (flowRateUnit === 'uL/hr') {
    flowRateULMin = flowRate / 60;
  }
  
  // Standardize Time to minutes
  let timeMin = time;
  if (timeUnit === 'hr') {
    timeMin = time * 60;
  }
  
  // Calculate Total Volume in µL, then convert to pL (1 µL = 1,000,000 pL)
  const totalVolUL = flowRateULMin * timeMin;
  const totalVolPL = totalVolUL * 1000000;
  
  // Total Droplets
  const totalDroplets = totalVolPL / volPL;
  
  // Generation Frequency (Hz) = total droplets / total seconds
  const timeSec = timeMin * 60;
  const frequencyHz = totalDroplets / timeSec;
  
  // Update UI
  document.getElementById('totalDropletsFormatted').innerText = totalDroplets.toLocaleString('en-US', {maximumFractionDigits: 0});
  document.getElementById('totalDropletsSci').innerText = totalDroplets.toExponential(2);
  document.getElementById('frequencyOut').innerText = frequencyHz.toLocaleString('en-US', {maximumFractionDigits: 0});
  
  document.getElementById('countResults').style.display = 'block';
}

// Poisson Logic
function factorial(n) {
  if (n === 0 || n === 1) return 1;
  for (var i = n - 1; i >= 1; i--) { n *= i; }
  return n;
}

function calculatePoisson() {
  const conc = parseFloat(document.getElementById('cellConc').value);
  const volInput = parseFloat(document.getElementById('dropVol').value);
  const volUnit = document.getElementById('dropVolUnit').value;
  
  // Convert based on selected unit to get volume in mL
  let volML = 0;
  if (volUnit === 'pL') {
    volML = volInput * 1e-9;
  } else if (volUnit === 'nL') {
    volML = volInput * 1e-6;
  }
  
  const lambda = conc * volML;
  const p0 = Math.exp(-lambda); 
  const p1 = lambda * Math.exp(-lambda); 
  const p2AndAbove = 1 - (p0 + p1); 
  
  document.getElementById('lambdaOut').innerText = lambda.toFixed(3);
  document.getElementById('p0').innerText = (p0 * 100).toFixed(1);
  document.getElementById('p1').innerText = (p1 * 100).toFixed(1);
  document.getElementById('p2').innerText = (p2AndAbove * 100).toFixed(1);
  
  document.getElementById('results').style.display = 'block';
}

// Double Poisson Logic
function calculateDoublePoisson() {
  const concA = parseFloat(document.getElementById('cellConcA').value);
  const concB = parseFloat(document.getElementById('cellConcB').value);
  const volInput = parseFloat(document.getElementById('dropVolDouble').value);
  const volUnit = document.getElementById('dropVolUnitDouble').value;
  
  let volML = 0;
  if (volUnit === 'pL') {
    volML = volInput * 1e-9;
  } else if (volUnit === 'nL') {
    volML = volInput * 1e-6;
  }
  
  const lambdaA = concA * volML;
  const lambdaB = concB * volML;
  
  // A Probabilities
  const p0_A = Math.exp(-lambdaA);
  const p1_A = lambdaA * Math.exp(-lambdaA);
  const p2_A = (Math.pow(lambdaA, 2) * Math.exp(-lambdaA)) / 2;
  
  // B Probabilities
  const p0_B = Math.exp(-lambdaB);
  const p1_B = lambdaB * Math.exp(-lambdaB);
  const p2_B = (Math.pow(lambdaB, 2) * Math.exp(-lambdaB)) / 2;
  
  // Combined
  const empty = p0_A * p0_B;
  const aOnly = p1_A * p0_B;
  const bOnly = p0_A * p1_B;
  const exactlyOneOfEach = p1_A * p1_B;
  const doubleA = p2_A * p0_B;
  const doubleB = p0_A * p2_B;
  
  // Everything else (Triplets, 2A+1B, etc.)
  const tripletsPlus = 1 - (empty + aOnly + bOnly + exactlyOneOfEach + doubleA + doubleB);
  
  // Update UI
  document.getElementById('lambdaAOut').innerText = lambdaA.toFixed(3);
  document.getElementById('lambdaBOut').innerText = lambdaB.toFixed(3);
  document.getElementById('dpEmpty').innerText = (empty * 100).toFixed(1);
  document.getElementById('dpAOnly').innerText = (aOnly * 100).toFixed(1);
  document.getElementById('dpBOnly').innerText = (bOnly * 100).toFixed(1);
  document.getElementById('dpAB').innerText = (exactlyOneOfEach * 100).toFixed(2);
  document.getElementById('dpDoubleA').innerText = (doubleA * 100).toFixed(2);
  document.getElementById('dpDoubleB').innerText = (doubleB * 100).toFixed(2);
  document.getElementById('dpMultiple').innerText = (tripletsPlus * 100).toFixed(2);
  
  document.getElementById('doubleResults').style.display = 'block';
}
</script>