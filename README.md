# Ario

This is the mechanical design for ATMoB's ARIO 10' diameter telescope
dome.  It was designed by Charlie Gettys in the spring of 2016, and
fabricated by Charlie & Jim Gettys and Bruce Berger.  Note that we are
currently designing a radio controlled motor controller as a companion
to this mechanical design.

The design opens or closes the dome slit in approximately 30 seconds in
ideal circumstances.

Note: the specified threaded rod was ordered by mistake: it is gross
overkill for the application; something much cheaper can/should be
bought rather than the precision rod currently specified in the as
built BOM. And the corresponding nut used should also be much cheaper.

It may take 50-100lbs force to start the slit of 10' dome ATMoB
has; we may decide to improve the cable path on our dome using pully
sheaves (as many of the later versions of that dome already have
improved designs) to reduce the required force.

The clutch in the design should prevent over stressing of the cable.
The cable has an operating strength of about 90lbs, with a breaking
strength about five times higher.  The motor was sized to provide enough
torque to produce about 100lbs of force given the diameter of the
threaded rod.

The design could be adapted/scaled up for much larger dome slits or
roll off roofs, by choosing other motors or changing the gear ratio in
the drive.  The gearing used with the motor was deliberately chosen to
have that flexibility, and the motor itself is available in different
sizes.  The components are easily available and "standard" among the
FIRST robotics community.

There is a included spreadsheet for making the torque
computations. Note that the motor, gear box, cable and threaded rod
all interact to produce the desired speed and force to move the dome
slit.

This design could be scaled up by using larger threaded rods and cables.
The force and closing speed can also be changed over a significant range
by changing the gearing in the gear box.  The ARIO gear design order
is documented in the file "motorspec.txt".

At maximum torque, you should not choose a motor that will generate
more force than the operating strength of the chosen cable. The clutch
is intended to provide a "fail safe" such that the breaking strength
of the cable will never be reached.

At maximum torque of one of these motors, you may need to provide
significant current; 55 amps@12V for the chosen motor in the ARIO design.

We are currently designing a radio controlled remote dome motor
controller to go with this mechanical design to replace our existing
current limited power supply (which cannot provide enough current),
which will be driven by a deep cycle marine battery charged by a solar
panel on the dome, to avoid needing power transfer to the dome, which
may not be designed into most smaller domes. A battery can easily
provide the needed current for the limited time to open or close the
dome more easily than a power supply.


