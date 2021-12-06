# Alignment Reference Super Elevation Exchange

**Coding** - E1b   
**Abreviation** - ARSE

## Summary
TBC
# Test instructions


|       Test Case title     | Code | Abbreviation | Author | Data Owner |
|:-------------------------:|:----:|:------------:|:------:| :---------:|
|  Alignment Reference Superelevation (+ Width) | E1a1 | ARSE | Lars Wikström | FTI? |

## Summary (intent)

<details><summary>click to expand</summary> 

This test case uses road alignments and IfcAnnotation predefined types to specify superelevation and width design parameters along the alignment to test the following capabilities:
- Project Global Positioning
- Simple Road spatial structure
- Road alignment
- Linear placement along alignment
- Properties of objects

The business context for the test is provided by a ?km portion of road, including: 2 alignments. 

### Test instructions (**high-level**, <ins>**not necessarily in this order**</ins>)

1. Model project breakdown structure (spatial structure)
1. Model alignment(s)
1. Geo-reference model
1. Model annotations including linear placement along alignment
1. Model properties of annotations
1. Assign objects to project breakdown

</details>

---

## Itemised Roots

<details><summary>click to expand</summary> 

The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary> 

  - IfcProject
  - IfcSite
  - IfcRoad
  - IfcFacilityPart
  - IfcAnnotation

  - IfcRelContainedInSpatialStructure
  - IfcRelDefinesByProperty
  - IfcRelNests

  - IfcAlignment
  - IfcAlignmentHorizontal
  - IfcAlignmentVertical
  - IfcAlignmentSegment
  - IfcAlignmentHorizontalSegment
  - IfcAlignmentVerticalSegment

  - IfcContext

  - IfcPropertySet
  - IfcPropertySingleValue
  - IfcPropertyEnumeratedValue

  - ... (to be continued)

</details>

<details><summary>Concept Templates</summary> 

  - Object Composition
     - Alignment Decomposition
     - Spatial Decomposition
  - Object definition
     - Property Sets for Objects
     - Property Sets for Types
  - Product Shape
     - Product Geometric Representation
       - Alignment Geometry
         - Alignment Geometry Gradient
     - Product placement
       - Product Linear Placement
       - Product Local Placement
  - Project Context
     - Project Global Positioning
     - Project Representation Context
     - Project Units
       </details>

</details>

---

## Variations

<details><summary>click to expand</summary>

The Following occurrence variations need to be checked and certified in relation to the targeted entities and concept templates:

- Entity_01 - *description of variation*
- Entity_02 - *description of variation*

</details>

## Usages

<details><summary>click to expand</summary> 

The following itemised restrictions and constraints shall be placed on IFC Entities & Concept Templates:

:construction: under construction :construction:

- IfcSomething
    - *Constraint*

The Test case requires the following additional checks related to Model Geometry:

- *Correspondence between the business-logic and the geometry parts for all segments*
- *Tangential continuity of alignemnt segments. Tolerance of ... millimetres*
- ... (to be continued)

</details>

---

## Model Dataset

<details open><summary>click to expand</summary> 

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. Form more details on each item see [Dataset description](Dataset/README.md).

| ID   | Filename          | Type (format) | Description                                                  |
| ---- | ----------------- | ------------- | ------------------------------------------------------------ |
|      | *filename + link* | csv           | Alignment parameters for horizontal segments                 |
|      | *filename + link* | csv           | Alignment parameters for vertical segments                   |
|      | *filename + link* | LandXML       | Alignment LandXML file, not including cant                   |
|      | Filename + link   | figure (jpg)  | Schematic layout (long section) of the test case including superelevation and width parameters |


</details>

---

## Expected Results

<details><summary>click to expand</summary> 

Considering the aim of this test, the expected results are:

:construction: under construction :construction:

1. N. 1 IFC file containing the information as requested
2. Screen-shot of ...

</details>

---

## Validation criteria
:warning: <ins>For this test case to be considered passed **all capabilities** listed in this section shall be verified, with no exception.</ins> :warning:

:construction: under construction :construction:

<details><summary>General</summary>

:construction: under construction :construction:

