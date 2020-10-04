# Chapter 20 Import

To analyze the information of the items that have been recorded in the XML file that is Import and registered in the database. The system provides the following classes required to import. Each item type inherits these classes to define the overriding item type own import processing methods needed to import.

## 1. Class

Class provided by the system are as follows.

* Imported items class
  * Class name: XooNIpsImportItem
  * Summary: The class that holds the information of imported items
* Imported items handler class
  * Class name: XooNIpsImportItemHandler
  * Summary: class that implements the import processing of imported items class. XooNIpsImportItemHandler class implements the import process of the item. Item type inherits XooNIpsImportItemHandler class, you can implement \(override\) the item type own import processing.

## 2. Class name

The class name is determined as follows based on the item type name.

class  ImportItem

\(Example: XNPBookImportItem, XNPDataImportItem, ...\)

class  ImportItemHandler

\(Example: XNPBookImportItemHandler, XNPDataImportItemHandler, ...\)

4 characters from the beginning is the case

1. The file name, file path

File name and path of the PHP file that defines the class is as follows.

File Path: modules / module name / class /

File name:  \_import\_item.class.php

\(Example: xnpbook\_import\_item.class.php, xnpdata\_import\_item.class.php, ...\)

All file names are lowercase

1. implementation of import items class

4.1. Predefined member variable

The imported items, use the following members variable.

Table 20.1. Member variable list

member Remarks

XooNIpsItemCompo \_item Object that holds the item information. This object is created in the constructor.

4.2. Overriding methods

Methods that item type overrides are as follows.

Table 20.2. Method summary

Method Remarks

int getTotalFileSize \(\) Returns a: The total size of the files attached to the item \(in bytes\)

XooNIpsImportItem & getClone \(\) Create duplicate imported items object \(clone\), and returns the reference

4.3. Constructor

Initialize the member variable $ \_item. Create the ORM object that has been defined for each item type, and assigns a reference. The following is an example of a Data type of constructor.

function XNPDataImportItem \(\) {

$ Handler = & xoonips\_getormcompohandler \( 'xnpdata', 'item'\);

$ This -&gt; \_item = & $ handler -&gt; create \(\);

}

1. implementation of import items handler class

5.1. Predefined member variable

The imported items handler uses the following member variable.

Table 20.3. Member variable list

member Remarks

string \[\] \_tag\_stack Stack to manage the element name of the XML being analyzed. Element name of the route to the top of the array, the last element name of the current analysis will be recorded.

string \_cdata String of CDATA part of the elements of the current in the analysis are stored. However, xmlEndElementHandler \( Section 5.5., "End element handler \(xmlEndElementHandler\)" until\) is called, please note that it is not to confirm the value of this member.

XooNIpsImportItem \_import\_item Import item object. Set the information of the items obtained by analyzing the XML to this object. This object is created in the constructor.

string \_attachment\_dir File path imported attachments are temporarily stored \(absolute path\).

5.2. Overriding methods

Methods that item type overrides are as follows.

Table 20.4. Method summary

Method Remarks

XooNIpsImportItem create \(\) It creates and returns an import item object in accordance with the item type.

void xmlStartElementHandler \($ parser, $ name, $ attribs\) It will be called back to when analyzing the start element of the XML file. It defines the analysis process of the start element of Detail Information.

void xmlEndElementHandler \($ parser, $ name\) It will be called back to when analyzing the end element of the XML file. It defines the analysis process of the end elements of the Detail Information.

void onImportFinished \(& $ item, & $ import\_items\) You define the operation of the item after a successful import.

bool insert \(& $ item\) Run the insert of the item object.

viod setNew \(& $ item\) Run the setNew of the item object.

viod unsetNew \(& $ item\) Run the unsetNew of the item object.

viod setDirty \(& $ item\) Run the setDirty of the item object.

viod unsetDirty \(& $ item\) Run the unsetDirty of the item object.

string getImportLog \($ import\_item\) Create the import result log.

void import \(& $ item\) Run the import.

5.3. Constructor

It calls the constructor of the super class. The following is an example of a Data type of constructor.

function XNPDataImportItemHandler \(\) {

parent :: XooNIpsImportItemHandler \(\);

}

5.4. Start element handler \(xmlStartElementHandler\)

void xmlStartElementHandler \($ parser, $ name, $ attribs\)

