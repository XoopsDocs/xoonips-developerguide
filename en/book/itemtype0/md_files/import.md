# Chapter 20 Import

To analyze the information of the items that have been recorded in the XML file that is Import and registered in the database. The system provides the following classes required to import. Each item type inherits these classes to define the overriding item type own import processing methods needed to import.

###1. Class

Class provided by the system are as follows.

* Imported items class

    * Class name: XooNIpsImportItem

    * Summary: The class that holds the information of imported items

* Imported items handler class

    * Class name: XooNIpsImportItemHandler

    * Summary: class that implements the import processing of imported items class. XooNIpsImportItemHandler class implements the import process of the item. Item type inherits XooNIpsImportItemHandler class, you can implement (override) the item type own import processing.

###2. Class name

The class name is determined as follows based on the item type name.

class <item type name> ImportItem

(Example: XNPBookImportItem, XNPDataImportItem, ...)

class <item type name> ImportItemHandler

(Example: XNPBookImportItemHandler, XNPDataImportItemHandler, ...)

4 characters from the beginning is the case

3. The file name, file path

File name and path of the PHP file that defines the class is as follows.

File Path: modules / module name / class /

File name: <item type name> _import_item.class.php

(Example: xnpbook_import_item.class.php, xnpdata_import_item.class.php, ...)

All file names are lowercase

4. implementation of import items class

4.1. Predefined member variable

The imported items, use the following members variable.

Table 20.1. Member variable list

member Remarks

XooNIpsItemCompo _item Object that holds the item information. This object is created in the constructor.

4.2. Overriding methods

Methods that item type overrides are as follows.

Table 20.2. Method summary

Method Remarks

int getTotalFileSize () Returns a: The total size of the files attached to the item (in bytes)

XooNIpsImportItem & getClone () Create duplicate imported items object (clone), and returns the reference

4.3. Constructor

Initialize the member variable $ _item. Create the ORM object that has been defined for each item type, and assigns a reference. The following is an example of a Data type of constructor.

 function XNPDataImportItem () {

 $ Handler = & xoonips_getormcompohandler ( 'xnpdata', 'item');

 $ This -> _item = & $ handler -> create ();

 }

5. implementation of import items handler class

5.1. Predefined member variable

The imported items handler uses the following member variable.

Table 20.3. Member variable list

member Remarks

string [] _tag_stack Stack to manage the element name of the XML being analyzed. Element name of the route to the top of the array, the last element name of the current analysis will be recorded.

string _cdata String of CDATA part of the elements of the current in the analysis are stored. However, xmlEndElementHandler ( Section 5.5., "End element handler (xmlEndElementHandler)" until) is called, please note that it is not to confirm the value of this member.

XooNIpsImportItem _import_item Import item object. Set the information of the items obtained by analyzing the XML to this object. This object is created in the constructor.

string _attachment_dir File path imported attachments are temporarily stored (absolute path).

5.2. Overriding methods

Methods that item type overrides are as follows.

Table 20.4. Method summary

Method Remarks

XooNIpsImportItem create () It creates and returns an import item object in accordance with the item type.

void xmlStartElementHandler ($ parser, $ name, $ attribs) It will be called back to when analyzing the start element of the XML file. It defines the analysis process of the start element of Detail Information.

void xmlEndElementHandler ($ parser, $ name) It will be called back to when analyzing the end element of the XML file. It defines the analysis process of the end elements of the Detail Information.

void onImportFinished (& $ item, & $ import_items) You define the operation of the item after a successful import.

bool insert (& $ item) Run the insert of the item object.

viod setNew (& $ item) Run the setNew of the item object.

viod unsetNew (& $ item) Run the unsetNew of the item object.

viod setDirty (& $ item) Run the setDirty of the item object.

viod unsetDirty (& $ item) Run the unsetDirty of the item object.

string getImportLog ($ import_item) Create the import result log.

void import (& $ item) Run the import.

5.3. Constructor

