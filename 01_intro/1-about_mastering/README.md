## 1.1 About Robot Mastering

- Mastering is a function used to improve robot motion accuracy by compensating for the mechanical zero (home) position of each axis.
- When the mechanical zero position is defined for the first time, mastering must be performed.

- After initial mastering, the mechanical zero position may change due to 
  factors such as axis twisting, replacement of drive components, or mechanical wear.
- In such cases, mastering must be performed again to restore accurate motion control.

- Mastering vs. Calibration
    - Mastering is the process of establishing the mechanical zero position that serves as the reference for coordinate calculations.
    - Calibration is the process of correcting positional errors while maintaining the established mechanical zero reference.
    - Calibration must always be performed after mastering has been completed.

- A digital contact sensor is used to operate the mastering in this manual.
  The sensor is attached to each axis of the robot and detects the V-groove while moving from -1.5 degrees to +1.5 degrees based on the starting point.
  The detected V-groove position is corrected to the mechanical origin.

<br>

<figure style="text-align: left; width: 100%; margin: 0;">
  <img src="../../_assets/12_mastering_concept_eng.PNG" style="width: 500px; margin-left: 70px;" alt="Mastering Concept">
  
  <figcaption style="font-size: 0.9em; margin-left: 0px; white-space: nowrap;">
    Fig 1.1. a. Starting point(axis distortion status), b. V-groove detection during mastering
  </figcaption>
</figure>
