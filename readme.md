# RA Task - Ohio Highway Resurfacing Data Collection Project

## Summary

- This folder outputs four key files:
  - **Ohio_projects_collected_clean.xlsx**: Contains all projects, mapped and completed according to the 10 specified fields.
  - **Ohio_projects_collected_clean_individually_verified.xlsx**: Contains the five distinct projects specified in "RA_Task.pdf", each individually and manually verified and documented in `15.ipynb`in accordance with the requirements outlined in `RA_Task.pdf`. These projects were randomly sampled to ensure unbiased selection demonstrating robust data collection and verification methodology as required by the assignment. The methodology, supporting evidence, and results are thoroughly detailed within the notebook. This process ensured that all blank fields for the sampled projects were accurately completed based on assignment.

  - **Ohio_projects_collected_clean_supplement_1.xlsx**: Provides supplementary data with additional fields derived from "Ohio_projects_collected.xlsx".
  - **Ohio_projects_collected_clean_supplement_2.xlsx**: Contains supplementary bidder information, including:
    - Bidder names and addresses
    - Bidder locations
    - Bid amounts
    - Project award status


This project delivers a comprehensive data collection solution as outlined in `RA_Task.pdf`. While the original requirements specified analysis of 5 projects, the scope was expanded to encompass all 202 available projects in the dataset, demonstrating thoroughness, technical proficiency and interest. Additional data fields have been incorporated to ensure completeness and enhance analytical values.

**Note**: Due to project timeline constraints, the codebase prioritized functionality and deliverable completion. Future iterations would benefit from improved readability, and organization.

## Data Quality Assessment

### Critical Finding: Project ID 105522 Mileage Discrepancy

During data validation, a significant discrepancy was identified in the mileage calculation for Project ID 105522, which serves as the reference example in `Ohio_projects_collected.xlsx`.

**Issue**: The recorded mileage of 12.982 miles does not align with supporting documentation.

**Analysis**:
- The value 12.982 does not appear in any source documentation
- While this may derive from the edge line measurement of 12.98 miles, this methodology is questionable
- Cross-referencing with the project proposal (`180326.pdf`) indicates a project length of 6.49 miles
- The edge line measurement in the bid tabulation (`180326bidtab.pdf`) shows 12.98 miles
- Since roads typically have edge lines on both sides, the actual project length would be 12.98 ÷ 2 = 6.49 miles, matching the proposal documentation
- It is likely that the correct value is 6.49 miles rather than 12.982 miles

## Table of Contents

- [Summary](#Summary)
- [Data Quality Assessent](#data-quality-assessment)
- [Project Methodology](#project-methodology)


## Project Methodology

This section outlines the systematic approach employed to complete the data collection task through 12 distinct phases:

### Phase 1: Data Understanding and Exploration (`1.ipynb`)
**Objective**: Comprehensive dataset analysis and column interpretation

**Activities**:
- Documented the meaning and properties of each column
- Analyzed relationships between variables
- Conducted summary statistics analysis
- Identified missing and unique values
- Developed a strategic framework for data extraction
- Researched relevant data sources and websites

### Phase 2: Automated County and Route Information Extraction (`2.ipynb`)
**Objective**: Systematically extract geographical and route data

**Process**:
- Implemented automated search functionality using the Transportation Information Mapping System (TIMS)
- Extracted county and route information for all projects
- Generated FIPS codes using county and state information
- Prioritized "Recorded County" data for consistency over alternative county measures

### Phase 3: Error Handling and Data Validation (`3.ipynb` and `4.ipynb`)
**Objective**: Address data quality issues identified in Phase 2

**Challenges Addressed**:
- Resolved instances where counties were marked as "District" instead of actual county names
- Implemented fallback to "Work County" when "Recorded County" was unavailable

**Data Quality Note**: While "Work County" is less consistent than "Recorded County", this substitution affects only a small portion of the dataset and maintains overall data integrity.

### Phase 4: Comprehensive Data Enhancement (`5.ipynb`)
**Objective**: Populate dataset with critical project metrics

**Data Elements Added**:
- Number of lanes
- Project duration
- Winning bid amounts
- Actual project costs

**Quality Assurance**:
- Conducted summary statistics analysis
- Performed data validation checks
- Generated visualizations to verify data reasonableness

### Phase 5: PDF Document Processing (`6.ipynb`)
**Objective**: Download and process project documentation

**Process**:
- Downloaded project proposal and bid tabulation PDFs
- Prepared documents for engineering estimate extraction
- Extracted bidder lists and count information

### Phase 6: PDF Data Extraction (`7.ipynb`)
**Objective**: Process downloaded PDFs for data extraction

**Activities**:
- Processed PDFs downloaded in Phase 5
- Implemented data quality consistency checks for error detection
- Validated extracted information for accuracy

### Phase 7: Bid Tabulation Analysis (`8.ipynb`)
**Objective**: Extract comprehensive bidder information from bid tabulation documents

**Data Elements Extracted**:
- Bidder names and addresses
- Bidder locations
- Bid amounts
- Project award status

**Output**: `Ohio_projects_collected_clean_supplement_2.xlsx`

**Note**: Due to time constraints and task scope requirements, accuracy verification of this extended dataset was not performed.

### Phase 8: Data Validation and Visualization (`9.ipynb`)
**Objective**: Conduct comprehensive dataset validation and generate insights

**Activities**:
- Created visualizations to study dataset validity
- Generated analytical insights from collected data
- Performed analysis for data verification

### Phase 9: Error Correction (`10.ipynb`)
**Objective**: Address minor dataset errors identified during validation

**Process**: Implemented targeted corrections to improve data quality

### Phase 10: Mileage Analysis (`11.ipynb`)
**Objective**: Determine appropriate mileage measurement methodology

**Analysis**:
- Analyzed properties of "project length" vs. "work length" measurements
- Evaluated interchangeability of these metrics
- Concluded that "project length" is most applicable based on mileage definition requirements

### Phase 11: Debugging and Error Resolution (`12.ipynb` and `13.ipynb`)
**Objective**: Systematic error identification and resolution

**Process**:
- Conducted thorough debugging of data extraction processes
- Identified and resolved all error sources
- Completed mileage entries for all available projects


**Key Finding**: 40 out of 203 projects have officially documented "NA" (not available) project lengths as stated in the official project proposals.

### Phase 12: Data Finalization (`14.ipynb`)
**Objective**: Final data cleaning and output formatting

**Activities**:
- Removed unnecessary columns
- Standardized data types to match requirements
- Generated multiple output formats:
  1. Template-matching layout file
  2. Fields-specific file as requested in `RA_Task.pdf`

---