To import XML files and system analysis, it will be called back when it was used to find the beginning element. Processing that require the attribute value of the element is defined here. Item type does the processing of the following in this function.

Call the xmlStartElementHandler superclass

An analysis of the start element

Information attached to the start element is given in the argument. The arguments are as follows.

$ Parser: the XML parser Reference

$ Name: element name

$ Attribs: attributes of the associative array

$ Parser is a reference of the XML parser that is created in xml\_parser\_create. If the XML of the relevant information \(such as the line number in the analysis\) the analysis is required, you can use this reference. Please refer to the information about the XML function of PHP for more information.

$ Name is a string of element name. Regardless of the writing in the XML file, the element name will be converted to uppercase.

$ Attrib holds the defined attribute names and values ​​in the start element in the form of an associative array.

All the above argument, the same as the start element handler XML function of PHP has to offer. Please refer to the information about the XML function of PHP \(such as xml\_set\_element\_handler\) for more information.

There is no return value.

All, errors in the process is recorded using the setErrors method of \_import\_item members. Please refer to the XooNIpsImportItem for details.

5.4.1. Call the start element handler of the superclass

parent :: xmlStartElementHandler \($ parser, $ name, $ attribs\);

At the beginning of the start element handler, call the start element handler of the super class as above. Please be sure to call.

5.4.2 carry out the analysis of. Start element

It refers to the member variable \_tag\_stack, to determine the current analysis target element, to define the process that was in element

The following is a sample that defines the processing of each element.

switch \(implode \( '/', $ this -&gt; \_tag\_stack\)\) {

case "ITEM / DETAIL":

//   to define the processing of the tag here.

break;

case "ITEM / DETAIL / FOO":

//    to define the processing of the tag here.

break;

}

5.5. End element handler \(xmlEndElementHandler\)

void xmlEndElementHandler \($ parser, $ name\)

To import XML files and system analysis, it will be called back when it finds the end element. Processing, which refers to the elements of the CDATA is defined in this method. Item type does the processing of the following in this function.

An analysis of the end element

Call the xmlEndElementHandler superclass

Information about the end element is given in the argument. The arguments are as follows. Commentary of argument is section 5.4. "Start element handler \(xmlStartElementHandler\)" Please refer to.

$ Parser: the XML parser Reference

$ Name: element name

There is no return value.

5.5.1. Carry out an analysis of the end element

It refers to the member variable \_tag\_stack, to determine the current analysis target element, to define the process that was in element

The following is a sample that defines the processing of each element.

switch \(implode \( '/', $ this -&gt; \_tag\_stack\)\) {

case "ITEM / DETAIL":

//   to define the processing of the tag here.

break;

case "ITEM / DETAIL / FOO":

//    to define the processing of the tag here.

break;

}

5.5.2. Call the end element handler of the superclass

parent :: xmlEndElementHandler \($ parser, $ name\);

At the end of the end element handler, it calls the end element handler of the super class as above. Please be sure to call.

5.6. The item of the insert \(insert\)

bool insert \(& $ item\)

To insert an item obtained by analyzing the XML in the database, and returns the success or failure. Processing delegates to XooNIpsItemCompoHandler.

function insert \(& $ item\) {

$ Handler = & xoonips\_getormcompohandler \( 'xnpdata', 'item'\);

return $ handler -&gt; insert \($ item\);

}

5.7. Items of new flag set \(setNew\)

void setNew \(& $ item\)

To import item object, and then set a new flag that represents a new item. Processing delegates to XooNIpsItemCompoHandler.

function setNew \(& $ item\) {

$ Handler = & xoonips\_getormcompohandler \( 'xnpdata', 'item'\);

$ Handler -&gt; setNew \($ item\);

}

5.8. New flag cancellation of item \(unsetNew\)

void unsetNew \(& $ item\)

To release the new flag of the imported item object. Processing delegates to XooNIpsItemCompoHandler.

function unsetNew \(& $ item\) {

$ Handler = & xoonips\_getormcompohandler \( 'xnpdata', 'item'\);

$ Handler -&gt; unsetNew \($ item\);

}

5.9. Items of dirty flag set \(setDirty\)

void setDirty \(& $ item\)

To import item object, sets the dirty flag indicating that the content has been changed. Processing delegates to XooNIpsItemCompoHandler.