It calls the constructor of the super class. The following is an example of a Data type of constructor.

function XNPDataImportItemHandler () {

 parent :: XooNIpsImportItemHandler ();

}

5.4. Start element handler (xmlStartElementHandler)

void xmlStartElementHandler ($ parser, $ name, $ attribs)

To import XML files and system analysis, it will be called back when it was used to find the beginning element. Processing that require the attribute value of the element is defined here. Item type does the processing of the following in this function.

Call the xmlStartElementHandler superclass

An analysis of the start element

Information attached to the start element is given in the argument. The arguments are as follows.

$ Parser: the XML parser Reference

$ Name: element name

$ Attribs: attributes of the associative array

$ Parser is a reference of the XML parser that is created in xml_parser_create. If the XML of the relevant information (such as the line number in the analysis) the analysis is required, you can use this reference. Please refer to the information about the XML function of PHP for more information.

$ Name is a string of element name. Regardless of the writing in the XML file, the element name will be converted to uppercase.

$ Attrib holds the defined attribute names and values ​​in the start element in the form of an associative array.

All the above argument, the same as the start element handler XML function of PHP has to offer. Please refer to the information about the XML function of PHP (such as xml_set_element_handler) for more information.

There is no return value.

All, errors in the process is recorded using the setErrors method of _import_item members. Please refer to the XooNIpsImportItem for details.

5.4.1. Call the start element handler of the superclass

parent :: xmlStartElementHandler ($ parser, $ name, $ attribs);

At the beginning of the start element handler, call the start element handler of the super class as above. Please be sure to call.

5.4.2 carry out the analysis of. Start element

It refers to the member variable _tag_stack, to determine the current analysis target element, to define the process that was in element

The following is a sample that defines the processing of each element.

switch (implode ( '/', $ this -> _tag_stack)) {

case "ITEM / DETAIL":

 // <Item> <detail> to define the processing of the tag here.

 break;

case "ITEM / DETAIL / FOO":

 // <Item> <detail> <foo> to define the processing of the tag here.

 break;

}



5.5. End element handler (xmlEndElementHandler)

void xmlEndElementHandler ($ parser, $ name)

To import XML files and system analysis, it will be called back when it finds the end element. Processing, which refers to the elements of the CDATA is defined in this method. Item type does the processing of the following in this function.

An analysis of the end element

Call the xmlEndElementHandler superclass

Information about the end element is given in the argument. The arguments are as follows. Commentary of argument is section 5.4. "Start element handler (xmlStartElementHandler)" Please refer to.

$ Parser: the XML parser Reference

$ Name: element name

There is no return value.

5.5.1. Carry out an analysis of the end element

It refers to the member variable _tag_stack, to determine the current analysis target element, to define the process that was in element

The following is a sample that defines the processing of each element.

switch (implode ( '/', $ this -> _tag_stack)) {

case "ITEM / DETAIL":

 // <Item> <detail> to define the processing of the tag here.

 break;

case "ITEM / DETAIL / FOO":

 // <Item> <detail> <foo> to define the processing of the tag here.

 break;

}



5.5.2. Call the end element handler of the superclass

parent :: xmlEndElementHandler ($ parser, $ name);



At the end of the end element handler, it calls the end element handler of the super class as above. Please be sure to call.

5.6. The item of the insert (insert)

bool insert (& $ item)

To insert an item obtained by analyzing the XML in the database, and returns the success or failure. Processing delegates to XooNIpsItemCompoHandler.

function insert (& $ item) {

 $ Handler = & xoonips_getormcompohandler ( 'xnpdata', 'item');

 return $ handler -> insert ($ item);

}

5.7. Items of new flag set (setNew)

void setNew (& $ item)

To import item object, and then set a new flag that represents a new item. Processing delegates to XooNIpsItemCompoHandler.

function setNew (& $ item) {

 $ Handler = & xoonips_getormcompohandler ( 'xnpdata', 'item');

 $ Handler -> setNew ($ item);

}



