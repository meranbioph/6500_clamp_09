Case clamp_09 is a re-hash of clamp_08, with a coarser mesh and with adjustTimeStep on.

OpenFoam version: 9

Solver: clampPimpleFoam v3

MESH
- The base mesh was built with the crude R program previously built.
- The cover region was expanded to 0.15m.
  - This means the cover D and F numbers need to be recalculated (1.1 / 150 * D and 1.1 / 150 * F)
- The outer domain was reduced in height by 2 meters.
Note that to get the merge patches to work, their order had to be changed from clamp_08.


ADJUST TIME STEP
The adjustTimeStep is turned on. This significantly speeds up the simulation.
An intital 2 seconds of simulation are run with a fixed timeStep of 0.002 just to get a more stable starting point.
- use controlDict_start
Then 60 minutes of simulation is run using the adjustTimeStep, with write every 60 seconds.
- use controlDict_long
- coMax is set to 0.6 and seems to work.
