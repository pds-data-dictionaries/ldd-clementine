PDS4 Clementine Mission Data Dictionary User's Guide  
[Last edited](#edit-history): 2026-02-11  
  
# Introduction  
1. Purpose of this User's Guide  
    - This User's Guide provides an overview of the Clementine Mission Data Dictionary. The guide details how to include the dictionary in a PDS4 label, describes the organization of the dictionary's classes and attributes, provides definitions for these classes and attributes, and lists example excerpts from labels that use them.  
2. Audience  
    - This User's Guide should be useful to data providers intending to archive Clementine data with PDS as well as PDS Nodes who are working with these data providers.  
  
# Overview of the Clementine Mission Data Dictionary  
The Clementine Mission Data Dictionary contains classes and attributes specific to the Clementine mission and its instruments.  
Steward: Madison N. Hughes , PDS Geosciences Node, mnhughes@wustl.edu  
  
# Document Outline  
1. [How to Include the Clementine Mission Data Dictionary in a PDS4 Label](#how-to-include-the-Clementine-Mission-data-dictionary-in-a-pds4-label)  
2. [Organization of Classes and Attributes](#organization-of-classes-and-attributes)  
    1. [Class Organization](#class-organization)  
    2. [Attributes by Class](#attributes-by-class)  
3. [Definitions](#definitions)  
    1. [Classes (in alphabetical order)](#classes-in-alphabetical-order)  
    2. [Attributes (in alphabetical order)](#attributes-in-alphabetical-order)  
4. [Examples](#examples)  
5. [Edit History](#edit-history)  
  
# How to Include the Clementine Mission Data Dictionary in a PDS4 Label  
The dictionary consists of a set of files with names in the form PDS4_CLEMENTINE_xxxx_yyyy.ext, where  
- xxxx = the PDS4 Information Model version, e.g. 1G00  
- yyyy = the Clementine Mission Data Dictionary version, e.g. 1000  
  
and the file extensions are  
  
- .csv = A comma-separated value table of dictionary attributes  
- .JSON = The dictionary contents in JSON format  
- .sch = The dictionary "rules" as an XML Schematron file  
- .txt = The report generated when the dictionary was built  
- .xml = The PDS4 label that describes this set of files  
- .xsd = The dictionary contents as an XML schema file  
  
Only the schema and Schematron files are needed for validating a PDS4 label.  
  
The latest version of this dictionary may be found on the PDS web site at https://pds.nasa.gov/datastandards/dictionaries/index-missions.shtml#clementine.  
  
The following is an example showing the use of this dictionary in a PDS4 label.  
  
```
<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="https://pds.nasa.gov/pds4/pds/v1/PDS4_PDS_1G00.sch" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<?xml-model href="https://pds.nasa.gov/pds4/mission/clementine/v1/PDS4_CLEMENTINE_1G00_1000.sch" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<Product_Observational xmlns="http://pds.nasa.gov/pds4/pds/v1"
    xmlns:clementine="http://pds.nasa.gov/pds4/mission/clementine/v1"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="https://pds.nasa.gov/pds4/pds/v1/PDS4_PDS_1G00.xsd
                        https://pds.nasa.gov/pds4/mission/clementine/v1/PDS4_CLEMENTINE_1G00_1000.xsd">
```  
  
The following is a schematic example showing the location of every Clementine Mission Data Dictionary class and attribute in a PDS4 label. Note that not all classes and attributes may be mutually compatible, and the example does not include any recursion, even if recursion is allowed.  
```
<Observation_Area>
  ...
  <Mission_Area>
    <clementine:Clementine_Parameters>
      <clementine:original_product_id/>
      <clementine:revolution_number/>
      <clementine:producer_institution_name/>
      <clementine:frame_sequence_number/>
      <clementine:sequence_table_id/>
      <clementine:uncorrected_start_time/>
      <clementine:clem_jpeg_version/>
      <clementine:twist_angle/>
      <clementine:smear_magnitude/>
      <clementine:smear_azimuth/>
      <clementine:north_azimuth/>
      <clementine:local_hour_angle/>
      <clementine:cryocooler_duration/>
      <clementine:Celestial_Footprint_Vertices>
        <clementine:Celestial_Reference_Pixel>
          <clementine:reference_pixel_location/>
          <clementine:pixel_ra/>
          <clementine:pixel_dec/>
        </clementine:Celestial_Reference_Pixel>
      </clementine:Celestial_Footprint_Vertices>
      <clementine:Illumination_Secondary>
        <clementine:light_source_name/>
        <clementine:light_source_distance/>
        <clementine:sub_light_source_azimuth/>
        <clementine:sub_light_source_latitude/>
        <clementine:sub_light_source_longitude/>
        <clementine:incidence_angle/>
        <clementine:phase_angle/>
      </clementine:Illumination_Secondary>
    </clementine:Clementine_Parameters>
  </Mission_Area>
  ...
</Observation_Area>
```  
  
The namespace for the Clementine Mission Data Dictionary is http://pds.nasa.gov/pds4/mission/clementine/v1, abbreviated "clementine:".  
  
# Organization of Classes and Attributes  
  
## Class Organization  
Below is a structured list showing the organization of classes, ordered by appearance in the PDS4 label. Each class name is linked to its complete definition in the [Definitions](#definitions) section.  
- [Clementine_Parameters](#clementine_parameters)  
  - [Celestial_Footprint_Vertices](#celestial_footprint_vertices)  
    - [Celestial_Reference_Pixel](#celestial_reference_pixel)  
  - [Illumination_Secondary](#illumination_secondary)  
  
## Attributes by Class  
The attributes immediately under each class (if any) are listed below. Both classes and attributes are ordered by appearance in the PDS4 label; however, each class is listed only once, even if that class can appear in more than one place in a PDS4 label. Each class and attribute name is linked to its complete definition in the [Definitions](#definitions) section.  
  
### [Clementine_Parameters](#clementine_parameters) (attribute list)  
- [original_product_id](#original_product_id)  
- [revolution_number](#revolution_number)  
- [producer_institution_name](#producer_institution_name)  
- [frame_sequence_number](#frame_sequence_number)  
- [sequence_table_id](#sequence_table_id)  
- [uncorrected_start_time](#uncorrected_start_time)  
- [clem_jpeg_version](#clem_jpeg_version)  
- [twist_angle](#twist_angle)  
- [smear_magnitude](#smear_magnitude)  
- [smear_azimuth](#smear_azimuth)  
- [north_azimuth](#north_azimuth)  
- [local_hour_angle](#local_hour_angle)  
- [cryocooler_duration](#cryocooler_duration)  
  
### [Celestial_Footprint_Vertices](#celestial_footprint_vertices) (attribute list)  
  
### [Celestial_Reference_Pixel](#celestial_reference_pixel) (attribute list)  
- [reference_pixel_location](#reference_pixel_location)  
- [pixel_ra](#pixel_ra)  
- [pixel_dec](#pixel_dec)  
  
### [Illumination_Secondary](#illumination_secondary) (attribute list)  
- [light_source_name](#light_source_name)  
- [light_source_distance](#light_source_distance)  
- [sub_light_source_azimuth](#sub_light_source_azimuth)  
- [sub_light_source_latitude](#sub_light_source_latitude)  
- [sub_light_source_longitude](#sub_light_source_longitude)  
- [incidence_angle](#incidence_angle)  
- [phase_angle](#phase_angle)  
  
# Definitions  
  
## Classes (in alphabetical order)  
  
### Celestial_Footprint_Vertices  
 The Celestial_Footprint_Vertices class provides a set of right ascension and declination pairs which are the vertices of a polygon representing the footprint of the field of view on the celestial sphere in the earth-centered J2000 (EME2000) coordinate system. This and its associates are direct analogs of geom:Footprint_Vertices and its associates, intended for referencing FoV to the celestial sphere rather than a target body. They can also be reconsidered reimplementations of the PDS3 Data Dictionary elements RETICLE_POINT_RA and RETICLE_POINT_DECLINATION.  
- [go to attribute list](#celestial_footprint_vertices-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Celestial_Reference_Pixel  
 The Celestial_Reference_Pixel class provides the right ascension and declination of a specific designated pixel in the earth-centered J2000 (EME2000) coordinate system.  
- [go to attribute list](#celestial_reference_pixel-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 5  
  
### Clementine_Parameters  
Container class for Clementine-specific parameters.  
- [go to attribute list](#clementine_parameters-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Illumination_Secondary  
The Illumination_Secondary class contains attributes providing illumination geometry for a secondary light source. It should be used only when parameters for a primary illumination source have been specified elsewhere in the label (perhaps using geom:Illumination_Geometry).  
- [go to attribute list](#illumination_secondary-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
## Attributes (in alphabetical order)  
  
### *clem_jpeg_version*  
 The clem_jpeg_version attribute specifies the specific set of parameters fed to the Matra compression chip that performed the onboard JPEG-variant discrete cosine transformation image compression. Two settings are documented as commonly used in the primary mission: "CLEM-JPEG-0" and, most often, "CLEM-JPEG-1." "CLEM-JPEG-2" and "CLEM-JPEG-3" also appear in some files but are not described in documentation.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - CLEM-JPEG-0  
    - Description:  CLEM-JPEG-0 denotes Matra's built-in quantization settings, weighted towards lower-frequency image data.  
  - CLEM-JPEG-1  
    - Description:  CLEM-JPEG-1 denotes settings that utilized a flat quantization table.  
  - CLEM-JPEG-2  
    - Description:  CLEM-JPEG-2 denotes some other group of settings not detailed in documentation.  
  - CLEM-JPEG-3  
    - Description:  CLEM-JPEG-3 denotes some other group of settings not detailed in documentation.  
  - None  
    - Description:  A value of None indicates that Clementine did not compress this particular image.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *cryocooler_duration*  
 The cryocooler_duration attribute provides the duration, in seconds, since the activation of an imager's cooling device and the acquisition of an image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *frame_sequence_number*  
 The frame_sequence_number attribute provides the position of an image within a sequence of images taken as part of an observational pass.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *incidence_angle*  
The incidence_angle element provides a measure of the lighting condition at the intercept point. Incidence angle is the angle between the local vertical at the intercept point (surface) and a vector from the intercept point to the sun. The incidence_angle varies from 0 degrees when the intercept point coincides with the subsolar point to 90 degrees when the intercept point is at the terminator (i.e., in the shadowed or dark portion of the target body).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *light_source_distance*  
 Distance between the target body center and the light source whose illumination parameters are described in the containing class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *light_source_name*  
 Name of light source to which other attributes of containing class apply.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *local_hour_angle*  
The local_hour_angle attribute provides a measure of the instantaneous apparent sun position at the subspacecraft point. The local_hour_angle is the angle between the extension of the vector from the Sun to the target body and the vector projection on the target body’s ecliptic plane of a vector from the target body’s planetocentric center to the observer (usually, the spacecraft). This angle is measured in a counterclockwise direction when viewed from north of the ecliptic plane. It may be converted from an angle in degrees to a local time, using the conversion of 15 degrees per hour for those planets for which the rotational direction corresponds with the direction of measure of the angle.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *north_azimuth*  
 north_azimuth gives the azimuth, in degrees, of the vector between the image center and the target north pole. The reference line for this angle extends from image center to image right edge; angle increases clockwise in the image plane.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *original_product_id*  
 The original_product_id attribute provides the identifier used for a product during active mission operations, which may be distinct from the product id used for archival.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *phase_angle*  
The phase_angle element provides a measure of the relationship between the instrument viewing position and incident illumination (such as solar light). Phase angle is measured at the target; it is the angle between a vector to the illumination source and a vector to the instrument. If illumination is from behind the instrument, phase_angle will be small.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *pixel_dec*  
The pixel_dec attribute gives the value of the declination of a particular pixel as projected on the celestial sphere.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *pixel_ra*  
The pixel_ra attribute gives the value of the right ascension of a particular pixel as projected on the celestial sphere.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *producer_institution_name*  
 The producer_institution_name element identifies the institution primarily responsible for the production of a particular data product.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *reference_pixel_location*  
 reference_pixel_location describes the position, within an image associated with the labeled data product, of a pixel referred to by other attributes of the containing class.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *revolution_number*  
 The revolution_number attribute identifies the number of the observational pass of a spacecraft around a target body. Note: The Clementine Mission used this attribute in place of orbit number because orbit number changes half way through the observational pass over the Moon and would not be an ideal parameter when interrogating the data set. The revolution number equals orbit number at the start of the observational pass.  
- PDS4 data type: ASCII_NonNegative_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 18446744073709551615  
- Regex Pattern: [0-9]+  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *sequence_table_id*  
The sequence_table_id attribute provides a code specifying the order in which cameras were shuttered and filters activated during a particular observation.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *smear_azimuth*  
 smear_azimuth gives the azimuth, in degrees, of the 'smear' velocity vector (velocity of image boresight intercept with target). The reference line for this angle extends from image center to image right edge; angle increases clockwise in the image plane.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *smear_magnitude*  
 smear_magnitude gives the amount, in pixels, that the image is 'smeared' by spacecraft motion. More specifically, in Clementine, it is the magnitude of the velocity vector of camera boresight intercept with target (including spacecraft rotation) multiplied by exposure duration and image scale.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *sub_light_source_azimuth*  
The sub_light_source_azimuth attribute provides the value of the angle between the line from the center of an image to the sub-light-source point on the target and a horizontal reference line (in the image plane) extending from the image center to the middle right edge of the image. The values of this angle increase in a clockwise direction.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *sub_light_source_latitude*  
The sub_light_source_latitude attribute gives the value of the planetocentric latitude at the sub-light-source point on the target.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *sub_light_source_longitude*  
The sub_light_source_longitude attribute gives the value of the planetocentric latitude at the sub-light-source point on the target.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *twist_angle*  
 The twist_angle attribute provides the angle of rotation about an instrument's optical axis relative to celestial coordinates. Right ascension, declination, and twist angle together completely specify the pointing of an instrument in a celestial coordinate system.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *uncorrected_start_time*  
The uncorrected_start_time attribute provides the starting time value originally assigned to a product before some corrective process.  
- PDS4 data type: ASCII_Date_Time_YMD  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
# Examples  
  
Example PDS4 label snippet from urn:nasa:pds:clementine_lwir_bt:data_brightness_temperature:bt0033a040.img::1.0:  
```
<Mission_Area>
  <clementine:Clementine_Parameters>
    <clementine:original_product_id>LLA0033A.040</clementine:original_product_id>
    <clementine:revolution_number>040</clementine:revolution_number>
    <clementine:frame_sequence_number>33</clementine:frame_sequence_number>
    <clementine:north_azimuth unit="deg">3.69</clementine:north_azimuth>
    <clementine:local_hour_angle unit="deg">5.33</clementine:local_hour_angle>
  </clementine:Clementine_Parameters>
</Mission_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:clementine:data:uvvis_24s_309e::1.0:  
```
<Mission_Area>
  <clementine:Clementine_Parameters>
    <clementine:producer_institution_name>UNITED STATES GEOLOGICAL SURVEY</clementine:producer_institution_name>
  </clementine:Clementine_Parameters>
</Mission_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:clementine:data:19940417t133222756_hires_moon_c_650::1.0:  
```
<Mission_Area>
  <clementine:Clementine_Parameters>
    <clementine:original_product_id>LHC33211.271</clementine:original_product_id>
    <clementine:revolution_number>271</clementine:revolution_number>
    <clementine:producer_institution_name>NAVAL RESEARCH LABORATORY</clementine:producer_institution_name>
    <clementine:frame_sequence_number>4417</clementine:frame_sequence_number>
    <clementine:sequence_table_id>FEQ_06</clementine:sequence_table_id>
    <clementine:uncorrected_start_time>1994-04-17T13:32:22.762Z</clementine:uncorrected_start_time>
    <clementine:clem_jpeg_version>CLEM-JPEG-0</clementine:clem_jpeg_version>
    <clementine:twist_angle unit="deg">232.43</clementine:twist_angle>
    <clementine:smear_magnitude>0.16</clementine:smear_magnitude>
    <clementine:smear_azimuth unit="deg">359.29</clementine:smear_azimuth>
    <clementine:north_azimuth unit="deg">180.99</clementine:north_azimuth>
    <clementine:Celestial_Footprint_Vertices>
      <clementine:Celestial_Reference_Pixel>
        <clementine:reference_pixel_location>Upper Left Corner</clementine:reference_pixel_location>
        <clementine:pixel_ra unit="deg">156.78</clementine:pixel_ra>
        <clementine:pixel_dec unit="deg">-48.49</clementine:pixel_dec>
      </clementine:Celestial_Reference_Pixel>
      <clementine:Celestial_Reference_Pixel>
        <clementine:reference_pixel_location>Upper Right Corner</clementine:reference_pixel_location>
        <clementine:pixel_ra unit="deg">156.41</clementine:pixel_ra>
        <clementine:pixel_dec unit="deg">-48.81</clementine:pixel_dec>
      </clementine:Celestial_Reference_Pixel>
      <clementine:Celestial_Reference_Pixel>
        <clementine:reference_pixel_location>Lower Right Corner</clementine:reference_pixel_location>
        <clementine:pixel_ra unit="deg">156.77</clementine:pixel_ra>
        <clementine:pixel_dec unit="deg">-48.99</clementine:pixel_dec>
      </clementine:Celestial_Reference_Pixel>
      <clementine:Celestial_Reference_Pixel>
        <clementine:reference_pixel_location>Lower Left Corner</clementine:reference_pixel_location>
        <clementine:pixel_ra unit="deg">157.14</clementine:pixel_ra>
        <clementine:pixel_dec unit="deg">-48.67</clementine:pixel_dec>
      </clementine:Celestial_Reference_Pixel>
      <clementine:Celestial_Reference_Pixel>
        <clementine:reference_pixel_location>Center</clementine:reference_pixel_location>
        <clementine:pixel_ra unit="deg">156.78</clementine:pixel_ra>
        <clementine:pixel_dec unit="deg">-48.74</clementine:pixel_dec>
      </clementine:Celestial_Reference_Pixel>
    </clementine:Celestial_Footprint_Vertices>
    <clementine:local_hour_angle unit="deg">158.64</clementine:local_hour_angle>
    <clementine:Illumination_Secondary>
      <clementine:light_source_name>EARTH</clementine:light_source_name>
      <clementine:light_source_distance unit="km">394128.7
                </clementine:light_source_distance>
      <clementine:sub_light_source_azimuth unit="deg">269.91
                </clementine:sub_light_source_azimuth>
      <clementine:sub_light_source_latitude unit="deg">4.8
                </clementine:sub_light_source_latitude>
      <clementine:sub_light_source_longitude unit="deg">352.67
                </clementine:sub_light_source_longitude>
      <clementine:incidence_angle unit="deg">85.15</clementine:incidence_angle>
      <clementine:phase_angle unit="deg">85.12</clementine:phase_angle>
    </clementine:Illumination_Secondary>
  </clementine:Clementine_Parameters>
</Mission_Area>
```  
  
# Edit History  
*See also: [CLEMENTINE change log](https://github.com/pds-data-dictionaries/ldd-clementine/blob/main/CHANGELOG.md).*  
2026-02-11  Madison N. Hughes 