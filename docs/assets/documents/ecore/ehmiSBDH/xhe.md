([CHG]: Denne side bliver der ikke linket til fra sitet, er den stadig relevante eller skal den slettes?)

# Exchange Header Envelope (XHE) Version 1.0

## 1.1 Overview

File or document headers have long been used to describe the information about a set of payloads in an entity that is kept separate and arm’s-length from the payloads themselves.

The metaphor of a paper envelope in which one places business documents for transport or management is apt to describe the role of an exchange header envelope in a container relationship to its payloads. Concepts of routing, authentication, non-repudiation and concealment all apply in both the metaphor and the electronic equivalent.

## 1.2 What is an Exchange Header Envelope?

The Exchange Header Envelope (XHE) specifies an XML vocabulary [XML] expressing in machine-processable syntax the semantics of describing either a header to or an envelope of a set of payloads of content with information about that content. This vocabulary is modeled using the UN/CEFACT Core Component Technical Specification Version 2.01 [CCTS 2.01].

XHE, a specification developed jointly by UN/CEFACT and OASIS, is the successor to the UN/CEFACT Standard Business Document Header (SBDH) version 1.3 [SBDH] and the OASIS Business Document Envelope (BDE) version 1.1 [BDE].

Note regarding publications
The UN/CEFACT Exchange Header Envelope and the OASIS Exchange Header Envelope are the same specification developed in collaboration and published as standards by the two organizations following the practices of each.

This specification enumerates the information components of a payload header envelope and formally describes the semantics of each component.

Normative markings
All clauses not marked as “informative” and also not a subclause of a clause marked as “informative” are to be considered normative. All notes and examples are informative.

The XHE is designed to be either a header as an integral part of a business document (e.g. either XML instance document or EDI interchange), an object associated with the business document itself, or as an envelope functioning as wrapper that contains one or more business documents.

This specification mandates a suite of XML schemas [XMLSCHEMA-1][XMLSCHEMA-2] and additional limitations describing the document constraints against which a conforming instance SHALL validate without error.

## 1.3 How is it used in EDI and XML environments?

There exist several business document exchange architectures and approaches, some using EDI formats and approaches, some using XML document types, and yet others use different document formats or non-standardized approaches. The XHE is designed to work with any document format and business process, whether standardized or not, and as such supports both the EDI, the XML and any other e-business community. Including a XHE in each instance of the business document reduces the effort needed to route and process documents and permits trading partner organizations to use different implementation approaches.

When implementing EDI, the provision of an additional business document header may not always be necessary, since EDI interchanges already contain functionality for some of the information in the XHE. An example is the EDIFACT UNB interchange header, the UNH message header, and the ‘function’ part of the BGM. The XHE specification allows for this existing approach and provides an option to express additional functionality, such as service and correlation information.

## 1.4 The Scope of the Exchange Header Envelope

Many users, implementers and supporting industry standard bodies are in agreement on the need for an Exchange Header Envelope. In their business-to-business activities, the XHE facilitates several different business needs:

- The routing of business documents from one point to another. This refers not only to the transfer of information from an external originator to receiver, but also from one intermediate application to another. Information in the XHE can help ensure that a document gets to the correct recipient.

- Ensuring integrity and confidentiality of business documents when routed over multiple hops, intermediaries, routers or access points, such as in 4-corner networks and architectures.

- Simplifying the bundling of several business documents or support documents into one package for simplified exchange.

- Facilitating the exchange of location pointers and access credentials to externally located business documents, not suitable for sending through an e-business network. This is necessary when the sending party needs to keep the business document confidential until a specified date (such as in tendering processes), and when sending very large files.

- The simplified processing of documents. Processing refers to taking action on data, for example transforming it from one format into another. Information in the XHE can reduce the effort required to determine the correct processing actions.

- Associating a data message with its originator is important from a business and legal perspective. It is especially important when using intermediaries for data transfer, as information from the transport protocol, may be lost after the initial transmission. Because information in the XHE is retained, it can help ensure that a document’s originator is correctly identified.

In addition to header functions provided by the XHE for routing and/or processing of business documents, there is the need for a completely separate technical communications transport layer. This deals with communications protocols and physical addresses which are outside the scope of this technical specification. Transport specifications including EDIINT-AS2 and ebXML Message Service (ebMS) are among a number of possible transport options that address technical communications needs by defining a separate technical header. The transport layer is completely outside the scope as it is a different layer of the stack.

<a href="https://docs.oasis-open.org/bdxr/xhe/v1.0/xhe-v1.0-oasis.html" target="_blank">XHE hos OASIS</a>
