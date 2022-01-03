## Summary

This is the test instruction for IFC4x3_AbRV-E1a-ALSE - Alignment Superelevation & Width.

The test instruction includes:

- A basic project structure setup including units and global positioning
- An alignment structure for a road including the horizontal and vertical layouts
- Assignment of superelevation- and width events along the alignment geometry using linear placement marking the locations where these design parameters change and the values of these design parameters

The data comes from, and is a simplified version of, the IFC Infra Unit Test [MCON-2](https://github.com/bSI-InfraRoom/IFC-infra-unit-test/tree/main/MCON-2) which in turn is extracted from the IFC Rail [Level Crossing storyline](https://github.com/IFCRail/IFC-Rail-Unit-Test/tree/master/8_Storylines%20Test%20(SL)/SL08_Level%20Crossing). 

## Itemised Roots
The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

- IFC Entities
    - *IfcProject*
      - *IfcSite*
      - *IfcRoad*
      - *IfcFacilityPart*
      - *IfcAnnotation*
      - *IfcAlignment*
      - *IfcAlignmentHorizontal*
      - *IfcAlignmentVertical*
      - *IfcAlignmentSegment*
      - *IfcAlignmentHorizontalSegment*
      - *IfcAlignmentVerticalSegment*
      - *IfcContext*
      - *IfcPropertySet*
      - *IfcPropertySingleValue*
      - *IfcPropertyEnumeratedValue*


- Concept Templates
    - *Project Units*
    - *Project Representation Context*
    - *Project Global Positioning*
    - *Spatial Decomposition*
    - *Spatial Composition*
    - *Spatial Container*
    - *Product Local Placement*
    - *Product Linear Placement*
    - *Property Sets for Objects*
    - *Alignment Decomposition*
    - *Alignment Geometry Gradient*

## Variations
The Following occurence variations need to be checked and certified in relation to the targeted entities and concept templates:

- IfcAnnotation/SUPERELEVATIONEVENT - *Pset_SuperElevation needs all variants of Side and TransitionSuperelevation tested. Furthermore, values for Superelevation shall include both positive and negative values*
- IfcAnnotation/WIDTHEVENT - *Pset_Width needs all variants of Side and TransitionWidth tested.*


## Usages
The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

- IfcAnnotation/SUPERELEVATIONEVENT
    - *Each superelevation event shall have a linear placement relative to the alignment curve*
    - *Each superelevation event shall have one instance of Pset_Superelevation attached*
    - *Each instance of Pset_Superelevation shall have values for properties Side, Superelevation and TransitionSuperelevation*

IfcAnnotation/WIDTHEVENT

- *Each width event shall have a linear placement relative to the alignment curve*
- *Each width event shall have one instance of Pset_Width attached*
- *Each instance of Pset_Superelevation shall have values for properties Side, NominalWidth and TransitionWidth*

The Test case requires the following additional checks related to Model Geometry:

- *Constraint*


## Model Dataset
This test case utilises the attached dataset documented by the following drawings and data schedule. 

Synopsis:

- IfcProject

  - IfcGeometricRepresentationContext

    - IfcMapConversion
      - IfcProjectedCRS

  - IfcSite

    - IfcAlignment
      - Should have straights, clothoid/circular arc to the left and to the right
      - Vertical is not really needed but is probably part of the included E1-ALRF

    - IfcRoad
      - IfcFacilityPart/ROADSEGMENT
        - IfcFacilityPart/CARRIAGEWAY
          - IfcAnnotation/SUPERELEVATIONEVENT (one for every start of alignment element)
            - Pset_Superelevation (left side)
            - IfcLinearPlacement
          - IfcAnnotation/SUPERELEVATIONEVENT (one for every start of alignment element)
            - Pset_Superelevation (right side)
            - IfcLinearPlacement
          - IfcAnnotation/WIDTHEVENT (one at start, add a narrowing of the road somewhere along the alignment)
            - Pset_Width (both)
            - IfcLinearPlacement

*This is a later step tha involved the detailed documentation of the certification dataset (model)*


## Drawings (Visualisations)
The following Drawings and visualisations describe the test case dataset to be modelled and certified.


## Supporting files

| Filename                          | Description                               |
|-----------------------------------|-------------------------------------------|
| *filename*                        | *short description*                       |