# Data Upload and Download Policy and Recommendations For Users

**BDCatalyst-RFC-\#:** 6  
**BDCatalyst-RFC-Title:** Data Access Working Group Data Upload and Download Policy and Recommendations For Users  
**BDCatalyst-RFC-Type:** Process   
**Name of the person who is to be Point of Contact:** Kira Bradford, Jessica Lyons  
**Email of the person who is to be Point of Contact:** [kcbradford@renci.org](mailto:kcbradford@renci.org), [Jessica\_Lyons@hms.harvard.edu](mailto:Jessica_Lyons@hms.harvard.edu)   
**Submitting Team:** Data Access Working Group  
**Requested BDCatalyst-RFC posting start date:** 2020-03-31  
**BDCatalyst-RFC-Status:** Comment only  
**URL Link to this document:**  
[https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/request-for-comments/data-upload-and-download-policy-and-recommendations-for-users](https://bdcatalyst.gitbook.io/biodata-catalyst-documentation/request-for-comments/data-upload-and-download-policy-and-recommendations-for-users)  
**URL Link to the BDCatalyst-RFC:**  
[https://www.nhlbidatastage.org/collaboration/rfcs/bdcatalyst-rfc-6](https://www.biodatacatalyst.org/collaboration/rfcs/bdcatalyst-rfc-6/)  
**License:** This work is licensed under a [CC-BY-4.0 license](https://creativecommons.org/licenses/by/4.0/).   


### DAWG Data Upload and Download Policy and Recommendations For Users

This document describes and defines data movement \(data egress and ingress\), explaining the types of data movement currently allowable on each platform, and what kinds of data should be downloaded or uploaded. This document is meant to inform the BioData Catalyst Go Live users of the Data Access Working Group’s \(DAWG\) data upload and download recommendations and policies. These policies and recommendations herein are specific to BioData Catalyst users. Please note the following terminology that will be in use throughout this document.

#### Terminology:

* Ecosystem = BioData Catalyst
* Platform = piece of the BioData Catalyst ecosystem
  * Examples: Terra, Gen3, Seven Bridges, PIC-SURE
* Workspace = areas to work on/with data within a platform
  * Examples: projects/workspaces within Seven Bridges or Terra, 
* Individual-level Data = Data at the level of the individual 
* Controlled-access data = Data that is not publically accessible and requires specific credentials or approvals for access and use primarily due to study participant consents. 
* External data/user uploaded data = Other data sources not hosted on BioData Catalyst, such as a users own created dataset, or data from another source. 
* FISMA moderate = The Federal Information Security Management Act \(FISMA\) creates standards to ensure that all government partners handle confidential and sensitive data appropriately. FISMA moderate is the designated level that means if the data are compromised there could be a serious adverse impact, such as a loss of confidentiality, integrity or availability of data. 
* Security boundary = refers to the technical infrastructure boundaries of a BioData Catalyst platform and Ecosystem.

## Definition of Types of Data Movement on BioData Catalyst 

We define data movement as the transfer of data, including controlled-access data, in and out of the FISMA moderate security boundaries of the BioData Catalyst ecosystem. Types of data movement are listed below along with available functionality by Go Live:  


* **Type 1:** Uploading and downloading data to a workspace within a platform
  * Uploading: Moving data that exists outside the BioData Catalyst security boundary inside the security boundary \(i.e. uploading data\) - available by Go Live \(See more information below on [Permissible Data Upload](https://docs.google.com/document/d/1d3cl4EzDuZLS2oPu0W_yUMIh9WVWqa03TahJvl_0wwE/edit#bookmark=id.gzmt9udkxi17)\)
  * Downloading: Moving data from within the BioData Catalyst security boundary outside of the security boundary \(i.e. downloading data\) - available by Go Live \(See [Permissible Data Download](https://docs.google.com/document/d/1d3cl4EzDuZLS2oPu0W_yUMIh9WVWqa03TahJvl_0wwE/edit#bookmark=id.cz4slif9tpr5) for data download limitations\)
* **Type 2:** Moving data from one workspace to another workspace within the same platform - available by Go Live
  * Example: move data from one workspace to another workspace within Terra. For example, a user copies a workspace on Terra and creates a new workspace to run a similar analysis in a different Terra workspace. 
* **Type 3:** Moving data from one platform workspace to another platform workspace - not available by Go Live from all platforms \(see Table 1 below\). Moving data using core services will be available, such as accessing data available from Gen3 and/or curated data from PIC-SURE and moving it to another platform for analysis. 
  * Example: If the user generates result files from running an analysis in one workspace \(e.g. Seven Bridges workspace\), those work files are not currently able to be accessed by a different platform workspace \(e.g. Terra workspace\).  
* **Type 4:** Sharing controlled-access data brought into or datasets with controlled-access data produced by users in the BioData Catalyst ecosystem with unauthorized users - prohibited for Go Live. This pertains to controlled access data brought into the ecosystem by the user or data available through BioData Catalyst, including data that has been created or altered for analyses. For user-generated results files, the BioData Catalyst consortium does not currently have policies in place or technical implementations to track this. We do not have the technical implementation to track a user bringing their own data on to the BioData Catalyst ecosystem, and sharing it with others. We also do not have any data provenance technical implementation for tracking how a dataset is transformed. Therefore, our policy is that the user is responsible for any external uploaded or transformed data. Users must adhere to all regulations and data use agreements and are solely responsible for the use of any data uploaded and transformed within the ecosystem.

## Data Movement Allowed

This table describes the current types of data movement allowed for BioData Catalyst users based on which platform they are using. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Platform</th>
      <th style="text-align:left">Type 1</th>
      <th style="text-align:left">Type 2</th>
      <th style="text-align:left">Type 3</th>
      <th style="text-align:left">Type 4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Gen3</td>
      <td style="text-align:left">&#x2714;</td>
      <td style="text-align:left">&#x2714;</td>
      <td style="text-align:left">
        <p>&#x2714;</p>
        <p>(as part of core services)</p>
      </td>
      <td style="text-align:left">prohibited</td>
    </tr>
    <tr>
      <td style="text-align:left">Terra</td>
      <td style="text-align:left">&#x2714;</td>
      <td style="text-align:left">&#x2714;</td>
      <td style="text-align:left">Not available by Go Live</td>
      <td style="text-align:left">prohibited</td>
    </tr>
    <tr>
      <td style="text-align:left">Seven Bridges</td>
      <td style="text-align:left">&#x2714;</td>
      <td style="text-align:left">&#x2714;</td>
      <td style="text-align:left">Not available by Go Live</td>
      <td style="text-align:left">prohibited</td>
    </tr>
    <tr>
      <td style="text-align:left">PIC-SURE</td>
      <td style="text-align:left">&#x2714;</td>
      <td style="text-align:left">&#x2714;</td>
      <td style="text-align:left">
        <p>&#x2714;</p>
        <p>(as part of core services)</p>
      </td>
      <td style="text-align:left">prohibited</td>
    </tr>
  </tbody>
</table>

**Table 1: Data Movement allowed in BioData Catalyst** 

Data Movement from core services to platforms is permissible. These include accessing data available from Gen3 and/or curated data from PIC-SURE and moving it to another platform for analysis. 

## Permissible Data Upload, Bring Your Own Data

Users are permitted to upload data not available to the BioData Catalyst ecosystem \(i.e. external data\) to their own workspace. Users may upload data into BioData Catalyst if they have the required approvals for such use. These approvals include: Approval of a Data Access Request for controlled access data that includes a BioData Catalyst cloud use statement and the user's institutional review board policies and guidelines. At all times, it is the user's responsibility to ensure they use the data they upload consistent with applicable Data Use Agreements, Data Use Limitations, IRB and any other restrictions on use.

## Permissible and Prohibited Data Download 

Due to the sensitive nature of data available through the BioData Catalyst ecosystem, users are only allowed to download certain pieces of data/results as outlined in Table 2. It is acknowledged that the technical infrastructure allows for data download on Biodata Catalyst platforms so the responsibility for compliance with data download requirements lies with the user of BioData Catalyst. Results and data that the user would broadly share, such as in an academic publication, may be downloaded through shared workspaces on the BioData Catalyst ecosystem; however, users are strongly encouraged to keep results and data within the BioData Catalyst ecosystem. Users are prohibited from downloading any controlled access, individual-level data \(see Table 2\). Users should be aware that if they choose to download permitted data and results, that the act of transferring that data through the BioData Catalyst security boundary may or may not be supported by your Data Use Agreement\(s\), Limitation\(s\), or Institutional Review Board policies and guidelines. BioData Catalyst users are solely responsible for adhering to the terms of these policies. Users should be aware that all data downloads are logged and regularly reviewed for compliance. See below examples of data permissible and prohibited for download. 

**Table 2: BioData Catalyst Permissible and Prohibited Download**  


<table>
  <thead>
    <tr>
      <th style="text-align:left">Permissible to Download</th>
      <th style="text-align:left">Prohibited to Download</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Aggregate results/tables that would be publishable in academic publication</li>
          <li>Summary data that does not include individual-level and/or controlled-access
            data</li>
          <li>Your own data that you brought to the platform for analyses following
            your DUAs and/or IRB protocols</li>
          <li>To request special permission for other types of download, please contact
            the BioData Catalyst help desk at <a href="https://urldefense.proofpoint.com/v2/url?u=https-3A__biodatacatalyst.nhlbi.nih.gov_contact&amp;d=DwMFAg&amp;c=WO-RGvefibhHBZq3fL85hQ&amp;r=e2NhGl_S3MgYQ2nUSk5Rd0MFsPF-3vp5-hM1VA0Uz38&amp;m=7Gd5tBXrt0vU7XDQ_F4pvKtJYOMOs6ovIGxrZQbfhCc&amp;s=uNYTta08_ieZn79R1F_TPxzGNOyAb5IHhh2UjrBEwFU&amp;e=">https://biodatacatalyst.nhlbi.nih.gov/contact</a>.</li>
        </ul>
      </td>
      <td style="text-align:left">
        <p>Users are prohibited to download any controlled-access, individual level
          data such as:</p>
        <ul>
          <li>Hosted TOPMed CRAM files with individual-level data</li>
          <li>Hosted TOPMed VCF files with individual-level data</li>
          <li>Hosted TOPMed or TOPMed-related phenotypic study data files with individual-level
            data</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

This list is not exhaustive of all possible scenarios and is subject to change.  If you have questions about permissible data download please contact [https://biodatacatalyst.nhlbi.nih.gov/contact](https://urldefense.proofpoint.com/v2/url?u=https-3A__biodatacatalyst.nhlbi.nih.gov_contact&d=DwMFAg&c=WO-RGvefibhHBZq3fL85hQ&r=e2NhGl_S3MgYQ2nUSk5Rd0MFsPF-3vp5-hM1VA0Uz38&m=7Gd5tBXrt0vU7XDQ_F4pvKtJYOMOs6ovIGxrZQbfhCc&s=uNYTta08_ieZn79R1F_TPxzGNOyAb5IHhh2UjrBEwFU&e=).

## Sharing Uploaded Data with Collaborators

Allowing users to share data with other collaborators is permissible per BioData Catalyst policy, but platforms are not required to have this sharing capability available on BioData Catalyst for Go Live. The BioData Catalyst user is ultimately responsible for maintaining the confidentiality, integrity, and the availability of any data uploaded or downloaded from the BioData Catalyst ecosystem. It is therefore essential that all users of the BioData Catalyst ecosystem accessing controlled access data understand their responsibilities for ensuring appropriate information security controls and that they work with their institutions to effectively implement those responsibilities. Users can upload their data to a workspace; however, it is the responsibility of the uploader to ensure that data policies and/or permissions are in place to permit data transfer to any users of the shared workspace. Additionally, the uploader should make all collaborators  aware of any Data Use Agreements or Limitations of any newly uploaded data. 

### User Upload/Download Data Policy Reminder

Users will be made aware and/or reminded of the data upload and download policy recommendations when working in the BioData Catalyst Ecosystem. The user will see this or similar messaging when working on BioData Catalyst platforms. 

“You are transferring data through the BioData Catalyst security boundary. Downloading controlled-access, individual-level data through BioData Catalyst is prohibited and downloading other types of data is strongly discouraged, due to the sensitive nature of the data hosted on the platform. Please see the Permissible and Prohibited Data Download section of the Data Upload and Download Policy  for more information. Additionally, transferring data may or may not be supported by your Data Use Agreement\(s\), Limitation\(s\), or your Institutional Review Board policies and guidelines. As a BioData Catalyst user, you are solely responsible for adhering to the terms of these policies.”  


