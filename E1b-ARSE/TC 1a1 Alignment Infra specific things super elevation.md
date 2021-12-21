## Summary

This is the test instruction for TC 1a1 Alignment Infra specific things: super elevation.

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

- IfcSomething
    - *Constraint*


The Test case requires the following additional checks related to Model Geometry:

- *Constraint*


## Model Dataset
This test case utilises the attached dataset documented by the following drawings and data schedule. 

*This is a later step tha involved the detailed documentation of the certification dataset (model)*


## Drawings (Visualisations)
The following Drawings and visualisations describe the test case dataset to be modelled and certified.


## Supporting files

| Filename                          | Description                               |
|-----------------------------------|-------------------------------------------|
| *filename*                        | *short description*                       |