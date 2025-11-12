##### **SAP BW/4HANA Data Warehouse Project – University Data Analytics** 



###### **🚀 Project Overview**



This project demonstrates the complete end-to-end implementation of a Business Intelligence (BI) and Data Warehouse (DW) solution using SAP BW/4HANA.

It was developed as part of the “Business Intelligence” coursework and is structured into two major phases:



Data Modeling \& BW Object Design



ETL Processes for Master and Transaction Data, followed by Query Design and OLAP Analysis



The scenario simulates a university data warehouse that consolidates information about faculties, students, degrees, and academic performance to support management reporting.



**🧩 Phase 1: SAP BW Modeling**



🎯 Objective



To design and implement a semantic data model (Star Schema) and the corresponding BW InfoObjects, DataSources, and DataStore Objects in SAP BW/4HANA.



🔧 Key Steps



| Step | Task                                         | Description                                                                                                                          |

| ---- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |

| 1    | \*\*Conceptual Data Model (ER → Star Schema)\*\* | Conversion of an entity-relationship model into a multidimensional data model.                                                       |

| 2    | \*\*Creation of InfoObjects\*\*                  | Design of key figures and characteristics (e.g., “Number of Students”, “Number of Bachelor Theses”, “Semester”, “Faculty”, “State”). |

| 3    | \*\*DataSource Development\*\*                   | Creation of extraction structures for CSV-based source data.                                                                         |

| 4    | \*\*DataStore Objects (aDSO)\*\*                 | Implementation of Advanced DataStore Objects for staging and harmonization.                                                          |

| 5    | \*\*Data Flow Design\*\*                         | Establishment of DataFlows and mapping from DataSource → aDSO → CompositeProvider.                                                   |





**⚙️ Phase 2: ETL Process \& Data Integration**



**🎯 Objective**



To extract, transform, and load (ETL) master and transactional data from CSV files into SAP BW/4HANA and prepare it for OLAP reporting.



**🔧 ETL Workflow**

1\. Master Data Loading

Creation of DataSources for Faculties, Semesters, and States

Data transformation and harmonization

Attribute and text loads into InfoObjects (TEC\_###FB, TEC\_###SE, TEC\_###BL)

Validation via PSA preview and DTP monitor



2\. Transaction Data (Bewegungsdaten)



Setup of Advanced DataStore Object (TECDMH###) for student movement data

Definition of transformations and DTPs between acquisition and Data Mart layers

Use of NODIV0() functions to prevent data division errors

Activation and validation through BW Monitor



3\. Virtualization Layer



Creation of CompositeProvider (TECCP1HS###)

Definition of joins/unions between InfoProviders

Configuration of field mappings and output structure

Enabling of key-text display for reporting



**📈 Phase 3: Query Design \& OLAP Analytics**



Using BW Query Designer in Eclipse, several analytical queries were built on top of the CompositeProvider:



| Query           | Description                     | Key Features                                                                                                |

| --------------- | ------------------------------- | ----------------------------------------------------------------------------------------------------------- |

| `TEC\_###\_Q1\_HS` | Bachelor Theses by State        | Includes formula for `%Bachelorarbeiten = (BA/ST)\*100` with 3 decimal precision                             |

| `TEC\_###\_Q2\_HS` | Top 4 Faculties                 | Uses \*Top N Condition\* to display the 4 faculties with the most theses                                      |

| `TEC\_###\_Q3\_HS` | Semester Comparison (2014–2015) | Restricted Key Figures for specific semesters                                                               |

| `TEC\_###\_Q4\_HS` | Parameterized Query             | Uses input variables (text \& characteristic variables) for Semester and State                               |

| `TEC\_###\_Q5\_HS` | Promotion Analysis              | Formula: `%Promotionen = (PR/ST)\*100`, visualized with conditional formatting (red/yellow/green thresholds) |





**💡 Key Technical Concepts**



Data Modeling

InfoObjects, InfoAreas, aDSOs, CompositeProviders

Star Schema and dimensional design principles

ETL Processes

DataSource → DTP → aDSO → CompositeProvider

Error handling via NODIV0 and PSA verification

Query Design

Restricted and Calculated Key Figures

Variables (Text/Merkmals)

Conditions (Top N) and Exceptions (Color Indicators)

Reporting

Analysis for Office (Excel Integration)

Aggregations by Semester, Faculty, State



**🧰 Tools \& Technologies**



| Category                    | Tools                                       |

| --------------------------- | ------------------------------------------- |

| \*\*Data Warehouse Platform\*\* | SAP BW/4HANA 7.5 on HANA                    |

| \*\*Modeling Environment\*\*    | Eclipse with BW Modeling Tools              |

| \*\*ETL \& Transformation\*\*    | DataSources, DTPs, Transformations          |

| \*\*Virtualization\*\*          | CompositeProvider                           |

| \*\*Reporting \& OLAP\*\*        | SAP BW Query Designer / Analysis for Office |

| \*\*Data Format\*\*             | CSV (UTF-8)                                 |





**🧠 Learning Outcomes**



Deep understanding of SAP BW/4HANA architecture and data modeling concepts

Practical experience with ETL pipelines and data harmonization

Ability to design OLAP queries and business reports

Understanding of semantic modeling and data warehousing best practices





**🏁 Conclusion**



This project demonstrates a complete BI lifecycle — from conceptual modeling to data integration and analytical reporting — within SAP BW/4HANA.

It highlights modern data warehouse principles such as semantic layering, ETL automation, and self-service OLAP analysis for university management insights.



**📫 Contact**



For questions or collaboration opportunities:

📧 assatahamine@gmail.com



🌐 www.linkedin.com/in/amine-assatah-151210227

&nbsp;                              



