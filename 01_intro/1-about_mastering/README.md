## 1.1 About Robot Mastering

- Mastering is a function used to improve robot motion accuracy by compensating for the mechanical zero (home) position of each axis.
- When the mechanical zero position is defined for the first time, mastering must be performed.

- After initial mastering, the mechanical zero position may change due to <br>
  factors such as axis twisting, replacement of drive components, or mechanical wear.
- In such cases, mastering must be performed again to restore accurate motion control.

- Mastering vs. Calibration
    - Mastering is the process of establishing the mechanical zero position that serves as the reference for coordinate calculations.
    - Calibration is the process of correcting positional errors while maintaining the established mechanical zero reference.
    - Calibration must always be performed after mastering has been completed.

- A digital contact sensor is used to operate the mastering in this manual.<br>
  The sensor is attached to each axis of the robot and detects the V-groove <br> while moving from -1.5 degrees to +1.5 degrees based on the starting point.<br>
  The detected V-groove position is corrected to the mechanical origin.<br><div>
<img src="../../_assets/12_mastering_concept_eng.PNG" style="max-width: 60vw"><br>
Fig 1.1. a. Starting point(axis distortion status), 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
b. V-groove detection during mastering
</div>
