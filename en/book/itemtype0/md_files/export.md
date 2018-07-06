##Chapter 19 Export

Item, the index is expressed in XML and then Export. The item type module that you want to correspond to the Export, please defines the following function always.

####1. License agreement

Whether or not the license agreement is necessary Upon to Export, and you need to return the license statement to XooNIps. Please define the following functions to the item type.

* function <module name> GetLicenseRequired ($ item_id)

    * Argument: item_id (item ID)

    * Returns: If you need agreement true

* function <module name> GetLicenseStatement ($ item_id)

    * Argument: item_id (item ID)

    * Return value: array (license statement, use_cc). If you want to use the license of Creative Commons is a non-false the use_cc by the license statement to html. If the license is not to the return value to NULL.

####2. Export of Detail Information

Returns a string representation of the item type of Detail Information in XML file. Begins with <DETAIL>, </ DETAIL> in the tag that ends with, you can define the item type own tag.

* function <module name> ExportItem ($ export_path, $ fhdl, $ item_id, $ attachment)

     * Argument: export_path (when you export a file attachment, please pass this argument to the first argument of xnpExportFile)

     * Argument: fhdl (output destination file handle)

     * Argument: item_id (item ID)

     * Argument: attachment (. If the attached file to Export true and not if false.)

     * Returns: If success true. If failure false.

Please also refer to the following function.

* xnpExportFile