function setDirty \(& $ item\) {

$ Handler = & xoonips\_getormcompohandler \( 'xnpdata', 'item'\);

$ Handler -&gt; setDirty \($ item\);

}

5.10. Dirty flag cancellation of item \(unsetDirty\)

void unsetDirty \(& $ item\)

It clears the dirty flag of the imported item object. Processing delegates to XooNIpsItemCompoHandler.

function unsetDirty \(& $ item\) {

$ Handler = & xoonips\_getormcompohandler \( 'xnpdata', 'item'\);

$ Handler -&gt; unsetDirty \($ item\);

}

5.11. Creating an import log \(getImportLog\)

string getImportLog \($ import\_item\)

And returns information about the items in the import process in the log format string. Do the processing in the following procedure.

Call the getImportLog superclass

To add an item type own log

5.11.1. Call the getImportLog superclass

Call the getImportLog of super class, to get the import log for Basic Information. The acquired string, and then add the item type own log.

$ Text = parent :: getImportLog \($ import\_item\);

Basic Information of the log is generated in the following format.

basic.   \(new line\)

Field name and its value are as follows.

Table 20.5. Field List

Field name Content

id Item ID \(provisional\)

title title

contributor Author of UID

itemtype Item Type ID

keyword keyword

description comment

doi ID

last\_update\_date Integer representation of the Last updated

creation\_date Integer representation of the creation date

publication\_year Publication year

publication\_month Issue month

publication\_mday date of issue

lang language

filename XML file name of the import file

url URL of the detail screen of the imported item \(at the time of import failure or when the test run is an empty string\)

related\_to ID of related items \(at the time of the test is running provisional item ID\)

index Import index ID

5.11.2. To add an item type own log

Add the item type own log. The information in the Detail Information to create according to the following format.

detail.   \(new line\)

If the field value, including the special character shown in the table below, you must have escaped by the  symbol.

Table 20.6. Escaping rules

Escape before After escape

 \

\(Newline character\)  N

The following is an example.

$ Detail = & $ import\_item -&gt; getVar \( 'detail'\);

$ Text. = " Ndetail.readme". Mb\_ereg\_replace \(

' N', ' n', mb\_ereg\_replace \(

'\\', '\\', $ Detail -&gt; getVar \( 'readme', 'n'\)\)\);

5.12. Corresponding to the attachment

If the item type has an attached file, you also need the following definition.

Definition of member variables

The definition of the start element handler

The definition of the end element handler

Definition of import end event processing method

5.12.1. Definition of member variables

To deal with the attachments, and then declare a member variable to hold the file object to import item handler.

5.12.2. The definition of the start element handler

Add the process of attachment to the start element handler.

Information of the attached file is defined in the FILE element. Start element handler, perform the following processing in the analysis of the FILE element.

Create a file object, set the member variable

Set the path of the attachment to a file object

Set the meta information of the file to the file object

Create a file object at the beginning. Session ID, also sets the file type ID. File type ID, you can query retrieve the file type ID corresponding to the value of the attribute FILE\_TYPE\_NAME in the database.

$ File\_type\_handler = & xoonips\_getormhandler \( 'xoonips', 'file\_type'\);

$ Criteria = new Criteria \( 'name', addslashes \($ attribs \[ 'FILE\_TYPE\_NAME'\]\)\);

$ File\_type = & $ file\_type\_handler -&gt; getObjects \($ criteria\);

$ File\_handler = & xoonips\_getormhandler \( 'xoonips', 'file'\);

$ This -&gt; \_file\_member = & $ file\_handler -&gt; create \(\);

$ This -&gt; \_file\_member -&gt; set \( 'sess\_id', session\_id \(\)\);

$ This -&gt; \_file\_member -&gt; set \( 'file\_type\_id', $ file\_type \[0\] -&gt; get \( 'file\_type\_id'\)\);

Then, set the attached file is placed path to the file object. Attachments are stored in a temporary folder that the system is secured. Path to the temporary folder you can get a member variable \_attachment\_dir. The attachment name is given by FILE\_NAME attribute. In the following manner, please set the path of the attachment to a file object.

$ This -&gt; \_file\_member -&gt; setFilepath \(.. $ This -&gt; \_attachment\_dir '/' $ attribs \[ 'FILE\_NAME'\]\);

Finally, to get the attributes for the file from the FILE element, and then set the file object. Please set the following information in the file object.

