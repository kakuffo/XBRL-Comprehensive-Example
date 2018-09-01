# XBRL-Comprehensive-Example
Overview of Comprehensive Example (DRAFT 2008-03-15)
The “Comprehensive Example” is intended to be a business use case which exercises the characteristics of XBRLS, but is small enough so that it is easy to maintain, easy to use, can be used as a teaching tool, etc.  The financial statement used is not intended to represent a correct financial statement, but rather to be enough of a financial statement so that a business user can get a good feel for the taxonomy and instance document.
THIS VERSION IS A DRAFT!!!  IT IS IMPORTANT THAT ONE UNDERSTAND WHAT IS TRYING TO BE ACCOMPLISHED HERE OR YOU MAY MISS THE POINT OF THIS TEST CASE.
Outstanding Items, Items to be Completed:
The following are outstanding items which still need to be completed:
1.	A number of parts of the taxonomy are created in two ways in order to show people the difference between the two ways.  One example of this is the classes of property, plant and equipment classes expressed in the taxonomy.  One of these approaches will eventually be dropped.
2.	A number of dimensions need to have default dimensions assigned.  This will be done in a later version.
3.	There may be some errors within the meta-patterns as the testing tool is not complete, therefore it cannot be 100% automatically tested at this time.
4.	The company extension and the base taxonomy are combined currently for convenience in editing the taxonomy.  These will be separated eventually.
5.	The modularity of the taxonomy is not as it will be in the final version for the convenience in editing the taxonomy currently.
6.	The [Member] and [Domain] markers are probably going to be removed.
7.	The numbers are probably going to be removed from the extended links, clearly both numbers and the alpha codes are not necessary.
8.	A “Reporting Period [Axis]” was added to experiment with.  This will likely be removed, seems to not work as one might like.


####How to Use this Example:
The ZIP file contains the following:  First, the “target” is a financial statement, see the file:  _Sample-Instance-Proof.pdf.  This is the starting point and the BEST CASE end result.  The goal is to create an XBRL version of the “printed” (PDF).  The PDF is NOT intended to be 100% correct from an accounting perspective.  It is intended to be enough of an accounting example to make it comprehendible to a business user, but exercise all known use cases.  If what is in the PDF can be achieved, then it is highly likely that 98% or more of business use cases can be achieved.
This is an example of what is in the PDF.  This is one page, the income statement.  This can be thought of as ONE example of the 25 or so use cases contended in that PDF:

####Taxonomy:
Next is the taxonomy which has the following file as the entry point of the taxonomy:  gaap.xsd.  (Note that the company taxonomy is not used at this time, it will be added later)
This taxonomy is intended to have 100% of what is needed to create the sample instance document.  It is intended to be compliant to the set of XBRLS meta patterns.  (But this has not been proved with automated testing as of yet.)  The intent is to be able to generate a set of templates complete with synthetic (auto generated) instance document data which could be used as an input template for creating the instance and also for reviewing the instance document once fully created to be sure it is CORRECTY created.  
Note that the taxonomy contains XBRL calculations, UBmatrix proprietary formulas, and aggregator-contributor (cross context) calculations for calculating across XBRL dimensions.  100% of the computations in the instance document are verifiable with these three different types of semantics.

####Neutral Format Table:
This is a sample “neutral format table” (see file _NeutralFormatTemplates-2008-04-18.xls) for the same section of the financial statement, the income statement, from above.  One of these templates exists for every part of what is in the PDF.



####Calculation Validation Report:
See file Sample-Instance-Proof_calctrace.html which is a validation report for what is validated in terms of computations.   This has business rules (formulas), XBRL calculations, and aggregator-contributor type relations.  This is an example from that file for the same portion of the financial statement, the income statement, shown in the above examples.  Again, these calculations exist for EVERY part of the instance document where there is a relation.  All these relations are expressed in the taxonomy.


####XBRL Instance Document:
The actual instance document is in file:  Sample-Instance-Proof.xml.  You can go to that instance and find everything in the PDF.  For example, the above screen shot shows the instance document section of  the same statement as all the other stuff above, the income statement.


####Style Sheet (which is used to create the PDF file):
Finally, there is a style sheet file _Sample-Instance-Proof-ToFO.xsl.  This uses the instance document and when fed to an XSLT processor, it transforms the XBRL into XSL-FO, generating what is in the file:  _Sample-Instance-Proof.fo.  This file is then fed into an XSL-FO Processor which generates PDF, back to the starting point.  That output is file:  _Sample-Instance-Proof.pdf
That is the full cycle of the process.

Again, this is a WORK IN PROGRESS.  There is still a lot of work to do, but one can certainly see the direction in which this is going.  
If you have any questions, please contact Charles.Hoffman@UBmatrix.com

##Comprehensive Example (2008-04-18)

This is an example XBRL instance document.  The purpose of the example is to experiment and try and see how to best make XBRL work.  The example takes each of the XBRLS business use cases, combines them into one taxonomy and instance document.  The example is large enough to look real, but small enough to be a sample.  The following are the components of this example:

####Printed Financial Statement:  (_Sample-Instance-Proof.pdf) This PDF was generated from the instance document (2) and the style sheet (3).

####Instance Document: (Sample-Instance-Proof.xml) This is the XBRL instance document.

####Style Sheet: (_Sample-Instance-Proof-ToFO.xsl)  This is a style sheet which was used to transform the XBRL (2) into PDF (1).
####XSL-FO: (_Sample-Instance-Proof.fo) This is an intermediate format used go get from the style sheet (3) to the PDF (1).  The XSLT in the style sheet generates XSL-FO.  That is sent to an FO processor (FOP) which is what actually generates the PDF.
Taxonomy: (gaap.xsd) This is the taxonomy schema file. Links to the label, references, presentation, calculation, definition, and formulas used can be found within this schema.
####Complex Types: (gaap-ComplexTypes.xsd) This is also a schema.  This contains a number of types defined using XML Schema Part 2.
XBRL Formulas: (gaap-formula.xml) This is an XBRL Formulas linkbase which has a lot, but not all, of the formulas which are used in this financial statement.  This still needs more work and is moving around as XBRL Formulas is still not a recommendation.
####Calculations Report: (Sample-Instance-Proof_calctrace.html) This is an valiation report for the instance documents, showing the calculations which were validated by the XBRL processor.  The XBRL Formulas validation are not shown on this report.
Neutral Format Tables: (_NeutralFormatTemplates-2008-10-10.xls) These are neutral format tables for every section of the instance document. The purpose of this is to show a minimally acceptable rendering of the instance document information with no bias to any type specific rendering characteristics.  This rendering is creatable from information contained within the taxonomy and the instance document. This was hand generated, a theoretical output of an XBRL processor which I believe is possible.
ReadMe (ReadMe.doc) This is a readme file which explains the example.
####ZIP File Containing all Files: (XBRLS-ComprehensiveExample-2008-04-18.zip) This is a ZIP file which can be downloaded to grab all of the files mentioned above.
There are a few other files in the ZIP file but they really are not that interesting.  Note that due to issues relating to default dimensions, this instance document is not 100% representative of what a good instance document would look like.  There are a number of duplicate concepts.