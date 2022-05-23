# Test Instruction

| Documentation Code | Title                                                 | Exchange Code | Test Code | Author        | Data Owner | Version | Date       |
| ------------------ | ----------------------------------------------------- | ------------- | --------- | ------------- | ---------- | ------- | ---------- |
| IFC4.3AbRV_E2_ASPC | Aggregate structures on Alignment - Pavement & Course | E2            | ASPC      | Lars Wikström | FTIA       | 1.0     | 19.05.2022 |


## Summary (Intent)

With these instructions the Aggregate structures on Alignment - Pavement & Course exchange is established.

This test instruction imports the alignment definition from [ALIN06](../E1a-ARSE/ALIN06) and defines a pavement structure that varies along the alignment.

| Info                         |                                     |
| ---------------------------- | ----------------------------------- |
| Number of alignment(s)       | 1                                   |
| Properties of segments       | no                                  |
| Horizontal layout            | Straight Line, Circular Arc         |
| Vertical layout              | Straight Line, Circular Arc         |
| Geometric representation     | IfcCompositeCurve, IfcGradientCurve |
| IFC reference file available | Yes                                 |

- Refer to [Test Case Imports](#Test-Case-Imports) to know the prerequisites for the present test.

- The [Expected Results](#Expected-Results) section lists the material that will be used to assess the fulfilment of capabilities.

- :zap: This is a test-driven process: refer to the [Validation Criteria](#Validation-Criteria) to understand what is required by the test :zap:

## Itemised Roots
The Test instruction addresses the import and export of the following IFC Entities & Concept Templates:

<details><summary>IFC Entities</summary>
These entities represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**


- From imported test instructions

  - Model setup

    - *IfcProject*
    - *IfcRepresentationContext*
    - *IfcMapConversion*
    - *IfcProjectedCRS*
    - *IfcUnitAssignment*

  - Spatial structure

    - *IfcSite*
    - *IfcRoad*

  - Alignment

    - *IfcAlignment*
    - *IfcAlignmentHorizontal*
    - *IfcAlignmentVertical*
    - *IfcAlignmentSegment*
    - *IfcAlignmentHorizontalSegment*
    - *IfcAlignmentVerticalSegment*
    - *IfcCompositeCurve*
    - *IfcGradientCurve*
    - *IfcCurveSegment*
    - *IfcLine*
    - *IfcCircle*

- For this test instruction

  - *IfcPavement*
  - *IfcCourse*
  - *IfcPropertySet*
  - *IfcPropertySingleValue*
  - *IfcPropertyEnumeratedValue*
  - *IfcLinearPlacement*


</details>

<details><summary>Concept Templates</summary>

These concept templates represent a test-specific subset of the wider AbRV_Ex exchange and the overall AbRV MVD, that must be correctly exported to meet the validation criteria. **The scope of the test shall not be used as a definitive scope of the exchange, or of the entire MVD.**

- From imported test instructions
  - Project Context
    - *Project Units*
    - *Project Representation Context*
    - *Project Global Positioning*
    - *Project Global Positioning*

  - Object Composition
    - *Alignment Decomposition*
    - *Spatial Decomposition*

  - Object Connectivity 
    - *Spatial Containment*

- For this test instruction
  - *Object Typing*
  - *Element Decomposition*
  - *Material Single*
  - *Product Linear Placement*
  - *Property Sets for Objects*


</details>

## Model Dataset

This test case utilises the dataset collected in the Dataset folder and summarised in the table below. **For more details on each item see [Dataset description](Dataset/README.md).**

| Filename                                                     | Description                                   |
| ------------------------------------------------------------ | --------------------------------------------- |
| [HorizontalAlignmentParameters](Dataset/HorizontalAlignmentParameters.csv) | Parameters for the horizontal segments as csv |
| [VerticalAlignmentParameters](Dataset/VerticalAlignmentParameters.csv) | Parameters for the vertical segments as csv   |
| [LandXML](Dataset/Testi_101_ml.xml)                          | LandXML-file representing the alignment       |
| [Pavement composition](./Dataset/Pavement-composition.png)   | Image showing the pavement composition        |

## Test Case Imports

Test instructions are defined with a modular approach to reduce repetition of validation criteria and test content, and improve vendors ability to solve issues and bugs. therefore this test instruction *imports/reuses* the following Test instructions and entities with the relevant associated validation criteria.

| TI Code                                                      | Test Instruction Title          | Comments |
| ------------------------------------------------------------ | ------------------------------- | -------- |
| [**IFC4x3_AbRV-E1a-ALIN06**](https://github.com/bSI-InfraRoom/MVD-Infra-Test-Instructions/blob/develop/E1a-ARSE/ALIN06) | Alignment Infrastructure Curves | na       |

## Expected Results

For certification of capabilities the only source will be:

- n. 1 IFC file containing the information as requested. The file shall be named using the following syntax: `MVDCode`-`ExchangeCode`-`TestCode`-`SoftwareVendor`.`ifc` (Example: `IFC4.3_AbRV-E2b-ASTPC-AmazingSoft.ifc`)

Considering the aim of this test, other **optional** results, not subject to the bSI certification process, yet usefull to illustrate test results are:
- Screen-shot of a planar view and a "long section" similar to the provided examples
- CSV export of the horizontal and vertical alignment segment parameters

---

## Validation criteria
:zap: For this test case to be considered passed **all capabilities listed in this section**, and **the ones of pre-required tests** shall be verified, with no exception. :zap:

### General

| **RULE ID** | **CRITERIA**                                                 | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| GENE_00     | All validation criteria of precondition's tests shall be verified |                                                              | na                         | na                     |
| GENE_01     | All requested entities (and attributes) exist in file        | As per Entities Table. See [Dataset description](Dataset/README.md) | na                         | na                     |

### Object typing

| **RULE ID** | **CRITERIA**              | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------- | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| OBTP_01     | Object types are verified | As per [Object Types Table](Dataset/README.md#Object-Types-Table) | na                         | Object Typing          |

> **Acceptance criteria**: For the **Object typing** capability, the validation procedure must verify that an IFC entity type with the given Name is typing (via `IfcRelDefinesByType`) exactly a given number of objects of the requested Name, no more and no less.

<details><summary>OBTP_01 details: Object types are verified</summary>

> - Given a set of types and objects taken from the [Object Types Table](Dataset/README.md#Object-Types-Table)
> - Then the Entity Type, with the Entity Type Name, exists
> - And the Entity Type must type exactly [MinSize..MaxSize] of the requested Object

</details>


### Material association

| **RULE ID** | **CRITERIA**                     | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | -------------------------------- | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| MATE_01     | Material association is verified | As per [Material Association Table](Dataset/README.md#Material-Association-Table) | na                         | Material Association   |

> **Acceptance criteria**: For the **Material association** capability, the validation procedure must verify that an Object of the requested type is associated (via `IfcRelAssociatesMaterial`) to a material definition with the requested name.

<details><summary>MATE_01 details: Material association is verified</summary>

> - Given a set of objects and materials taken from the [Material Association Table](Dataset/README.md#Material-Association-Table)
> - Then the Objects, and optionally the Object Type, exists
> - And the Object must be associated to the requested Material

</details>

### Element (De)Composition (Assemblies)

| **RULE ID** | **CRITERIA**                                       | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)**                      |
| ----------- | -------------------------------------------------- | ------------------------------------------------------------ | -------------------------- | ------------------------------------------- |
| ASSE_01     | Mandatory components are present in the assemblies | As per [Element (De)Composition Table](Dataset/README.md#Element-(De)Composition-Table) | na                         | Element Composition & Element Decomposition |

> **Acceptance criteria**: For the **ASSE_01 rule**, the validation procedure must verify that an assembly of the requested type (and name) aggregates (via `IfcRelAggregates`) at least a given number of elements of the requested type (and name).

<details><summary>ASSE_01 details: Mandatory components are present in the assemblies</summary>

> - Given a set of assemblies taken from the [Element (De)Composition Table](Dataset/README.md#Element-(De)Composition)
> - Then the Assembly, and optionally the Assembly Type, exists
> - And the Assembly must aggregate at least a number within [MinSize..MaxSize] of the requested Element

</details>

### Properties

| **RULE ID** | **CRITERIA**                                             | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)**                              |
| ----------- | -------------------------------------------------------- | ------------------------------------------------------------ | -------------------------- | --------------------------------------------------- |
| PSET_01     | The model does not contain unrequested property sets     | As per [Properties Table](Dataset/README.md#Properties-Table) | na                         | Property Sets for Objects & Property Sets for Types |
| PNAM_01     | The property set does not contain unrequested properties | As per [Properties Table](Dataset/README.md#Properties-Table) | na                         | Property Sets for Objects & Property Sets for Types |
| PTEX_01     | Property values belong to a list of values               | As per [Properties Table](Dataset/README.md#Properties-Table) | na                         | Property Sets for Objects & Property Sets for Types |
| PVAL_01     | Property values are not null and not empty               | As per [Properties Table](Dataset/README.md#Properties-Table) | na                         | Property Sets for Objects & Property Sets for Types |
| PVAL_02     | Requested property value types are found                 | As per [Properties Table](Dataset/README.md#Properties-Table) | na                         | Property Sets for Objects & Property Sets for Types |

> **Acceptance criteria**: For the **Properties for objects and object types** capability, the validation procedure must verify that both standard and custom property sets requested by the test case (including relative properties and values) are present in the IFC file.
> See below for further specification of each rule.

<details><summary>PSET_01: The model does not contain unrequested property sets</summary>

> - Given a set of properties taken from the [Properties Table](Dataset/README.md#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - Then the IfcEntity is associated at most to the property set with the PropertySet Name
</details>

<details><summary>PNAM_01: The property set does not contain unrequested properties</summary>

> - Given a set of properties taken from the [Properties Table](Dataset/README.md#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - Then the property set has at most the properties with the Property Name
</details>

<details><summary>PTEX_01: Property values belong to a list of values</summary>

> - Given a set of properties taken from the [Properties Table](Dataset/README.md#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - Then the property value is part of the List Of Values
</details>

<details><summary>PVAL_01: Property values are not null and not empty</summary>

> - Given a set of properties taken from the [Properties Table](Dataset/README.md#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - Then the property value is not null
> - And the property value is not empty
</details>

<details><summary>PVAL_02: Requested property value types are found</summary>

> - Given a set of properties taken from the [Properties Table](Dataset/README.md#Properties-Table)
> - When the IfcEntity, and optionally the Type, exists
> - And the IfcEntity is associated to a property set with the PropertySet Name
> - And the property set has a property with the Property Name
> - And the property value is not null
> - Then the property type is equal to the Property Value Type
</details>

## Spatial containment

| **RULE ID** | **CRITERIA**                    | **VALUE [examples]**                                         | **ENTITY (if applicable)** | **CT (if applicable)** |
| ----------- | ------------------------------- | ------------------------------------------------------------ | -------------------------- | ---------------------- |
| SCON_01     | Spatial containment is verified | As per [Spatial Containment Table](Dataset/README.md#Spatial-Containment-Table) | na                         | Spatial Containment    |

> **Acceptance criteria**: For the **Spatial containment** capability, the validation procedure must verify that a Spatial Element of the requested type contains (via `IfcRelContainedInSpatialStructure`) exactly a given number of Elements of the requested type, no more and no less.

<details><summary>SCON_01 details: Spatial containment is verified</summary>

> - Given a set of elements taken from the [Spatial Containment Table](Dataset/README.md#Spatial-Containment-Table)
> - Then the Spatial Element, and optionally the Spatial Element Type, exists
> - And the Spatial Element must contain at least a number within [MinSize..MaxSize] of the requested Element

</details>

### Product geometric representation

| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| PREP_01     | Geometric representation of products is verified | As per [Product Geometric Representation Table](Dataset/README.md#Product-Geometric-Representation-Table) |                   | Product Geometric Representation and its subtemplates |

> **Acceptance criteria**: For the **Group Geometric Representation** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has an IfcShapeRepresentation with the requested Representation Identifier, Representation Type and Items.

<details><summary>PREP_01 details:  Geometric representation of products is verified</summary>

> - Given a set of products taken from the [Product Geometric Representation Table](#Product-Geometric-Representation-Table)
> - Then the Product, and optionally the Product Type, exists
> - And the Product must have an IfcShapeRepresentation (via IfcProductDefinitionShape) with the requested Representation Identifier, Representation Type and Items.

</details>


### Product placement

| **RULE ID** | **CRITERIA**                            | **VALUE [examples]**                     | **ENTITY (if applicable)** | **CT (if applicable)**     |
|-------------|-----------------------------------------|------------------------------------------|----------------------------|----------------------------|
| PPLA_01     | Placement of products is verified | As per [Product Placement Table](Dataset/README.md#Product-Placement-Table) |                   | Product Placement subtemplates |
| PPLA_02     | For a product that has ObjectPlacement as IfcLinearPlacement, the CartesianPosition of IfcLinearPlacement shall be available | depends on cases |                   | Product Linear Placement |

> **Acceptance criteria**: For the **Product Placement** capability, the validation procedure must verify that a Product of the requested type (and optionally a requested name) has the requested Object Placement, and optionally the Object Placement has PlacementRelTo reference to the Object Placement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

<details><summary>PPLA_01 details:  Placement of products is verified</summary>

> - Given a set of products taken from the [Product Placement Table](Dataset/README.md#Product-Placement-Table)
> - Then the Product with Product Type and Product Name, exists
> - And the Product must have Object Placement, and the Object Placement has PlacementRelTo reference to the ObjectPlacement of Relative Placement Product with requested Relative Placement Product Type and Relative Placement Product Name.

</details>