Table 20.7. Attribute list

Attribute name Remarks

ORIGINAL\_FILE\_NAME Original file name

MIME\_TYPE mime-type

FILE\_SIZE File size \(bytes\)

5.12.3. The definition of the end element handler

As well as the start element handler, and then add the processing of the attachments to the end element handler. In the end element handler performs the following processing.

Analysis of caption

Analysis of the thumbnail image

Record the file to the database

5.12.3.1. Analysis of caption

If the attachment is a preview image, to get the image caption. Because the caption is defined by the CAPTION child element of the FILE, to get the caption from \_cdata member variables in the analysis of the end elements of the CAPTION. Acquired caption will be set in the file object.

case 'ITEM / DETAIL / FILE / CAPTION':

$ Unicode = & xoonips\_getutility \( 'unicode'\);

$ This -&gt; \_file\_member -&gt; set \(

'Caption',

$ Unicode-&gt; decode\_utf8 \(

$ This -&gt; \_cdata, xoonips\_get\_server\_charset \(\), 'h'\)\);

}

break;

5.12.3.2. Analysis of the thumbnail image

If the attachment is a preview image, you get a thumbnail image of the image. Since the thumbnail image is defined by the CAPTION child element of the FILE, to get the thumbnail image from \_cdata member variables in the analysis of the end elements of the CAPTION. Since the acquired thumbnail image is a string that has been encoded in base64, and then set the file object on the decoded.

case 'ITEM / DETAIL / FILE / THUMBNAIL':

$ This -&gt; \_file\_member -&gt; set \( 'thumbnail\_file',

base64\_decode \($ this -&gt; \_cdata\)\);

break;

5.12.3.3. Recording the files to the database

In the analysis of the end elements of FILE, to record the contents of the file object in the database. The recorded file object, and then set to import item object.

Because this item ID has not been determined at the time, the item ID is also in the file object to be recorded will not be recorded. After the import of the item is successful item ID has been determined, and updates the item ID of the file object. Update of the item ID, import end event processing method \( section 5.12.4. "Defining the import end event processing method" done in\).

case "ITEM / DETAIL / FILE":

$ File\_handler = & xoonips\_getormhandler \( 'xoonips', 'file'\);

if \($ file\_handler -!&gt; insert \($ this -&gt; \_file\_member\)\) {

$ This -&gt; \_import\_item -&gt; setErrors \(

E\_XOONIPS\_DB\_QUERY,

"I can not insert attachment file:"

. $ This -&gt; \_file\_member -&gt; get \( 'original\_file\_name'\)

. $ This -&gt; \_get\_parser\_error\_at \(\)\);

}

$ This -&gt; \_file\_member = $ file\_handler -&gt; get \(

$ This -&gt; \_file\_member -&gt; get \( 'file\_id'\)\);

$ This -&gt; \_import\_item -&gt; setVar \( 'file\_member',

$ This -&gt; \_file\_member\);

$ This -&gt; \_import\_item -&gt; setHasDataFile \(\);

break;

5.12.4. Definition of import end event processing method

void onImportFinished \(& $ item, & $ import\_items\)

Only if the requested import was successful all, the system, and callback the import end event processing method function. For each of the items that have been imported, this method will be called back.

// Callback processing image of

// \(In practice corresponding to the respective item type

// Call back the method of imported items handler. \)

foreach \($ import\_items as $ item\) {

$ Handler-&gt; onImportFinished \($ item, $ import\_items\);

}

Argument is as follows.

$ Item: Imported items

$ Import\_items: Imported array of all the items

This method defines the following processing.

Delete the existing attachments

Update of the attached file information

Creating a full-text search index

Call the super class

5.12.4.1. Delete the existing attachments

Only if you overwrite imported into an existing item, delete the files that had been previously attached. This process is defined as a method of the superclass. Please put out call in the following manner. The caller, you do not need to check whether or not it is overwritten import.

$ This -&gt; \_set\_file\_delete\_flag \($ item\);

5.12.4.2. Update of the attached file information

Section 5.12.3.3. "Recording the file to the database." As mentioned in, and set the item ID that was determined by the success of the import in the attached file. Since the processing is defined as methods of the super class, sure to call in the following manner. $ item is import item object given in the first argument of this method.

$ File\_member = & $ item -&gt; getVar \( 'file\_member'\);

