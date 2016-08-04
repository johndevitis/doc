# Model Changes
## Swap Rocker Bearing Locations

The rocker bearings are on the other 4 girders.

![Center Pier Links](Images/CenterPierLinks.png)

## Model Rocker Bearings with XY Rigid Links
The pinned bearings used, release all rotational degrees of freedom. This is not a realistic representation of the true behavior of a rocker bearing. A rigid link in the XY plane will more properly release longitudinal translation. Furthermore, these new links should only extend from the bottom of the I-girder to the top of the box-girder. New nodes with rigid links to the component center nodes may need to be created to accomplish this.

![Rocker Link](Images/RockerLink.png)

## Model Elastomeric Bearings Differently

New nodes will need to be created at the bottom of the I-section girder (there appears to be a node already at the top of the box girder).

![Bearing Locations](Images/BearingLocation.png)

Existing node stiffness should be removed. This method of simulating a flexible connection between components is incorrect.

![Node Stiffness](Images/NodeStiffness.png)

Rigid links will have to be modified such that they go from the center of the I-section girder to the bottom node, and the center of the box girder to the top node. The two nodes (girder bottom and box-girder top) will be connected with a pinned link and a spring-damper element.

![Spring-damper element](Images/SpringElement.png)

The same process should be completed on the elastomeric bearings between the pier columns and the box-girder.
