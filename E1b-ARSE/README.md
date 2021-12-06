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
     - ... (to be continued)
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

| ID | Filename                                                        | Type (format)  | Description                               |
|----|-----------------------------------------------------------------|----------------|-------------------------------------------|
|    | *filename + link*                                               | csv            | Alignment parameters for horizontal segments |
|    | *filename + link*                                               | csv            | Alignment parameters for vertical segments |
|    | *filename + link*                                               | csv            | Alignment parameters for cant segments |
|    | *filename + link*                                               | LandXML        | Alignment LandXML file, not including cant  |
|    | *filename + link*                                               | dwg            | Alignment dwg file, not including cant  |
|    | [Line_layout](Dataset/Line_layout.jpg)                                | figure (jpg)   | Schematic layout of the test case railway line |
|    | [Objects overview](Dataset/ObjectsOverview.png)         | diagram (png)  | Objects overview: a diagram + table describing the main to be used for the test case |
|    | *filename + link*                                               | drawing (pdf)  | Cross section example |
|    | *filename + link*                                               | drawing (dwg)  | Cross section example |
|    | *filename + link*                                               | drawing (PDF)  | Turnout drawing to be used as example |


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


| ID   | CRITERIA                           | VALUE                                                        |
| ---- | ---------------------------------- | ------------------------------------------------------------ |
|      | Pset name used for superelevation  | "Pset_Superelevation"                                        |
|      | Pset name used for width           | "Pset_Width"                                                 |
|      | Property values for superelevation | "Side" = xxx<br />"Superelevation" = yyy<br />"TransitionSuperelevation" = zzz |
|      | Property values for width          | "Side" = xxx<br />"TransitionWidth" = yyy<br />"NominalWidth" = zzz |

</details>

<details><summary> Alignment 2 </summary>

| ID | CRITERIA                                                           | VALUE          |
|----|--------------------------------------------------------------------|----------------|
|    | Starting point Horizontal  - Mileage (pk)                          | 0+510.011      |
|    | Starting point Horizontal  - DistAlong                             | 0.000          |
|    | Starting point Horizontal  - X                                     | 451,296.6992   |
|    | Starting point Horizontal  - Y                                     | 4,538,798.8214 |
|    | Starting point Vertical  - Mileage                                 | 0+510.011      |
|    | Starting point Vertical  - Z                                       | 36.76035       |
|    | Ending point Horizontal  - Mileage (pk)                            | 47+271.7631    |
|    | Ending point Horizontal  - DistAlong                               | 46,761.7521    |
|    | Ending point Horizontal  - X                                       | 479,666.2177   |
|    | Ending point Horizontal  - Y                                       | 4,554,675.8253 |
|    | Ending point Vertical  - Mileage                                   | 47+271.7631    |
|    | Ending point Vertical  - Z                                         | 121.0179       |
|    | Total 2D length of alignment (horizontal projection)               | 46,761.7521    |
|    | Total 3D length of alignment                                       | 46,765.4520    |
|    | Hight difference between start and end point of alignment 3D curve | -84.2575       |

</details>

</details>

<details><summary>Object grouping</summary>

For the **Object grouping** capability, the test is considered passed if **all** the following validation criteria are satisfied.

The validation procedure must verify that a group of the requested type is grouping (via `IfcRelAssignsToGroup`) exactly a given number of objects of the requested type, no more and no less.

- **Concept Template**: Group Assignment
- **Usage** (if existing): NA

| Group    | Group Type                          | Minimum | Maximum | Object             | Object Type          |
|----------|-------------------------------------|---------|---------|--------------------|----------------------|
| IfcGroup | Binari di corsa (Contenitore)       | 1       | 1       | IfcFacilityPart    | TRACKSTRUCTURE       |
| IfcGroup | Deviatoi/Intersezioni (Contenitore) | 1       | 1       | IfcActuator        | Manovra deviatoio    |
| IfcGroup | Deviatoi/Intersezioni (Contenitore) | 1       | 1       | IfcElementAssembly | TURNOUTPANEL         |
| IfcGroup | Massicciata (Contenitore)           | 2       | 2       | IfcCourse          | BALLASTBED           |
| IfcGroup | Rotaie (Contenitore)                | 3       | 3       | IfcGroup           | Segmento di rotaia   |
| IfcGroup | Segmento di rotaia                  | 2       | 2       | IfcRail            | RAIL                 |
| IfcGroup | Traverse (Contenitore)              | 3       | 3       | IfcGroup           | Segmento di traverse |
| IfcGroup | Segmento di traverse                | 1       |         | IfcTrackElement    | SLEEPER              |