$ This -&gt; \_fix\_item\_id\_of\_file \($ item, $ file\_member\);

5.12.4.3. Creating a full-text search index

To enable search the contents of the attached file, to create a full-text search index. Since the processing is defined as a method of super class, please call in the following manner. $ Item is imported items objects that were given in the first argument of this method. $ To get the object of attachment from the item, please specify it in the argument of the method.

$ File\_member = & $ item -&gt; getVar \( 'file\_member'\);

$ This -&gt; \_create\_text\_search\_index \($ file\_member\);

5.12.4.4. Call the super class

Finally, we call the same name of the method of the superclass. In the super class, in order to build a related item of items between you import, it is set to a related item information defined item ID.

parent :: onImportFinished \($ item, $ import\_items\);

1. Other function

6.1. Error function \(setErrors\)

XooNIpsImportItem :: setErrors \($ err\_code, $ err\_str\)

If an error occurs during processing, to record the error information using this method. The system will refer to this information, the judgment of the success or failure of the treatment, make, such as the output of the error information. If an error occurs during the processing of the imported items handler, set the o error information to \_import\_item member variable as follows.

$ This -&gt; \_import\_item -&gt; setErrors \(E\_XOONIPS\_ATTACHMENT\_HAS\_REDUNDANT,

"Multiple attachment is not allowed"\);

The arguments are as follows.

$ Err\_code: error code

$ Err\_str: textual explanation of the error

$ Err\_code will use to choose one appropriate code from the following error code that is determined in advance. These are defined in condefs.h.

Table 20.8. Error Code List

Error code defined name value Overview

E\_XOONIPS\_SUCCESS E0000 success

E\_XOONIPS\_ERROR E0001 error

E\_XOONIPS\_PARSER E0002 Error of XML parsing

E\_XOONIPS\_USER\_NOT\_FOUND E0003 Not a user is not found

E\_XOONIPS\_DB\_QUERY E0004 Error in DB operation

E\_XOONIPS\_ATTR\_REDUNDANT E0005 Redundant \(such as the exclusive use of attributes are both specified\)

E\_XOONIPS\_ATTR\_NOT\_FOUND E0006 Attribute is not defined

E\_XOONIPS\_ATTR\_INVALID\_VALUE E0007 Invalid attribute value \(in the form abnormal, such as unknown attribute value\)

E\_XOONIPS\_DATA\_TOO\_LONG E0008 It is too long the specified data

E\_XOONIPS\_INDEX\_NOT\_FOUND E0009 Not specified index does not exist

E\_XOONIPS\_OPEN\_FILE E0010 Failed to open file

E\_XOONIPS\_RELATED\_ITEM\_IS\_NOT\_FOUND E0011 Not find the specified related items

E\_XOONIPS\_FILE\_SYSTEM E0012 File systems in general

E\_XOONIPS\_IMPORT E0013 Error of the import operation

E\_XOONIPS\_INVALID\_VALUE E0014 Malformed, unknown value of the CDATA value

E\_XOONIPS\_VALUE\_IS\_REQUIRED E0015 Not essential values ​​are specified

E\_XOONIPS\_NO\_PRIVATE\_INDEX E0016 Items to be imported is not registered in the private index

E\_XOONIPS\_ATTACHMENT\_HAS\_REDUNDANT E0017 I was trying to import more than necessary attachments

E\_XOONIPS\_NOT\_PERMITTED\_ACCESS E0018 Items, there is no access to the index, such as

E\_XOONIPS\_TAG\_NOT\_FOUND E0019 Not found can not be omitted XML tags

E\_XOONIPS\_INVALID\_VERSION E0020 Unknown version \(version attribute value\)

E\_XOONIPS\_PSEUDO\_ID\_CONFLICT E0021 Multiple XML files with the same ID is found in the import file

E\_XOONIPS\_RELATED\_TO\_CONFLICTING\_ITEM E0022 Are related item is duplicated

E\_XOONIPS\_TAG\_REDUNDANT E0023 Redundant tags \(tags are duplicated, use the number is too large\)

E\_XOONIPS\_DOI\_CONFLICT E0024 The value of the DOI field of the item is a duplicate of the existing items

E\_XOONIPS\_UPDATE\_CERTIFY\_REQUEST\_LOCKED E0025 Can not be updated because the item is locked

