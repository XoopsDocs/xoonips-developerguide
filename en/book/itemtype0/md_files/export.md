# Chapter 19 Export

Item, the index is expressed in XML and then Export. The item type module that you want to correspond to the Export, please defines the following function always.

## 1. License agreement

Whether or not the license agreement is necessary Upon to Export, and you need to return the license statement to XooNIps. Please define the following functions to the item type.

* function  GetLicenseRequired \($ item\_id\)
  * Argument: item\_id \(item ID\)
  * Returns: If you need agreement true
* function  GetLicenseStatement \($ item\_id\)
  * Argument: item\_id \(item ID\)
  * Return value: array \(license statement, use\_cc\). If you want to use the license of Creative Commons is a non-false the use\_cc by the license statement to html. If the license is not to the return value to NULL.

## 2. Export of Detail Information

Returns a string representation of the item type of Detail Information in XML file. Begins with , &lt;/ DETAIL&gt; in the tag that ends with, you can define the item type own tag.

* function  ExportItem \($ export\_path, $ fhdl, $ item\_id, $ attachment\)
  * Argument: export\_path \(when you export a file attachment, please pass this argument to the first argument of xnpExportFile\)
  * Argument: fhdl \(output destination file handle\)
  * Argument: item\_id \(item ID\)
  * Argument: attachment \(. If the attached file to Export true and not if false.\)
  * Returns: If success true. If failure false.

Please also refer to the following function.

* xnpExportFile