5.8. New flag cancellation of item (unsetNew)

void unsetNew (& $ item)

To release the new flag of the imported item object. Processing delegates to XooNIpsItemCompoHandler.

function unsetNew (& $ item) {

 $ Handler = & xoonips_getormcompohandler ( 'xnpdata', 'item');

 $ Handler -> unsetNew ($ item);

}



5.9. Items of dirty flag set (setDirty)

void setDirty (& $ item)

To import item object, sets the dirty flag indicating that the content has been changed. Processing delegates to XooNIpsItemCompoHandler.

function setDirty (& $ item) {

 $ Handler = & xoonips_getormcompohandler ( 'xnpdata', 'item');

 $ Handler -> setDirty ($ item);

}



5.10. Dirty flag cancellation of item (unsetDirty)

void unsetDirty (& $ item)

It clears the dirty flag of the imported item object. Processing delegates to XooNIpsItemCompoHandler.

function unsetDirty (& $ item) {

 $ Handler = & xoonips_getormcompohandler ( 'xnpdata', 'item');

 $ Handler -> unsetDirty ($ item);

}



5.11. Creating an import log (getImportLog)

string getImportLog ($ import_item)

And returns information about the items in the import process in the log format string. Do the processing in the following procedure.

Call the getImportLog superclass

To add an item type own log

5.11.1. Call the getImportLog superclass

Call the getImportLog of super class, to get the import log for Basic Information. The acquired string, and then add the item type own log.

$ Text = parent :: getImportLog ($ import_item);

Basic Information of the log is generated in the following format.

basic. <field name> <value> (new line)

Field name and its value are as follows.

Table 20.5. Field List

Field name Content

id Item ID (provisional)

title title

contributor Author of UID

itemtype Item Type ID

keyword keyword

description comment

doi ID

last_update_date Integer representation of the Last updated

creation_date Integer representation of the creation date

publication_year Publication year

publication_month Issue month

publication_mday date of issue

lang language

filename XML file name of the import file

url URL of the detail screen of the imported item (at the time of import failure or when the test run is an empty string)

related_to ID of related items (at the time of the test is running provisional item ID)

index Import index ID

5.11.2. To add an item type own log

Add the item type own log. The information in the Detail Information to create according to the following format.

detail. <field name> <value> (new line)

If the field value, including the special character shown in the table below, you must have escaped by the \ symbol.

Table 20.6. Escaping rules

Escape before After escape

\ \\

(Newline character) \ N

The following is an example.

$ Detail = & $ import_item -> getVar ( 'detail');

$ Text. = "\ Ndetail.readme". Mb_ereg_replace (

 '\ N', '\ n', mb_ereg_replace (

 '\\\\', '\\\\', $ Detail -> getVar ( 'readme', 'n')));



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

Create a file object at the beginning. Session ID, also sets the file type ID. File type ID, you can query retrieve the file type ID corresponding to the value of the attribute FILE_TYPE_NAME in the database.

$ File_type_handler = & xoonips_getormhandler ( 'xoonips', 'file_type');

$ Criteria = new Criteria ( 'name', addslashes ($ attribs [ 'FILE_TYPE_NAME']));

$ File_type = & $ file_type_handler -> getObjects ($ criteria);

$ File_handler = & xoonips_getormhandler ( 'xoonips', 'file');

$ This -> _file_member = & $ file_handler -> create ();

$ This -> _file_member -> set ( 'sess_id', session_id ());

$ This -> _file_member -> set ( 'file_type_id', $ file_type [0] -> get ( 'file_type_id'));



Then, set the attached file is placed path to the file object. Attachments are stored in a temporary folder that the system is secured. Path to the temporary folder you can get a member variable _attachment_dir. The attachment name is given by FILE_NAME attribute. In the following manner, please set the path of the attachment to a file object.

$ This -> _file_member -> setFilepath (.. $ This -> _attachment_dir '/' $ attribs [ 'FILE_NAME']);