NOTE:
- for typing of groups refer to the Validation criteria of the **Object typing** capability
- when **Minimum** and **Maximum** have the same value, it means exactly. Example: Minimum=Maximum=2, means that the group must group exactly 2 objects of the requested type.
- when **Maximum** is empty, it means unlimited. Example: Minimum=1; Maximum=empty, means that the group must group 1 or more elements of the requested type.

</details>

<details><summary>Object typing</summary>

For the **Object typing** capability, the test is considered passed if **all** the following validation criteria are satisfied.

The validation procedure must verify that an IFC entity type with the given Name is typing (via `IfcRelDefinesByType`) exactly a given number of objects of the requested Name, no more and no less.

- **Concept Template**: Object Typing
- **Usage** (if existing): NA

| Entity Type     | Entity Type Name                    | Minimum | Maximum | IfcObject       | IfcObject Name                      |
|-----------------|-------------------------------------|---------|---------|-----------------|-------------------------------------|
| IfcTypeObject   | Binari di corsa (Contenitore)       | 1       | 1       | IfcGroup        | Binari di corsa di Foligno          |
| IfcTypeObject   | Deviatoi/Intersezioni (Contenitore) | 1       | 1       | IfcGroup        | Deviatoi                            |
| IfcTypeObject   | Massicciata (Contenitore)           | 1       | 1       | IfcGroup        | Massicciata                         |
| IfcTypeObject   | Rotaie (Contenitore)                | 1       | 1       | IfcGroup        | Rotaie                              |
| IfcTypeObject   | Traverse (Contenitore)              | 1       | 1       | IfcGroup        | Traverse                            |
| IfcActuatorType | Manovra deviatoio                   | 1       | 1       | IfcActuator     | Cassa di manovra CM04               |
| IfcCourseType   | Segmento di massicciata             | 1       | 1       | IfcCourse       | Segmento di massicciata M01         |
| IfcCourseType   | Segmento di massicciata             | 1       | 1       | IfcCourse       | Segmento di massicciata M02         |
| IfcTypeObject   | Segmento di rotaia                  | 1       | 1       | IfcGroup        | Segmento di rotaia R01              |
| IfcTypeObject   | Segmento di rotaia                  | 1       | 1       | IfcGroup        | Segmento di rotaia R02              |
| IfcTypeObject   | Segmento di rotaia                  | 1       | 1       | IfcGroup        | Segmento di rotaia R03              |
| IfcTypeObject   | Segmento di traverse                | 1       | 1       | IfcGroup        | Segmento di traverse T01            |
| IfcTypeObject   | Segmento di traverse                | 1       | 1       | IfcGroup        | Segmento di traverse T02            |
| IfcTypeObject   | Segmento di traverse                | 1       | 1       | IfcGroup        | Segmento di traverse T03            |
| IfcTypeObject   | Binari di corsa                     | 1       | 1       | IfcFacilityPart | Binario IV dispari - Orte Falconara |

NOTE:
- when **Minimum** and **Maximum** have the same value, it means exactly. Example: Minimum=Maximum=1, means that the entity type must type exactly 1 object with that Name.

</details>

<details><summary>Object decomposition (assemblies)</summary>

:construction: under construction :construction:

- **Concept Template**: Element Decomposition
- **Usage** (if existing): NA

| Assembly           | Assembly Type | Minimum | Maximum | Element         | Element Type |
|--------------------|---------------|---------|---------|-----------------|--------------|
| IfcElementAssembly | TURNOUTPANEL  | 1       | 1       | IfcFastener     | WELD         |
| IfcElementAssembly | TURNOUTPANEL  | 1       | 1       | IfcTrackElement | FROG         |
| IfcElementAssembly | TURNOUTPANEL  | 1       | 10      | IfcRail         | RAIL         |
| IfcElementAssembly | TURNOUTPANEL  | 1       | 2       | IfcRail         | CHECKRAIL    |
| IfcElementAssembly | TURNOUTPANEL  | 52      | 52      | IfcTrackElement | SLEEPER      |

