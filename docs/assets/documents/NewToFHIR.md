[Return](../../index.md)


# New to FHIR?

**Table of contents**
- [1 FHIR glossary](#1-fhir-glossary)
- [2 How to read a MedCom Implementation Guide](#2-how-to-read-a-medcom-implementation-guide)
- [3 More information](#3-more-information)
  * [3.1 Webinars](#31-webinars)
  * [3.2 HL7 FHIR documentation](#32-hl7-fhir-documentation)
<!-- - [5 Release Notes](#5-release-notes) -->

The purpose of this section is to give an introduction to MedCom's FHIR standards to stakeholders with no or limited knowledge about FHIR. On this page, you will find a brief introduction to the most frequently used terms and guidance to more information about FHIR and MedComs FHIR standards. 


## 1 FHIR Glossary
<a href="https://www.hl7.org/fhir/" target="_blank">Fast Healthcare Interoperability Resources (FHIR&reg;&copy;)</a> is developed by the international organization Health Level 7 (HL7) and is an open-source standard developed to exchange healthcare-related information. FHIR defines several resources, often referred to as ‘building blocks’, each describing a delimited area within healthcare e.g., a Patient or an Encounter. These resources are generic and can therefore be used across the world. However, when using the resources in a specific context, such as communication between Danish healthcare parties, the resources need to be profiled to accommodate the use. The profiling could be to require the last name of a Patient. In some cases, it is necessary to extend the generic resources to fit the context e.g., to add a civil registration number (Danish: CPR-nummer) as a patient identifier.

When creating a MedCom FHIR standard, multiple profiles are assembled to include the information necessary to support the business requirements. Under the auspices of MedCom, these profiles will most often come from multiple Implementation Guides (IG). This decision is further addressed in  section "[Why are there Multiple Implementation Guides?](FAQ.md)" that can be founded in the Frequen aked qestions page.  

The first wave of MedCom's modernisation only includes messages, which means that there must always be a sender and a receiver. A relevant exchange paradigm could be to upload data as services or as documents where multiple receivers can get access to data or documents. If another exchange exchange paradigm is to be used, it is possible to reuse the profiles from the Core IG. This is an example of FHIR's reusability across. The optimal exchange paradigm for a standard will be considered when modernizing the next wave of MedCom standards.

In the <a href="#Tab1">Table 1</a>  you will find the most common terms and associated descriptions and examples. These terms all describe a fundamental feature in FHIR, and they make the foundation to understand FHIR, and why they are presented initially.

> Note: the <a href="#Tab1">Table 1</a>  uses FHIR-paths to describe exactly which element is referred to e.g. Patient.name refers to the nameelement in the Patient resource.

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:65%;width:75%;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-1wig{font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-az2b{background-color:#FFF;color:#333333;font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-316y{color:#2c415c;font-weight:bold;text-align:center;vertical-align:middle}
.tg .tg-t3tv{color:#333333;text-align:left;vertical-align:middle}
.tg .tg-cxm4{color:#333333;font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-4m1j{color:#333333;text-align:left;text-decoration:underline;vertical-align:top}
</style>
<div style="overflow-x:auto;">
<table class="tg" id="Tab1">
<caption style="color:#2c415c;font-weight:bold">Table 1: Most used terms in MedCom's FHIR universe</caption>
<thead>
  <tr>
    <th class="tg-316y">Term</th>
    <th class="tg-316y">Description</th>
    <th class="tg-316y">Example</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-1wig"><span style="font-weight:bold">Implementation Guide (IG)</span></td>
    <td class="tg-t3tv">The technical specification of a MedCom FHIR standard. A set of rules and associated documentation describing, how FHIR profiles should be implemented to accommodate a given standard and requirements.</td>
    <td class="tg-t3tv"> <a href="http://medcomfhir.dk/ig/acknowledgement/" target="_blank">Acknowledgement IG </a>, 
    <a href="http://medcomfhir.dk/ig/hospitalnotification/" target="_blank">HospitalNotification IG </a>, 
    <a href="https://build.fhir.org/ig/medcomdk/dk-medcom-carecommunication/" target="_blank">CareCommunication IG </a>, 
    <a href="http://medcomfhir.dk/ig/terminology/" target="_blank">Terminology IG </a>, 
    <a href="http://medcomfhir.dk/ig/core/" target="_blank">Core IG target="_blank"</a>,
    <a href="http://medcomfhir.dk/ig/messaging/" target="_blank">Messagaging IG </a> 
    </td>
  </tr>
  <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">Standard</span></td>
    <td class="tg-t3tv">FHIR standard define how health and care information can be exchanged between providers and their system regardles of how the information is stored in those systems. </td>
    <td class="tg-t3tv">MedCom FHIR standards are HospitalNotification, CareCommunication</td>
  </tr>
  <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">Element</span></td>
    <td class="tg-t3tv">A resource consists of multiple elements each describing a specific part of the content.</td>
    <td class="tg-t3tv">Patient.name or Patient.address.</td>
  </tr>
  <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">Cardinality</span></td>
    <td class="tg-t3tv">Each element is described with a minimum and maximum cardinality, describing how many times an element may or shall appear:<br>
    <ul>
      <li> If the minimum cardinality is 0, the element may appear</li>
      <li> If the minimum cardinality is 1, or more the element shall at least appear the number of times stated.</li>
      <li> If the maximum cardinality is 0, the element must not appear</li>  
      <li> If the maximum cardinality is 1, the element may not appear more than once</li>
      <li> If the maximum cardinality is *, the element may appear several times  </li>    
    </ul>
    </td>
    <td class="tg-t3tv">In the generic resource <I>Patient.name</I> has the cardinality 0..*, meaning a patient may have zero or more names.<br>In the generic resource <I>Encounter.status</I> has the cardinality 1..1, meaning that a status always shall appear, and in may only appear once.</td>
  </tr>
   <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">Resources</span></td>
    <td class="tg-t3tv">FHIR consists of generic resources, each describing a clinically delimited area. Resources are 'building blocks' defined by HL7.</td>
    <td class="tg-t3tv">A Patient resource, an Allergy resource, an Observation resource, an Encounter resource ect.</td>
  </tr>
   <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">Profile</span></td>
    <td class="tg-t3tv">FHIR profile is a set of specified constrains and/or extensions on the base resource</td>
    <td class="tg-t3tv"><a href="https://medcomfhir.dk/ig/messaging/profiles.html">MedComMessaging profiles </a>, <br> <a href="https://medcomfhir.dk/ig/core/profiles.html"  target="_blank">MedComCore profiles</a> </td>
  </tr>
  <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">Profiling</span></td>
    <td class="tg-t3tv">Profiling allow to fit resource to a given context, by defining constrains and/or bydefine extensions. It is widely recognized that when exchanging data it is impossible to make a one size fits all within healthcare worldwide.<br>To accommodate this, the resources made generic with the possibility to be profiled to fit a specific context, such as exchanging a CareCommunication message between Danish healthcare parties.</td>
    <td class="tg-t3tv">Profiling could be to require a lastname and an identifier of a patient or citizen when exchanging information about the person.</td>
  </tr>
  <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">Extensions</span></td>
    <td class="tg-t3tv">To extend a resource to include additional information than defined by HL7. </td>
    <td class="tg-t3tv"> Extending the MedCom MessageHeader with a reportOfAdmissionFlag.</td>
  </tr>
  <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">CodeSystem</span></td>
    <td class="tg-t3tv">A collection of codes, which can be predetermined by HL7, from a international terminology or defined by the developer of the IG.</td>
    <td class="tg-t3tv">Predetermined by HL7 e.g. <a href="http://hl7.org/fhir/valueset-administrative-gender.html" target="_blank" rel="noopener noreferrer"><span style="text-decoration:none">gender</span></a>, from an international terminology e.g. <a href="https://browser.ihtsdotools.org/?" target="_blank" rel="noopener noreferrer"><span style="text-decoration:none">SNOMED CT</span></a>, or defined by the developer of the IG e.g. <a href="https://medcomfhir.dk/ig/terminology/CodeSystem-medcom-careCommunication-categoryCodes.html" target="_blank" rel="noopener noreferrer"><span style="text-decoration:none">categories </span></a>categories in a CareCommunication message.</td>
  </tr>
  <tr>
    <td class="tg-az2b"><span style="font-weight:bold;background-color:#FFF">ValueSet</span></td>
    <td class="tg-t3tv">A collection of codes from one or more CodeSystems. ValueSets can either include all codes from a CodeSystem or only some codes.</td>
    <td class="tg-tysj"><a href="https://medcomfhir.dk/ig/terminology/ValueSet-medcom-messaging-messageTypes.html" target="_blank" rel="noopener noreferrer">MedComMessagingMessageTypes</a>  is a ValueSet that includes all codes from the <a href="https://medcomfhir.dk/ig/terminology/CodeSystem-medcom-messaging-eventCodes.html" target="_blank" rel="noopener noreferrer">MedComMessagingEvents</a> CodeSystem. The ValueSet includes the codes for MedComs FHIR standards</td>
  </tr>
  <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">MustSupport</span></td>
    <td class="tg-t3tv">Indicates which information which shall be included in a MedCom standard if available in the sender systemer and which information the receiver system shall be able to handle. MustSupport is defined during profiling of the resource.</td>
    <td class="tg-t3tv">The elements Patient.identifier, Patient.name and Patient.address does all have the flag MustSupport in the <a href="https://medcomfhir.dk/ig/core/StructureDefinition-medcom-core-patient.html" target="_blank"> MedComCorePatient</a> profile.</td>
  </tr>
  <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">Modifier</span></td>
    <td class="tg-t3tv">An element which modifies or changes the understanding of the resource. '!?' indicates in the IG that the element is a modifier element, which is often defined in the generic resource or in developed extensions</td>
    <td class="tg-t3tv">Patient.deceased is a modifier element, since is modifies the way the content of the profile should be understood, if the patient is deceased.</td>
  </tr>
  <tr>
    <td class="tg-cxm4"><span style="font-weight:bold">Narrative</span></td>
    <td class="tg-t3tv"> A textual summary of the information   in a message which can be   used to display information if the structured data cannot be displayed. All   information in a message shall be included in the summary. <br>Description:    </td>
    <td class="tg-t3tv">All content from a message, including the patients name or CPR-number and the written correspondence in a CareCommunication message.</td>
  </tr>
</tbody>
</table>
</div>
<br>
<br>

## 2 How to read a MedCom Implementation Guide
If you are interested in understanding the basic content and the composition of an IG, you can follow this [step-by-step guide](FHIRImplementationGuide.md).



## 3 More information

### 3.1 Webinars
In 2022 MedCom has held  two webinars concerning the modernization of MedCom standards. Both webinars are free and available in Danish:
* <a href="https://www.youtube.com/watch?v=8doBKskz3J8" target="_blank">FHIR-introductionswebinar (17. may 2022)</a>
* <a href="https://www.youtube.com/watch?v=bfzx7U2Suug" target="_blank">FHIR demo-webinar with MedCom, Mjølner and Trifork (10 . february 2022)</a>
<p>&nbsp;</p>

### 3.2 HL7 FHIR Documentation

All FHIR documentation can be found at <a href="https://www.hl7.org/fhir/" target="_blank">www.hl7.org/fhir/</a>. Here you will find detailed descriptions about basic principles, presentations to all resources and much more. 

<!-- ## 5 Release Notes

[The latest changes of this page can be found here.](ReleaseNotesNewToFHIR.md) -->