Finally, to get the attributes for the file from the FILE element, and then set the file object. Please set the following information in the file object.

Table 20.7. Attribute list

Attribute name Remarks

ORIGINAL_FILE_NAME Original file name

MIME_TYPE mime-type

FILE_SIZE File size (bytes)

5.12.3. The definition of the end element handler

As well as the start element handler, and then add the processing of the attachments to the end element handler. In the end element handler performs the following processing.

Analysis of caption

Analysis of the thumbnail image

Record the file to the database

5.12.3.1. Analysis of caption

If the attachment is a preview image, to get the image caption. Because the caption is defined by the CAPTION child element of the FILE, to get the caption from _cdata member variables in the analysis of the end elements of the CAPTION. Acquired caption will be set in the file object.

case 'ITEM / DETAIL / FILE / CAPTION':

 $ Unicode = & xoonips_getutility ( 'unicode');

 $ This -> _file_member -> set (

 'Caption',

 $ Unicode-> decode_utf8 (

 $ This -> _cdata, xoonips_get_server_charset (), 'h'));

 }

 break;



5.12.3.2. Analysis of the thumbnail image

If the attachment is a preview image, you get a thumbnail image of the image. Since the thumbnail image is defined by the CAPTION child element of the FILE, to get the thumbnail image from _cdata member variables in the analysis of the end elements of the CAPTION. Since the acquired thumbnail image is a string that has been encoded in base64, and then set the file object on the decoded.

case 'ITEM / DETAIL / FILE / THUMBNAIL':

 $ This -> _file_member -> set ( 'thumbnail_file',

 base64_decode ($ this -> _cdata));

 break;

5.12.3.3. Recording the files to the database

In the analysis of the end elements of FILE, to record the contents of the file object in the database. The recorded file object, and then set to import item object.

Because this item ID has not been determined at the time, the item ID is also in the file object to be recorded will not be recorded. After the import of the item is successful item ID has been determined, and updates the item ID of the file object. Update of the item ID, import end event processing method ( section 5.12.4. "Defining the import end event processing method" done in).

case "ITEM / DETAIL / FILE":

 $ File_handler = & xoonips_getormhandler ( 'xoonips', 'file');

 if ($ file_handler -!> insert ($ this -> _file_member)) {

 $ This -> _import_item -> setErrors (

 E_XOONIPS_DB_QUERY,

 "I can not insert attachment file:"

 . $ This -> _file_member -> get ( 'original_file_name')

 . $ This -> _get_parser_error_at ());

 }

 $ This -> _file_member = $ file_handler -> get (

 $ This -> _file_member -> get ( 'file_id'));

 $ This -> _import_item -> setVar ( 'file_member',

 $ This -> _file_member);

 $ This -> _import_item -> setHasDataFile ();

 break;



5.12.4. Definition of import end event processing method

void onImportFinished (& $ item, & $ import_items)

Only if the requested import was successful all, the system, and callback the import end event processing method function. For each of the items that have been imported, this method will be called back.

// Callback processing image of

// (In practice corresponding to the respective item type

// Call back the method of imported items handler. )

foreach ($ import_items as $ item) {

 $ Handler-> onImportFinished ($ item, $ import_items);

}



Argument is as follows.

$ Item: Imported items

$ Import_items: Imported array of all the items

This method defines the following processing.

Delete the existing attachments

Update of the attached file information

Creating a full-text search index

Call the super class

5.12.4.1. Delete the existing attachments

Only if you overwrite imported into an existing item, delete the files that had been previously attached. This process is defined as a method of the superclass. Please put out call in the following manner. The caller, you do not need to check whether or not it is overwritten import.

$ This -> _set_file_delete_flag ($ item);



5.12.4.2. Update of the attached file information

Section 5.12.3.3. "Recording the file to the database." As mentioned in, and set the item ID that was determined by the success of the import in the attached file. Since the processing is defined as methods of the super class, sure to call in the following manner. $ item is import item object given in the first argument of this method.