</details>

<details open><summary>Object classification via external reference (i.e., bSDD)</summary>
:construction: under construction :construction:

- **Concept Template**: Classification Association
- **Usage** (if existing): NA

All the sleepers (IfcTrackElement.SLEEPER) must be classified using the correspondent classification inside the bSDD (buildingSMART Data Dictionary). The example below shows how the classification is expected to be done.

Given two sleepers

> `#21 = IFCTRACKELEMENT('0$kRFU7b50rP3_$BI9iljk', #1, 'Sleeper Z20#0001', 'Sleeper', $, #368035, #368038, $, .SLEEPER.);`
>
> `#22 = IFCTRACKELEMENT('00sqkYXHv4OfDNJGKpHKi$', #1, 'Sleeper Z20#0002', 'Sleeper', $, #368052, #368055, $, .SLEEPER.);`

These are classified using `IfcClassification`, `IfcClassificationReference`, and `IfcRelAssociatesClassification`.

<ins>Below is an example of the attributes' values, plus a mapping of these attributes to the bSDD data model.</ins>

`IfcClassification`
| Example instance             | Source           | Edition       | EditionDate | Name       | Description | Location                                                      | ReferenceTokens |
|------------------------------|------------------|---------------|-------------|------------|-------------|---------------------------------------------------------------|-----------------|
| #45 = IFCCLASSIFICATION      | 'buildingSMART'    | '4.3rc4'        | $           | 'IFC'        | $           | http://identifier.buildingsmart.org/uri/buildingsmart/ifc-4.3 | $               |
|                              | IFCLABEL         | IFCLABEL      | IFCDATE     | IFCLABEL   | IFCTEXT     | IFCURIREFERENCE                                               | IFCIDENTIFIER   |
| **Mapping with bSDD data model** | *OrganizationCode* | *DomainVersion* | *ReleaseDate* | *DomainName* | NA          | *DomainNamespaceUri*                                            | NA              |

`IfcClassificationReference`
| Example instance                 | Location                                                                                   | Identification         | Name                    | ReferencedSource                 | Description                                                                                                        | Sort          |
|----------------------------------|--------------------------------------------------------------------------------------------|------------------------|-------------------------|----------------------------------|--------------------------------------------------------------------------------------------------------------------|---------------|
| #46 = IFCCLASSIFICATIONREFERENCE | http://identifier.buildingsmart.org/uri/buildingsmart/ifc-4.3/class/ifctrackelementsleeper | 'ifctrackelementsleeper' | 'IfcTrackElement.SLEEPER' | #45                              | $ | $             |
|                                  | IFCURIREFERENCE                                                                            | IFCIDENTIFIER          | IFCLABEL                | IFCCLASSIFICATIONREFERENCESELECT | IFCTEXT                                                                                                            | IFCIDENTIFIER |
| **Mapping with bSDD data model**     | *DomainNamespaceUri/class/code*                                                              | *Code*                   | *Name*                    | NA                               | *Definition*                                                                                                         | NA            |

`IfcRelAssociatesClassification`
| Example instance                     | GlobalId               | OwnerHistory    | Name                        | Description | RelatedObjects      | RelatingClassification  |
|--------------------------------------|------------------------|-----------------|-----------------------------|-------------|---------------------|-------------------------|
| #47 = IFCRELASSOCIATESCLASSIFICATION | '0OLroQf6D0tfjW0rwFRKeK' | #10             | 'Classification Relationship' | $           | (#21,#22)           | #46                     |
|                                      | IFCGLOBALLYUNIQUEID    | IFCOWNERHISTORY | IFCLABEL                    | IFCTEXT     | IFCDEFINITIONSELECT | IFCCLASSIFICATIONSELECT |


</details>

<details><summary>Project Global Positioning</summary>

| **ID** | **CRITERIA**                            | **VALUE** / **COMMENT**               |
|--------|-----------------------------------------|---------------------------------------|
|        | ABC                                     | 0                                     |

