# rights

## Chapter 8 Rights <a id="8-rights"></a>

It handles Copyrights, License or the Creative Commons: see Chapter 7. _TextFile_ for more information．

## 1. array xnpGetRightsDetailBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \) <a id="1-array-xnpgetrightsdetailblock-int-item-id-int-use-cc-1-string-text-int-cc-commercial-use-1-int-cc-modification-2"></a>

### 1.1. Inpet <a id="1-1"></a>

* use\_cc: Select 1 if selecting Some rights reserved, 0 if not
* text: urlencode License Text
* cc\_commercial\_use: Select 1 if you allow for Commercial use, 0 if not
* cc\_modification: Select 2 if you allow for adaptation/alteration, 1 if you allow conditionally, 0 if not

### 1.2. Referenced in the internal $\_POST variable <a id="1-2-post"></a>

None

### 1.3. Screen <a id="1-3"></a>

If you select Some rights reserved will be displayed as follows:

![](../../../.gitbook/assets/xnpGetRightsDetailBlock%20%282%29.gif)

If you select All rights reserved, the screen will be the same as in Chapter 1. \[array xnpGetTextFileDetailBlock\( int item\_id, string name, string text \)\]

### 1.4. Submit Data <a id="1-4"></a>

None

## 2. array xnpGetRightsEditBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \) <a id="2-array-xnpgetrightseditblock-int-item-id-int-use-cc-1-string-text-int-cc-commercial-use-1-int-cc-modification-2"></a>

### 2.1. Input <a id="2-1"></a>

* use\_cc : Some rights reservedを選択なら1，そうでないなら0
* text : urlencodeされたLicense Text
* cc\_commercial\_use : 営利目的利用を許すなら1, そうでないなら0
* cc\_modification : 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

※ $\_POST\["rightsUseCC"\]があれば，これらの引数は全て無視されて以下の$\_POST変数が使用されます．

### 2.2. Referenced in the internal $\_POST variable <a id="2-2-post"></a>

* $\_POST\["rightsUseCC"\] = Some rights reservedを選択なら1，そうでないなら0．
* $\_POST\["rightsEncText"\] = urlencodeされたLicense Text
* $\_POST\["rightsCCCommercialUse"\] = 営利目的利用を許すなら1, そうでないなら0
* $\_POST\["rightsCCModification"\] = 翻案・改変を許すなら2, 条件付で許すなら1, そうでないなら0

### 2.3. Screenshot <a id="2-3"></a>

![](../../../.gitbook/assets/xnpGetRightsEditBlock1%20%282%29.gif)

### 2.4. Submit Data <a id="2-4"></a>

If you click on the "Submit" button → it will open the "Confirmation" screen

* $\_POST\["rightsEncText"\]
* $\_POST\["rightsUseCC"\]
* $\_POST\["rightsCCCommercialUse"\]
* $\_POST\["rightsCCModification"\]

## 3. array xnpGetRightsConfirmBlock\( int item\_id, int maxlen=65535 \) <a id="3-array-xnpgetrightsconfirmblock-int-item-id-int-maxlen-65535"></a>

To generate the HTML for the Confirm screen.

### 3.1. Referenced in the internal $\_POST variable <a id="3-1-post"></a>

* $\_POST\["rightsEncText"\]
* $\_POST\["rightsUseCC"\]
* $\_POST\["rightsCCCommercialUse"\]
* $\_POST\["rightsCCModification"\]

### 3.2. Screenshot <a id="3-2"></a>

Same as → Chapter 1. 「array xnpGetRightsDetailBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)」

### 3.3. Submit Data <a id="3-3"></a>

* $\_POST\["rightsEncText"\]
* $\_POST\["rightsUseCC"\]
* $\_POST\["rightsCCCommercialUse"\]
* $\_POST\["rightsCCModification"\]

### 3.4. Input <a id="3-4"></a>

* maxlen : column of DB size

## 4. array xnpGetRightsRegisterBlock\( \) <a id="4-array-xnpgetrightsregisterblock"></a>

→ Same as Chapter 2. \[array xnpGetRightsEditBlock\( int item\_id, int use\_cc=1, string text='', int cc\_commercial\_use=1, int cc\_modification=2 \)\]

## 5. array xnpGetRights\(\) <a id="5-array-xnpgetrights"></a>

Transmitted data sequence shows in the Confirm screen \( $text, $use\_cc, $cc\_commercial\_use, $cc\_modification \) and return it to. Each item type module records the string obtained in this function to the DB.

