# 4_Axis_LinuxCNC
A working example of a dual parallel port card setup for controlling a 4 Axis CNC Mill on Linux

1) Address 0cc00 is the one determined by trial and error, using
   stepconf, as working for the second parallel port card. 

2) Be sure to add the existing lpr and parport modules to the
   system blacklist. 

3) net astep           => parport.1.pin-04-out
   setp parport.1.pin-04-out-reset 1
   net adir            => parport.1.pin-05-out

   I arrived at these pins connections for the A axis by first testing a stepper 
   motor against the Y axis of my first 4-axis driver board using
   parport 0, the built-in parallel port, then the same stepper 
   against the Y axis of my second 4-axis driver also using parport 0.

   Finally, I tried each port address for the parallel port card I 
   added to the computer, parport 1, until I found the correct address.
