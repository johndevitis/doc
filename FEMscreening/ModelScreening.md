## Model Error Screening

Some of the first steps to error screening involve carefully looking at the geometry to make sure it is consistent with drawings or whatever information source is being used. Once the creator is reasonably confident in the model, they can begin to use other tools and techniques.
The first of these are the geometry tools provided by Strand7. The following buttons allow the user to identify any lapses in connectivity between elements.

![Free Ends and Edges](Images/Buttons.png)

The bottom seven buttons will highlight free ends of elements. The image below shows the result of displaying plate free edges:

![Plate Free Edges](Images/PlateFreeEdges.png)

Only the edges of the deck are free, as indicated by the yellow outline. If edges were highlighted in the interior of the deck, this would indicated there is a geometry mismatch that should be rectified. A similar process can be performed on links, beam elements, and brick elements.

Once the creator is confident the geometry of their model is correct, analysis may be utilized to further error screen the model.

1. A natural frequency analysis shall be performed on the completed model. The first several modes shall be examined for local deformations which suggest discontinuities or improper stiffness assignments. Sufficient number of modes shall be analyzed such that at least 4 global modes are identified.
2. The deflected shape under multiple load cases (dead load and live load) shall be examined for atypical behavior (e.g. nonsymmetrical deformation, unintended breaks or discontinuities).
3. When further error screening is deemed necessary (recommended for any manually constructed model) the following procedures may be performed:
  1. Manual calculation of structure weight shall be compared to the sum of dead load vertical reactions.
  2. FE responses (e.g. deflection, moment, etc.) under simple load cases shall be compared to the corresponding theoretical responses for single line girder models (i.e. approximate analysis)
