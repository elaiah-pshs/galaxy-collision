# `evolve_two_disk()`

Calculates the position and motion of two galaxies and their stars as they interact with each other

## Parameters:
- `primary`: first galaxy to evolve
- `secondary`: second galaxy to evolve
- `time_step`: time duration in the real world in between snapshots
- `N_steps`: number of time steps to consider and compute for
- `N_snapshots`: number of time steps to take a picture of

## Procedure

1. Create a new variable that stores a number equivalent to `time_step` expressed in seconds

2. Obtain necessary information about the galaxies (listed below) in standard SI units
    * bulge radii
    * number of stars
    * masses
    * cartesian coordinates of galactic centre
    * velocity of galaxy, expressed as a cartesian vector
    * cartesian coordinates of stars
    * velocities of stars, expressed as a cartesian vector

3. Set up an array to store all snapshots
    * A snapshot is an array that contains all the coordinates of the galactic centres and all stars in both galaxies at a given point in time.

4. Generate every snapshot and add it to `snapshots`
    * Get the distances of ths stars from the two galactic centres
    * Update the velocities of the stars based on their distance to the two centres as derived previously
    * Update the positions of the stars based on their new velocities
    * Get the distance between the two galactic centres
    * Get the gravitational acceleration induced by the larger galaxy on the smaller galaxy
    * Update the velocities of the galactic centres based on the computed acceleration
    * Update the positons of the galactic centres based on their computed velocities
    * Add all the snapshot information to a list, then add that list to `snapshots`

5. Generate an array containing the timestamps of the snapshots

6. Return `time` and `snapshots`, expressed in megayears and kiloparsecs respectively