</details>

<details><summary>Railway spatial structure</summary>

:construction: under construction :construction:

- **Concept Template**: Spatial Decomposition
- **Usage** (if existing): NA

| Parent Element | Parent Element Type | Minimum | Maximum | Child Element   | Child Element Type |
|----------------|---------------------|---------|---------|-----------------|--------------------|
| IfcSite        |                     | 1       | 1       | IfcRailway      | Località           |
| IfcRailway     | Località            | 1       | 1       | IfcFacilityPart | TRACKSTRUCTURE     |

</details>

<details><summary>Spatial containment</summary>

:construction: under construction :construction:

- **Concept Template**: Spatial Containment
- **Usage** (if existing): NA

| Spatial Element | Spatial Element Type | Minimum | Maximum | Element            | Element Type      |
|-----------------|----------------------|---------|---------|--------------------|-------------------|
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcActuator        | Manovra deviatoio |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcElementAssembly | TURNOUTPANEL      |
| IfcFacilityPart | TRACKSTRUCTURE       | 2       | 2       | IfcCourse          | BALLASTBED        |
| IfcFacilityPart | TRACKSTRUCTURE       | 6       | 6       | IfcRail            | RAIL              |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | TBD     | IfcTrackElement    | SLEEPER           |
| IfcSite         |                      | 2       | 2       | IfcAlignment       |                   |

</details>

<details><summary>Spatial reference</summary>

:construction: under construction :construction:

- **Concept Template**: :warning: Spatial Service Connectivity (or better *Group Spatial Connectivity*, not yet present in documentation) :warning:
- **Usage** (if existing): NA

| Spatial Element | Spatial Element Type | Minimum | Maximum | Product or Group | Product Type or Group Type          |
|-----------------|----------------------|---------|---------|------------------|-------------------------------------|
| IfcRailway      | Località             | 1       | 1       | IfcGroup         | Binari di corsa (Contenitore)       |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Deviatoi/Intersezioni (Contenitore) |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Massicciata (Contenitore)           |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Rotaie (Contenitore)                |
| IfcFacilityPart | TRACKSTRUCTURE       | 1       | 1       | IfcGroup         | Traverse (Contenitore)              |

</details>

<details><summary>Linear placement along alignment</summary>

| **ID** | **CRITERIA**                            | **VALUE** / **COMMENT**               |
|--------|-----------------------------------------|---------------------------------------|
|        | ABC                                     | 0                                     |

</details>

<details><summary>Properties of objects and object types</summary>

:construction: under construction :construction:

- **Concept Template**: Property Sets for Objects, Property Sets for Types
- **Usage** (if existing): NA

| Entity          | Entity Type          | PropertySet Name | Property Name           | Property Value Type | List Of Values                                       | IfcSimpleProperty subtype  |
|-----------------|----------------------|------------------|-------------------------|---------------------|------------------------------------------------------|----------------------------|
| IfcFacilityPart | TRACKSTRUCTURE       | RFI_S16000       | Binario                 | IFCLABEL            | Pari, Dispari, Unico                                 | IfcPropertyEnumeratedValue |
| IfcFacilityPart | TRACKSTRUCTURE       | RFI_S16000       | Codice binario SAS      | IFCLABEL            |                                                      | IfcPropertySingleValue     |
| IfcFacilityPart | TRACKSTRUCTURE       | RFI_S16000       | n. deviatoi elettrici   | IFCINTEGER          |                                                      | IfcPropertySingleValue     |
| IfcFacilityPart | TRACKSTRUCTURE       | RFI_S16000       | Profilo manutentivo L94 | IFCLABEL            | <=40 t/g, >100 t/g, 40< t/g <=100 | IfcPropertyEnumeratedValue |
| IfcFacilityPart | TRACKSTRUCTURE       | RFI_S16000       | Binario elettrificato   | IFCLOGICAL          |                                                      | IfcPropertySingleValue     |
| IfcTrackElement | SLEEPER              | ???              |                         |                     |                                                      |                            |
| IfcGroup        | Segmento di traverse | ???              |                         |                     |                                                      |                            |




</details>