- All the concept templates must be correctly used
- At least 1 instance of each entity listed in [Itemised Roots](#Itemised-Roots) is present in the file

</details>

<details><summary>Linear Placement of Superelevations and widths</summary> 


For the **Linear placement of superelevations and widths** capability, the test is considered passed if **all** the following validation criteria are satisfied.

| **ID** | **CRITERIA**                             | **VALUE** | **COMMENT**                                                  |
| ------ | ---------------------------------------- | --------- | ------------------------------------------------------------ |
|        | Nr of superelevation annotations in file | 3         | The superelevations shall be represented as IfcAnnotation with PredefinedType=.SUPERELEVATIONEVENT. |
|        | Nr of width annotations in file          | 3         | The superelevations shall be represented as IfcAnnotation with PredefinedType=.WIDTHEVENT. |
|        | Placement of superelevation              | xxx       |                                                              |
|        | Placement of width                       | xxx       |                                                              |

NOTES:
-	Xxx

<details><summary> Properties for superelevation and width </summary>

Planning 3 instances of each annotation type...

| Id   | Entity        | Entity Type         | PropertySet Name    | Property Name            | Property Value Type         | List Of Values | IfcSimpleProperty subtype  |
| ---- | ------------- | ------------------- | ------------------- | ------------------------ | --------------------------- | -------------- | -------------------------- |
| 1    | IfcAnnotation | SUPERELEVATIONEVENT | Pset_Superelevation | Side                     | IfcLabel                    | xxx            | IfcPropertyEnumeratedValue |
| 1    | IfcAnnotation | SUPERELEVATIONEVENT | Pset_Superelevation | Superelevation           | IfcRatioMeasure             | xxx            | IfcPropertySingleValue     |
| 1    | IfcAnnotation | SUPERELEVATIONEVENT | Pset_Superelevation | TransitionSuperelevation | IfcLabel                    | xxx            | IfcPropertyEnumeratedValue |
| 2    | IfcAnnotation | WIDTHEVENT          | Pset_Width          | Side                     | IfcLabel                    | yyy            | IfcPropertyEnumeratedValue |
| 2    | IfcAnnotation | WIDTHEVENT          | Pset_Width          | NominalWidth             | IfcNonNegativeLengthMeasure | yyy            | IfcPropertySingleValue     |
| 2    | IfcAnnotation | WIDTHEVENT          | Pset_Width          | TransitionWidth          | IfcLabel                    | yyy            | IfcPropertyEnumeratedValue |
|      |               |                     |                     |                          |                             |                |                            |

</details>

</details>

<details><summary>Project Global Positioning</summary>

| **ID** | **CRITERIA**                                                 | **VALUE** / **COMMENT** |
| ------ | ------------------------------------------------------------ | ----------------------- |
|        | The project geometric context shall be associated with an IfcMapConversion with the TargetCRS set to an IfcProjectedCRS. Attributes for these specified below. | 0                       |

| Entity           | Attribute        | Value                                    |
| ---------------- | ---------------- | ---------------------------------------- |
| IfcMapConversion | SourceCRS        | Project geometric context                |
| IfcMapConversion | TargetCRS        | Reference to IfcProjectedCRS (See below) |
| IfcMapConversion | Eastings         | xxx                                      |
| IfcMapConversion | Northings        | xxx                                      |
| IfcMapConversion | OrthogonalHeight | xxx                                      |
| IfcMapConversion | XAxisAbscissa    | xxx                                      |
| IfcMapConversion | XAxisOrdinate    | xxx                                      |
| IfcMapConversion | Scale            | xxx                                      |
| IfcMapConversion | ScaleY           | xxx                                      |
| IfcMapConversion | ScaleZ           | xxx                                      |
| IfcProjectedCRS  | Name             | yyy                                      |
| IfcProjectedCRS  | Description      | yyy                                      |
| IfcProjectedCRS  | GeodeticDatum    | yyy                                      |
| IfcProjectedCRS  | VerticalDatum    | yyy                                      |
| IfcProjectedCRS  | MapProjection    | yyy                                      |
| IfcProjectedCRS  | MapZone          | yyy                                      |
| IfcProjectedCRS  | MapUnit          | yyy                                      |

</details>

<details><summary>Road spatial structure</summary>


:construction: under construction :construction:

- **Concept Template**: Spatial Decomposition
- **Usage** (if existing): NA

| Parent Element | Parent Element Type | Minimum | Maximum | Child Element | Child Element Type |
| -------------- | ------------------- | ------- | ------- | ------------- | ------------------ |
| IfcSite        |                     | 1       | 1       | IfcRoad       |                    |
| IfcRoad        |                     |         |         |               |                    |

</details>

<details><summary>Spatial containment</summary>

:construction: under construction :construction:

- **Concept Template**: Spatial Containment
- **Usage** (if existing): NA

| Spatial Element | Spatial Element Type | Minimum | Maximum | Element       | Element Type        |
| --------------- | -------------------- | ------- | ------- | ------------- | ------------------- |
| IfcSite         |                      | 1       | 1       | IfcAlignment  |                     |
| IfcRoad         |                      | 3       | 3       | IfcAnnotation | SUPERELEVATIONEVENT |
| IfcRoad         |                      | 3       | 3       | IfcAnnotation | WIDTHEVENT          |

</details>
