## 1.1 About Robot Mastering

<div style="width: 630px; line-height: 1.5; word-break: keep-all;">
  <ul style="margin: 0; padding-left: 20px;">
    <li>Mastering improves robot accuracy by compensating for the mechanical zero position of each axis.</li>
    <li>It must be performed when the mechanical zero is first defined or changes due to axis twisting, component replacement, or wear.</li>
    <li><strong>Mastering vs. Calibration</strong>
      <ul style="list-style-type: circle; padding-left: 20px;">
        <li>Mastering: Establishes the mechanical zero reference for coordinate calculations.</li>
        <li>Calibration: Corrects positional errors based on the established zero.</li>
        <li>Calibration must always follow mastering.</li>
      </ul>
    </li>
  </ul>

  <br>

  <div style="width: 630px; margin: 10px 0; background-color: #fcfcfc; padding: 5px 0;">
    This manual uses a <strong>digital contact sensor</strong> for mastering. The sensor, attached to each axis, detects the V-groove by moving within a range of <strong>-1.5° to +1.5°</strong> from the starting point. The detected V-groove position is then corrected to the mechanical origin.
  </div>
</div>

<br>

<figure style="text-align: left; width: 100%; margin: 0;">
  <img src="../../_assets/12_mastering_concept_eng.PNG" style="width: 630px; margin-left: 25px;" alt="Mastering Concept">
  
  <figcaption style="font-size: 0.9em; margin-left: 0px; white-space: nowrap;">
    Fig 1.1. a. Starting point(axis distortion status), b. V-groove detection during mastering
  </figcaption>
</figure>