$ File_member = & $ item -> getVar ( 'file_member');

$ This -> _fix_item_id_of_file ($ item, $ file_member);



5.12.4.3. Creating a full-text search index

To enable search the contents of the attached file, to create a full-text search index. Since the processing is defined as a method of super class, please call in the following manner. $ Item is imported items objects that were given in the first argument of this method. $ To get the object of attachment from the item, please specify it in the argument of the method.

$ File_member = & $ item -> getVar ( 'file_member');

$ This -> _create_text_search_index ($ file_member);



5.12.4.4. Call the super class

Finally, we call the same name of the method of the superclass. In the super class, in order to build a related item of items between you import, it is set to a related item information defined item ID.

parent :: onImportFinished ($ item, $ import_items);



6. Other function

6.1. Error function (setErrors)

XooNIpsImportItem :: setErrors ($ err_code, $ err_str)

If an error occurs during processing, to record the error information using this method. The system will refer to this information, the judgment of the success or failure of the treatment, make, such as the output of the error information. If an error occurs during the processing of the imported items handler, set the o error information to _import_item member variable as follows.

$ This -> _import_item -> setErrors (E_XOONIPS_ATTACHMENT_HAS_REDUNDANT,

 "Multiple attachment is not allowed");



The arguments are as follows.

$ Err_code: error code

$ Err_str: textual explanation of the error

$ Err_code will use to choose one appropriate code from the following error code that is determined in advance. These are defined in condefs.h.

Table 20.8. Error Code List

Error code defined name value Overview

E_XOONIPS_SUCCESS E0000 success

E_XOONIPS_ERROR E0001 error

E_XOONIPS_PARSER E0002 Error of XML parsing

E_XOONIPS_USER_NOT_FOUND E0003 Not a user is not found

E_XOONIPS_DB_QUERY E0004 Error in DB operation

E_XOONIPS_ATTR_REDUNDANT E0005 Redundant (such as the exclusive use of attributes are both specified)

E_XOONIPS_ATTR_NOT_FOUND E0006 Attribute is not defined

E_XOONIPS_ATTR_INVALID_VALUE E0007 Invalid attribute value (in the form abnormal, such as unknown attribute value)

E_XOONIPS_DATA_TOO_LONG E0008 It is too long the specified data

E_XOONIPS_INDEX_NOT_FOUND E0009 Not specified index does not exist

E_XOONIPS_OPEN_FILE E0010 Failed to open file

E_XOONIPS_RELATED_ITEM_IS_NOT_FOUND E0011 Not find the specified related items

E_XOONIPS_FILE_SYSTEM E0012 File systems in general

E_XOONIPS_IMPORT E0013 Error of the import operation

E_XOONIPS_INVALID_VALUE E0014 Malformed, unknown value of the CDATA value

E_XOONIPS_VALUE_IS_REQUIRED E0015 Not essential values ​​are specified

E_XOONIPS_NO_PRIVATE_INDEX E0016 Items to be imported is not registered in the private index

E_XOONIPS_ATTACHMENT_HAS_REDUNDANT E0017 I was trying to import more than necessary attachments

E_XOONIPS_NOT_PERMITTED_ACCESS E0018 Items, there is no access to the index, such as

E_XOONIPS_TAG_NOT_FOUND E0019 Not found can not be omitted XML tags

E_XOONIPS_INVALID_VERSION E0020 Unknown version (version attribute value)

E_XOONIPS_PSEUDO_ID_CONFLICT E0021 Multiple XML files with the same ID is found in the import file

E_XOONIPS_RELATED_TO_CONFLICTING_ITEM E0022 Are related item is duplicated

E_XOONIPS_TAG_REDUNDANT E0023 Redundant tags (tags are duplicated, use the number is too large)

E_XOONIPS_DOI_CONFLICT E0024 The value of the DOI field of the item is a duplicate of the existing items

E_XOONIPS_UPDATE_CERTIFY_REQUEST_LOCKED E0025 Can not be updated because the item is locked


