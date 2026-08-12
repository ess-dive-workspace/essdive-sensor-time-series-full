# Term Guide
The  Sensor Time Series - Full Reporting Format terms are defined below, including  whether that term is required, a brief definition, formatting requirements, an example, and additional guidance. Additional required terms are included in the [Location Metadata Reporting Format](https://github.com/ess-dive-workspace/essdive-location-metadata/blob/release-v2.0.0/term_guide.md).

If a user includes terms that are not governed by this RF in their files (i.e., user-defined metadata columns), those terms will NOT be parsed in ESS-DIVE’s internal tools or independently verified during schematization. The information may be included in the data schema as an unidentified piece of metadata.

A single asterisk (*) below marks terms that are required. Two asterisks (**) mark terms that are conditionally required.

### Terms of the reporting format:
[**Sensor Time Series Data File**](#sensor-time-series-data-file)
- [datetime_measured](#datetime_measured)**
- [datetime_measured_start](#datetime_measured_start)**
- [datetime_measured_end](#datetime_measured_end)**
- [{measurement_column_name}](#measurement_column_name)*
- [{measurement_column_name}_flag](#measurement_column_name_flag)
- [notes](#notes)

[**Methods and Attributes File**](#methods-and-attributes-file)
- [attr_id](#attr_id)*
- [attr_type](#attr_type)*
- [attr_description](#attr_description)*
- [analysis_detection_limit](#analysis_detection_limit)
- [analysis_precision](#analysis_precision)
- [instrument_precision](#instrument_precision)
- [lower_bound](#lower_bound)
- [upper_bound](#upper_bound)
- [sensor_model](#sensor_model)
- [sensor_serial_number](#sensor_serial_number)

[**File Level Metadata File**](#file-level-metadata-file)
- [file_name](#file_name)*
- [file_description](#file_description)*
- [standard](#standard)*
- [data_dictionary_file_name](#data_dictionary_file_name)*
- [file_version](#file_version)
- [data_orientation](#data_orientation)
- [header_rows](#header_rows)
- [column_or_row_name_position](#column_or_row_name_position)
- [notes](#notes-1)

[**Data Dictionary File**](#data-dictionary-file)
- [column_or_row_name](#column_or_row_name)*
- [unit](#unit)*
- [definition](#definition)*
- [measured_variable](#measured_variable)*
- [material_measured](#material_measured)*
- [method_id](#method_id)*
- [location_id](#location_id)*
- [sensor_id](#sensor_id)
- [treatment_id](#treatment_id)
- [unit_basis](#unit_basis)
- [column_or_row_long_name](#column_or_row_long_name)
- [data_type](#data_type)
- [missing_value_code](#missing_value_code)
- [representation_temporal](#representation_temporal)
- [statistic_measurement](#statistic_measurement)
- [statistic_measurement_number](#statistic_measurement_number)
- [statistic_spatial](#statistic_spatial)
- [statistic_spatial_number](#statistic_spatial_number)
- [statistic_temporal](#statistic_temporal)
- [statistic_temporal_number](#statistic_temporal_number)
- [statistic_detail](#statistic_detail)
- [notes](#notes-2)

[**Location Metadata Reporting Format Term Guide**](https://github.com/ess-dive-workspace/essdive-location-metadata/blob/release-v2.0.0/term_guide.md)

---
## Sensor Time Series Data File

### datetime_measured
|term|`datetime_measured`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required conditionally: either `datetime_measured` or both `datetime_measured_start` and `datetime_measured_end` must be used|
|format|datetime, ISO 8601:2019|
|unit|N/A|
|definition|Date and time of measurement, to known specificity.|
|example|2026-03-12T13:50-06:00|
|additional guidance|Dates must be reported in the ISO 8601:2019 standard (YYYY-MM-DD) and completed to known precision (e.g. YYYY-MM, YYYY). Times must be reported with a date in either Coordinated Universal Time (UTC) (YYYY-MM-DDThh:mm:ssZ) or Local Standard Time with the UTC offset (YYYY-MM-DDThh:mm±hh:mm). It is strongly recommended not to change UTC offset in the middle of a time series (i.e., do not switch from Standard Time to Daylight Savings Time). Complete times to known precision (e.g. YYYY-MM-DDThh). Use of "T" and either “Z” or “±” characters are required. <br><br> YYYY = 4-digit year, MM = 2-digit month, DD = 2-digit day of month, hh = 2-digit hour ranging from 00-23, mm = 2-digit minute, ss = 2-digit second.|

### datetime_measured_start
|term|`datetime_measured_start`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required conditionally: either `datetime_measured` or both `datetime_measured_start` and `datetime_measured_end` must be used|
|format|datetime, ISO 8601:2019|
|unit|N/A|
|definition|Date and time of the start of the measurement, to known specificity.|
|example|2026-03-12T13:50-06:00|
|additional guidance|Dates must be reported in the ISO 8601:2019 standard (YYYY-MM-DD) and completed to known precision (e.g. YYYY-MM, YYYY). Times must be reported with a date in either Coordinated Universal Time (UTC) (YYYY-MM-DDThh:mm:ssZ) or Local Standard Time with the UTC offset (YYYY-MM-DDThh:mm±hh:mm). It is strongly recommended not to change UTC offset in the middle of a time series (i.e., do not switch from Standard Time to Daylight Savings Time). Complete times to known precision (e.g. YYYY-MM-DDThh). Use of "T" and either “Z” or “±” characters are required. <br><br> YYYY = 4-digit year, MM = 2-digit month, DD = 2-digit day of month, hh = 2-digit hour ranging from 00-23, mm = 2-digit minute, ss = 2-digit second.|

### datetime_measured_end
|term|`datetime_measured_end`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required conditionally: either `datetime_measured` or both `datetime_measured_start` and `datetime_measured_end` must be used|
|format|datetime, ISO 8601:2019|
|unit|N/A|
|definition|Date and time of the end of the measurement, to known specificity.|
|example|2026-03-12T13:50-06:00|
|additional guidance|Dates must be reported in the ISO 8601:2019 standard (YYYY-MM-DD) and completed to known precision (e.g. YYYY-MM, YYYY). Times must be reported with a date in either Coordinated Universal Time (UTC) (YYYY-MM-DDThh:mm:ssZ) or Local Standard Time with the UTC offset (YYYY-MM-DDThh:mm±hh:mm). It is strongly recommended not to change UTC offset in the middle of a time series (i.e., do not switch from Standard Time to Daylight Savings Time). Complete times to known precision (e.g. YYYY-MM-DDThh). Use of "T" and either “Z” or “±” characters are required. <br><br> YYYY = 4-digit year, MM = 2-digit month, DD = 2-digit day of month, hh = 2-digit hour ranging from 00-23, mm = 2-digit minute, ss = 2-digit second.|

### {measurement_column_name}
|term|`{measurement_column_name}`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|text; only UTF-8 characters are permitted|
|unit|N/A|
|definition|User-defined measurement column name. Strongly recommend to use only letters, numbers, underscores, and hyphens.|
|example|temp_soil_2|
|additional guidance|`{measurement_column_name}` is considered arbitrary. They are not parsed for information on type of variable, unit, statistic, or temporal representation. Each `{measurement_column_name}` must be defined in the data dictionary file using the required terms that include `measured_variable` and `unit`. Optional terms, such as `statistic_*`, `representation_temporal`, and `unit_basis`, should be used to fully describe the measurement characteristics. |

### {measurement_column_name}_flag
|term|`{measurement_column_name}_flag`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|text; only UTF-8 characters are permitted|
|unit|N/A|
|definition|User-defined identifier that indicates a flag for the individual measurement in the corresponding `{measurement_column_name}`. Often used for data quality flags. Strongly recommend to use only letters, numbers, underscores, and hyphens.|
|example|temp_soil_2_flag|
|additional guidance|Column header for associated `{measurement_column_name}` will be appended with “_flag” for a flag column. Flag codes must be defined in the methods and attributes file|

### notes
|term|`notes`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|Free text notes field.|
|example|Storm event occurred during sampling.|
|additional guidance|N/A|

---

## Methods and Attributes File
###  attr_id
|term|`attr_id`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|text; only UTF-8 characters are permitted|
|unit|N/A|
|definition|Attribute identifier associated with either a method ID, flag, treatment ID, or sensor ID. Strongly recommend to use only letters, numbers, underscores, and hyphens.|
|example|soil_method_012|
|additional guidance|N/A|

###  attr_type
|term|`attr_type`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-sensor-time-series-full/blob/release-v1.0.0/controlled_vocabulary.md#attr-type)|
|unit|N/A|
|definition|Attribute identifier type|
|example|method_id|
|additional guidance|N/A|

###  attr_description
|term|`attr_description`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|free text|
|unit|N/A|
|definition|Description of the attribute identifier provided within the `attr_id` term. The description should hold enough detail to pass peer review in a journal article methods section.|
|example|Sensor was attached to a brick and placed on riverbed.|
|additional guidance|The attr_description text can be written in sections within the description to improve clarity. For example, including sections for sensor deployment, calibration, and QAQC. The user can also choose to use subheaders to indicate that parts of the description apply to specific measurements. For example: pressure sensor, dissolved oxygen sensor.|

###  analysis_detection_limit
|term|`analysis_detection_limit`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|See associated measurement column unit|
|definition|Detection limit associated with the analysis (i.e., the lowest / smallest quantity that can be measured), in the units of the reported measurement|
|example|0.05|
|additional guidance|N/A|

###  analysis_precision
|term|`analysis_precision`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|See associated measurement column unit|
|definition|Precision associated with the analysis (i.e., how close repeated measures are to each other), in the units of the reported measurement|
|example|0.02|
|additional guidance|N/A|

###  instrument_precision
|term|`instrument_precision`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|See associated measurement column unit|
|definition|Precision of the instrument/sensor (i.e., the smallest difference between measurements that the instrument can resolve), in the units of the reported measurement|
|example|0.02|
|additional guidance|N/A|

### lower_bound
|term|`lower_bound`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|See associated measurement column unit|
|definition|Lower bound of expected data values, in the units of the reported measurement|
|example|5|
|additional guidance|Bounds can support programmatic removal of flagged values. The lower bound may describe what is physically possible for the measurement type or what is expected for the particular system.|

### upper_bound
|term|`upper_bound`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|See associated measurement column unit|
|definition|Upper bound of expected data values, in the units of the reported measurement|
|example|8|
|additional guidance|Bounds can support programmatic removal of flagged values. The upper bound may describe what is physically possible for the measurement type or what is expected for the particular system.|

### sensor_model
|term|`sensor_model`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|Model of sensor|
|example|YSI EXO2 Multiparameter Sonde with EXO Optical Dissolved Oxygen Smart Sensor|
|additional guidance|N/A|

### sensor_serial_number
|term|`sensor_serial_number`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|Serial number of sensor|
|example|12345|
|additional guidance|N/A|

---

## File Level Metadata File
### file_name
|term|`file_name`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|N/A|
|definition|Provide the name of the associated file. File names should be unique and be as descriptive as possible about the file contents. Use only letters (e.g. CamelCase), numbers, and underscores. Do not include spaces. Hyphens allowed but not preferred. Use "\*" wildcard when the FLMD applies to multiple files. For example - the same FLMD applies to all soil core files in this data package - "soil_cores_*.csv"|
|example|measurements.csv|
|additional guidance|This term is from the [File Level Metadata reporting format](https://github.com/ess-dive-workspace/essdive-file-level-metadata/blob/main/flmd_quick_guide.md#file-name).|

### file_description
|term|`file_description`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement| required|
|format|N/A|
|definition|A brief description (minimum of 10 characters) of the file and what distinguishes this file from other files in the data package. Include information about the type of data (images, observations, experimental, etc.) |
|example|Geochemistry data measurements, including anions and cations, for 2025-06-08 to 2026-01-02.|
|additional guidance|This term is from the [File Level Metadata reporting format](https://github.com/ess-dive-workspace/essdive-file-level-metadata/blob/main/flmd_quick_guide.md#file-description).|

### standard
|term|`standard`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|_Controlled vocabulary to be updated once revisions are finalized._|
|definition|Identify if an ESS-DIVE Reporting Format or any other data or metadata standard was applied to the data file. Standard names for the ESS-DIVE reporting formats are available in the [Standard FLMD Term List](https://github.com/ess-dive-workspace/essdive-file-level-metadata/blob/main/RF_FLMD_Standard_Terms.csv).| 
|example|ESS-DIVE Sensor Time Series - Full Reporting Format v1|
|additional guidance|For any files following the Sensor Time Series - Full reporting format, including data, methods and attributes, and data dictionary, provide "ESS-DIVE Sensor Time Series - Full Reporting Format v1" in the `standard` term.|

### data_dictionary_file_name
|term|`data_dictionary_file_name`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|text; contains “dd.csv"|
|definition|The file name of the data dictionary that corresponds to the provided “file_name” entry. The file name must end with “dd.csv”.| 
|example|measurements_dd.csv|
|additional guidance|N/A|

### file_version
|term|`file_version`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|definition|This is the version of the data file being described in the FLMD. The data file version is assigned by the data provider and not by the system. This would change if the data file is updated after the data package is published. Changes should be explained in the Notes term.| 
|example|version 1|
|additional guidance|This term is from the [File Level Metadata reporting format](https://github.com/ess-dive-workspace/essdive-file-level-metadata/blob/main/flmd_quick_guide.md#file-version).|

### data_orientation
|term|`data_orientation`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|horizontal or vertical|
|definition|Describe how the data are organized within the data matrix. Choose between "horizontal" (i.e., data are organized in rows with column headers) or "vertical" (i.e., data are organized in columns with row headers).| 
|example|horizontal|
|additional guidance|For files following the Sensor Time Series - Full reporting format, the `data_orientation` value should be "horizontal".| 

### header_rows
|term|`header_rows`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|N/A|
|definition|Provide the total number of header rows before the start of the first data row, including the column header or row name. Do not include commented-out (i.e., column/rows that begin with a hash (#)) in the header_rows count. This term is marked as optional, but is required if any data files have more than one header row.|
|example|1|
|additional guidance|For files following the Sensor Time Series - Full reporting format, the `header_rows` value should be 1.|

### column_or_row_name_position
|term|`column_or_row_name_position`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|N/A|
|definition|Provide the row or column number that contains the header names. This term is not required if there are no rows or columns before the row/column names. If not included, it will be assumed that header names are in row 1 (horizontal orientation) or column 1 (vertical orientation). Do not include commented-out (i.e., column/rows that begin with a hash (#)) in the column_or_row_name_position count. |
|example|1|
|additional guidance|For files following the Sensor Time Series - Full reporting format, the `column_or_row_name_position` value should be 1.|

### notes
|term|`notes`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|definition|Information provided would be data file specific. Details may include details on data file versioning, reporting format, software requirements, data quality, etc.| 
|example||
|additional guidance|This term is from the [File Level Metadata reporting format](https://github.com/ess-dive-workspace/essdive-file-level-metadata/blob/main/flmd_quick_guide.md#notes).| 

---

## Data Dictionary File
### column_or_row_name
|term|`column_or_row_name`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|free text|
|unit|N/A|
|definition|Column or row name from the data file. Provide entries for each column or row name from the data matrix in the data file.|
|example|temp_soil_2|
|additional guidance|This term is from the [File Level Metadata reporting formathere](https://github.com/ess-dive-workspace/essdive-file-level-metadata/blob/main/CSV_dd/csv_dd_quick_guide.md#column-or-row-name).|

### unit
|term|`unit`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-sensor-time-series-full/blob/release-v1.0.0/controlled_vocabulary.md#unit)|
|unit|N/A|
|definition|Unit of measurement.|
|example|degree Celsius|
|additional guidance|Insert "N/A" when units aren't applicable. Insert “unitless” if the measurement is unitless or nondimensional. When a unit is a ratio of two of the same units (e.g., g/g), do not use “unitless”, use the actual units.|

### definition
|term|`definition`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|free text|
|unit|N/A|
|definition|A description of the column header.|
|example|Soil temperature replicate 2 at location loc_25d|
|additional guidance|Definitions for reporting format terms must be used as is from the provided data dictionary template. For user-defined `{measurement_column_name}`, the measurement characteristics must be defined in the required terms that include `measured_variable` and `unit`. Optional terms, such as `statistic_*`, `representation_temporal`, and `unit_basis`, should be used to fully describe the measurement characteristics. The measurement characteristics can be repeated in the definition; however downstream resources will primarily utilize the other specific data dictionary terms.|

### measured_variable
|term|`measured_variable`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-sensor-time-series-full/blob/release-v1.0.0/controlled_vocabulary.md#measured_variable)|
|unit|N/A|
|definition|The variable or property being measured. This term is only used for `{measurement_column_name}` column headers.|
|example|temperature|
|additional guidance|N/A|

### material_measured
|term|`material_measured`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-sensor-time-series-full/blob/release-v1.0.0/controlled_vocabulary.md#material_measured)|
|unit|N/A|
|definition|The material or medium in which the measurement was taken. This term is only used for `{measurement_column_name}` column headers.|
|example|air|
|additional guidance|N/A|

### method_id
|term|`method_id`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|text; only UTF-8 characters are permitted; semicolon whitespace delimiter|
|unit|N/A|
|definition|User-defined identifier that indicates what methods were used to collect the measured values. Strongly recommend to use only letters, numbers, underscores, and hyphens.|
|example|soil_method_012|
|additional guidance|The method ID must be defined within the methods and attributes file. If more than one `method_id` is populated in a single cell, they should be separated with a semicolon and space.|

### location_id
|term|`location_id`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|required|
|format|text; only UTF-8 characters are permitted|
|unit|N/A|
|definition|A unique identifier of a location. The identifier can be globally unique or unique within a project. Strongly recommended to only use letters, numbers, hyphens, and underscores.|
|example|loc_25d|
|additional guidance|The location ID must be defined within the location file.|

### sensor_id
|term|`sensor_id`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|text; only UTF-8 characters are permitted; semicolon space delimiter|
|unit|N/A|
|definition|User-defined identifier that indicates what sensor(s) were used to collect the measured values. Strongly recommend to only use letters, numbers, hyphens, and underscores.|
|example|exo_12345|
|additional guidance|The sensor ID must be defined within the methods and attributes file. <br><br> If more than one sensor ID is listed in a cell, the sensor IDs should be separated by a semicolon and space. <br><br> Changes in sensor ID during the time series can be indicated at the datetime of change in a measurement column’s corresponding flag column or in the notes field.|

### treatment_id
|term|`treatment_id`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|Optional|
|format|text; only UTF-8 characters are permitted |
|unit|N/A|
|definition|User-defined identifier that indicates what treatment was used for manipulation experiments, if applicable. Strongly recommended that only letters, numbers, hyphens, and underscores are used.|
|example|treatment_wet_01|
|additional guidance|Treatment IDs should be defined within the methods and attributes file. <br><br> It is recommended that if there is no treatment but the column is present, the `treatment_id` should be “N/A”. It is recommended that if there is a control treatment, the `treatment_id` should be “control”.|

### unit_basis
|term|`unit_basis`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|Basis for how the measurement values are quantified (e.g., “as nitrate” vs. “as nitrogen”; “per kg dry sediment”; “relative to Vienna Pee Dee Belemnite”). Provide if relevant.|
|example|as carbon|
|additional guidance|This information is important for the correct interpretation of the measurement value.|

### column_or_row_long_name
|term|`column_or_row_long_name`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|recommended|
|format|free text|
|unit|N/A|
|definition|Longer human-readable column name. Sometimes this may be identical to Definition or even Column_or_Row_Name.|
|example|temperature_soil_2|
|additional guidance|This term is from the [File Level Metadata reporting format](https://github.com/ess-dive-workspace/essdive-file-level-metadata/blob/main/CSV_dd/csv_dd_quick_guide.md#column-or-row-long-name)|

### data_type
|term|`data_type`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-sensor-time-series-full/blob/release-v1.0.0/controlled_vocabulary.md#data_type)|
|unit|N/A|
|definition|Data type for each column|
|example|text|
|additional guidance|N/A|

### missing_value_code
|term|`missing_value_code`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|The missing value code used for missing measurements. Only one code allowed.|
|example|-9999|
|additional guidance|Based on the CSV Reporting Format guidelines, for columns containing numeric data, ESS-DIVE recommends using "-9999" as the missing value code. For columns containing character data, ESS-DIVE recommends using "N/A" as the missing value code. If you would like to use a different missing value code, specify the used missing value code within this term. If a missing value code is not applicable for a column, leave this entry blank or use a generic missing value code.|

### representation_temporal
|term|`representation_temporal`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-sensor-time-series-full/blob/release-v1.0.0/controlled_vocabulary.md#representation_temporal)|
|unit|N/A|
|definition|Temporal representativeness of the measurement, if applicable. This term is only used for data dictionary rows where the `column_or_row_name` entry is a measured variable. In many cases, a corresponding `statistic_temporal` should be specified. The temporal representation will be considered instantaneous if no value is provided.|
|example|month|
|additional guidance|The temporal representation should be used when the measurement value is not an instantaneous observation and/or represents a non-instantaneous time period. For example, if measurements are made every hour and then averaged to represent a day, the temporal representation of “day” should be used, with the corresponding temporal statistic of “mean”. <br><br> If `datetime_measured_start` and `datetime_measured_end` are reported and a temporal representation is applicable, the temporal representation should match the temporal difference.|

### statistic_measurement
|term|`statistic_measurement`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-sensor-time-series-full/blob/release-v1.0.0/controlled_vocabulary.md#statistic)|
|unit|N/A|
|definition|Statistic description, if applicable. This term is only used for `{measurement_column_name}` headers if the measured value represents repeated observations of the same scientifically-equivalent spatial location and/or temporal period (e.g., replicates), or for general uncertainty in the measurement itself.|
|example|mean|
|additional guidance|A measurement statistic typically describes variation or uncertainty in the measurement. This can be obtained / reported by an instrument or calculated via replicates. Use the spatial and / or temporal statistical descriptions, if the variability is due to multiple scientifically important locations or time periods.|

### statistic_measurement_number
|term|`statistic_measurement_number`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|N/A|
|definition|The number of observations used to calculate the `statistic_measurement`. The observations should be scientifically equivalent in space and time.|
|example|5|
|additional guidance|Use only with `{measurement_column_name}` that have `statistic_measurement` specified.|

### statistic_spatial
|term|`statistic_spatial`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-sensor-time-series-full/blob/release-v1.0.0/controlled_vocabulary.md#statistic)|
|unit|N/A|
|definition|Statistical description, if applicable. This term is only used for `{measurement_column_name}` headers if the measured value represents a combination of individual observations from separate locations to represent a larger location.|
|example|mean|
|additional guidance|The spatial statistic should be used to describe measurement values that are a combination of separate spatial locations.|

### statistic_spatial_number
|term|`statistic_spatial_number`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|N/A|
|definition|The number of observations used to calculate the `statistic_spatial`.|
|example|5|
|additional guidance|Use only with `{measurement_column_name}` that have `statistic_spatial` specified.|

### statistic_temporal
|term|`statistic_temporal`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|[Controlled vocabulary](https://github.com/ess-dive-workspace/essdive-sensor-time-series-full/blob/release-v1.0.0/controlled_vocabulary.md#statistic)|
|unit|N/A|
|definition|Statistic description, if applicable. This term is only used for `{measurement_column_name}` headers if the measured value represents a combination of individual observations at different times to represent a larger time period. In most cases, a corresponding `representation_temporal` should be specified.|
|example|mean|
|additional guidance|The temporal statistic should be used when the measurement value is a combination of individual measurements made at separate times.|

### statistic_temporal_number
|term|`statistic_temporal_number`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|numeric|
|unit|N/A|
|definition|The number of observations used to calculate the `statistic_temporal`.|
|example|5|
|additional guidance|Use only with `{measurement_column_name}` that have `statistic_temporal` specified.|

### statistic_detail
|term|`statistic_detail`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|Additional details for interpretation of the `statistic _*` terms.|
|example|statistic_measurement is mean of 5 biological replicates|
|additional guidance|If the `statistic_measurement` is used, it is recommended to add details describing whether physical replicates, or repeat measurements of the same entity, or other approaches were used. Additional details may include information about how the statistic was calculated.|

### notes
|term|`notes`|
|:----------------------------------------------------|:----------------------------------------------------|
|requirement|optional|
|format|free text|
|unit|N/A|
|definition|Free text notes field|
|example||
|additional guidance|N/A|
