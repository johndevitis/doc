# Model Creation

## Bearings
The manner in which bearings are modeled is dependent on the level of detail to be included in the model. If the substructure is to be included in the model, or otherwise structural elements included that are connected by a bearing, the bearing should be explicitly modeled as detailed below. Otherwise the bearings may be modeled with boundary conditions (i.e. node restraint and node stiffness).
### Elastomeric Bearings
Elastomeric bearings are composed of vulcanized rubber, often compositely layered with thin steel plates to increase stability. The purpose of these bearings is to allow differential movement of the components it is connecting. The vertical stiffness of elastomeric bearings is very high compared to the lateral (shear) stiffness. In addition is preloaded under dead load, and thus will allow for virtually no vertical translation. If the bearings are to be explicitly modeled they may be done in the following manner:

1. Create nodes at the top and bottom of the bearing if they do not already exist, and ensure these nodes are appropriately connected to the adjacent components (via rigid links).
2. Connect nodes with Spring-Damper beam element. Apply proper stiffness to the lateral torsion. If the material stiffness is unknown, sensitivity studies should be performed to understand and bound the possible stiffness values. Axial and torsional stiffness may be specified if known. However, most often it is appropriate to leave the torsional stiffness at zero. The axial stiffness may be set to an infinitely high value (such that the structure experiences no axial deformation of the elastomeric bearing). Alternatively the axial stiffness may be set to zero, and instead utilize a link to provide vertical rigidity.
3. Connect nodes with a pinned link if the axial stiffness of the spring-damper elements is set to zero. This link will release rotational degrees of freedom between the nodes, but provide infinite vertical stiffness.

![Spring-damper element](/Images/SpringElement.png)

Using these methods, the modeled bearing can move laterally in both directions with resistance as specified by the lateral stiffness of the spring-damper element. It will not experience any vertical deformation.

### Rocker Bearings
Rocker bearings are steel sections that have a curved bottom flange, allowing the bearing to "rock" back and forth and thus giving the supported component freedom to translate longitudinally. The modeled connection meant to simulate this type of bearing should allow for free translation in one direction, and prohibit translation in any other direction.

A rigid link can accommodate these requirements if a rigid link for a single plane is used.

![Rigid Link in Single Plane](/Images/RockerLink.png)

The plane selected should be normal to the direction the supported components (e.g. If the girders run longitudinally along the Z-axis, the XY plane should be selected for the rigid link). The link will act like an infinitely rigid beam for any differential movement between the components in the selected plane, but will allow longitudinal translation.

### Fixed Bearings
Fixed bearings are often just steel pedestals (e.g. short I-sections) that are bolted between the connected components. This type of connection can be modeled as a rigid connection, and thus rigid links (XYZ) can be used.
If the flexibility of the connection is thought to be significant and influential, the bearings may be modeled as described for elastomeric bearings, or by explicitly modelling the pedestal as a beam element.
