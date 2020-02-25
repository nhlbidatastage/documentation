---
description: A brief review of the Portable Format for Bioinformatics (PFB) file type
---

# PFB Files

## What is a Portable Format for Bioinformatics \(PFB\)?

A Portable Format for Bioinformatics \(PFB\) allows users to transfer both the metadata from the the Data Dictionary as well as the Data Dictionary itself. As a result, data can be transferred while keeping the structure from the original source. Specifically, a PFB consists of 3 parts \(additional details below\):

* A schema
* Metadata
* Data

For a more in-depth review and information that includes Python tools for PFB creation and exploration please visit the [PyPFB github page](https://github.com/uc-cdis/pypfb/) and install the newest version. 

> **NOTE**: The following PFB example is a direct PFB export from the `tutorial-synthetic_data_set_1` found on [Gen3 BioData Catalyst](https://gen3.biodatacatalyst.nhlbi.nih.gov/). Due to the large amount of data stored within PFB files, only small sections are shown with breaks, `...` , occurring in the output.

### **Schema**

A schema is a JSON formatted Data Dictionary containing information about the properties such as value types and descriptions, amongst others. To view the PFB schema, use the following command:  
`pfb show -i PFB_file.avro schema`

```text
...
  {
    "type": "record",
    "name": "gene_expression",
    "fields": [
      {
        "default": null,
        "name": "data_category",
        "type": [
          "null",
          {
            "type": "enum",
            "name": "gene_expression_data_category",
            "symbols": [
              "Transcriptome Profiling"
            ]
          }
        ]
      },
      {
        "default": null,
        "name": "data_type",
        "type": [
          "null",
          {
            "type": "enum",
            "name": "gene_expression_data_type",
            "symbols": [
              "Gene Expression Quantification"
            ]
          }
        ]
      },
      {
        "default": null,
        "name": "data_format",
        "type": [
          "null",
          {
            "type": "enum",
            "name": "gene_expression_data_format",
            "symbols": [
              "TXT",
              "TSV",
              "CSV",
              "GCT"
            ]
          }
        ]
      },
      {
        "default": null,
        "name": "experimental_strategy",
        "type": [
          "null",
          {
            "type": "enum",
            "name": "gene_expression_experimental_strategy",
            "symbols": [
              "RNA-Seq",
              "Total RNA-Seq"
            ]
          }
        ]
      },
      {
        "default": null,
        "name": "file_name",
        "type": [
          "null",
          "string"
        ]
      },
      {
        "default": null,
        "name": "file_size",
        "type": [
          "null",
          "long"
        ]
      },
      {
        "default": null,
        "name": "md5sum",
        "type": [
          "null",
          "string"
        ]
      },
      {
        "default": null,
        "doc": "The GUID of the object in the index service.",
        "name": "object_id",
        "type": [
          "null",
          "string"
        ]
      }
...
```

> **NOTE**: To make the outputs more human-readable, the above information was then piped through the program [jq](https://stedolan.github.io/jq/). Example: `pfb show -i PFB_file.avro schema | jq`

### **Metadata**

The metadata in a PFB contains all of the information explaining the linkage between nodes and external references for each of the properties. To view the PFB metadata, use the following command:  
`pfb show -i PFB_file.avro metadata`

```text
...
    {
      "name": "exposure",
      "ontology_reference": "",
      "values": {},
      "links": [
        {
          "multiplicity": "MANY_TO_ONE",
          "dst": "subject",
          "name": "subjects"
        }
      ],
      "properties": [
        {
          "name": "years_smoked",
          "ontology_reference": "Person Smoking Duration Year Count",
          "values": {
            "source": "caDSR",
            "cde_id": "3137957",
            "cde_version": "1.0",
            "term_url": "https://cdebrowser.nci.nih.gov/CDEBrowser/search?elementDetails=9&FirstTimer=0&PageId=ElementDetailsGroup&publicId=3137957&version=1.0"
          }
        },
        {
          "name": "years_smoked_gt89",
          "ontology_reference": "Person Smoking Duration Year Count",
          "values": {
            "source": "caDSR",
            "cde_id": "3137957",
            "cde_version": "1.0",
            "term_url": "https://cdebrowser.nci.nih.gov/CDEBrowser/search?elementDetails=9&FirstTimer=0&PageId=ElementDetailsGroup&publicId=3137957&version=1.0"
          }
        },
        {
          "name": "alcohol_history",
          "ontology_reference": "Alcohol Lifetime History Indicator",
          "values": {
            "source": "caDSR",
            "cde_id": "2201918",
            "cde_version": "1.0",
            "term_url": "https://cdebrowser.nci.nih.gov/CDEBrowser/search?elementDetails=9&FirstTimer=0&PageId=ElementDetailsGroup&publicId=2201918&version=1.0"
          }
        },
        {
          "name": "alcohol_intensity",
          "ontology_reference": "Person Self-Report Alcoholic Beverage Exposure Category",
          "values": {
            "source": "caDSR",
            "cde_id": "3457767",
            "cde_version": "1.0",
            "term_url": "https://cdebrowser.nci.nih.gov/CDEBrowser/search?elementDetails=9&FirstTimer=0&PageId=ElementDetailsGroup&publicId=3457767&version=1.0"
          }
        },
...
```

### **Data**

The data in the PFB are the values for the properties in the format of the Data Dictionary. To view the data within the PFB, use the following command:  
`pfb show -i PFB_file.avro`

```text
...
{
  "id": "6c5e21d5-da76-49a5-9f82-7e3a726d44c6",
  "name": "lab_result",
  "object": {
    "cer451q1": null,
    "oxldl1": null,
    "f81c": null,
    "renins1c": null,
    "cystatc1": null,
    "triglycerides": -0.40415245294570923,
    "glucos1c": 6.5463337898254395,
    "glucos1u": null,
    "ldl": 2.0789523124694824,
    "hdl": 2.7123606204986572,
    "creatin1": null,
    "total_cholesterol": 3.039848566055298,
    "chlcat1c": null,
    
...

    "uabcat1c": null,
    "inslnr1t": 1.8090298175811768,
    "vldlp31c": null,
    
...

    "unit_hematocrit_vfr_bld": null,
    "age_at_total_cholesterol": 80,
    "unit_total_cholesterol": null,
    "age_at_triglycerides": 80,
    "unit_triglycerides": null,
    "age_at_hdl": 80,
    "unit_hdl": null,
    "age_at_ldl": 80,
    "unit_ldl": null,
    
...

    "unit_mcv_entvol_rbc": null,
    "submitter_id": "HG00325_lab_res",
    "state": "validated",
    "project_id": "tutorial-synthetic_data_set_1",
    "created_datetime": "2020-01-27T13:54:06.745386+00:00",
    "updated_datetime": "2020-01-27T13:54:06.745386+00:00"
  },
  "relations": [
    {
      "dst_id": "f4fdda57-80f4-4995-bea2-161c3242c525",
      "dst_name": "subject"
    }
  ]
}
```

To look at  a certain number of entries in the PFB file, the following flag, `-n`, can be used to designate a number. To view the first 10 data entries within the PFB, use the following command:  
`pfb show -i PFB_file.avro -n 10`

