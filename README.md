# SensorCalibration
This project simulates an automated calibration process for an oxygen concentration sensor.  Known gas concentrations are introduced, readings are sampled, and the input range is adjusted using math operations to ensure accurate sensor scaling.

Link to video of operation: https://youtu.be/nr6_XlnM7x0

Link to video of operation with HMI Implementation https://youtu.be/mbDPy-Tj9Yw

This video focuses on demonstrating the calibration process in action. I don’t go in-depth on every piece of logic here — that would take a while — but if you're interested in the full logic and structure behind it, feel free to check out the included PDFs for the project description and ladder logic. You could also download the .rss file if you'd like but be aware it may not work properly in environments other than Logix500. 

--Side Note-- I've not programmed an edge case scenario where the sensor is stuck reading the same number for each calibration phase.  Meaning it's detecting 0% o2 as the same as 30% o2 during calibration.  That would fault the program because if phase1avg>=phase2avg, our math would give us a new input min greater than the new input max, which is impossible.  It is something I have considered and will loop back to implement when I have a bit more time.  Some condition like "if phase 1 sample average >= phase 2 sample average, then run abort protocol" or something similar would likely work. 
