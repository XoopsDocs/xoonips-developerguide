# textfile

## Chapter 7 TextFile

Here we handle the PlainText. Mainly in the form that assumes a long input, you can read the contents of a text file in place of the key input. Key input is also possible.

\($name for discussion see chapter 14. Supplement: Attachment, for $name argument of TextFile system function \)

## 1. array xnpGetTextFileDetailBlock\( int item\_id, string name, string text \) <a id="1-array-xnpgettextfiledetailblock-int-item-id-string-name-string-text"></a>

### 1.1. Referenced in the internal $\_POST variable

None

### 1.2.Screen <a id="1-2"></a>

※ Add as Text ・Add as File become this display.

※ the text of the argument, is displayed in the，&lt;TEXTAREA&gt; … &lt;/TEXTAREA&gt;．

> ![](../../../.gitbook/assets/xnpGetTextFileDetailBlock%20%282%29.gif)

### 1.3. Submit data <a id="1-3"></a>

None

## 2. array xnpGetTextFileEditBlock\(int item\_id, string name, string text \) <a id="2-array-xnpgettextfileeditblock-int-item-id-string-name-string-text"></a>

※ Text を外から引数として与える必要があります．

### 2.1. 内部で参照する $\_POST 変数 <a id="2-1-post"></a>

* $\_POST\["${name}EncText"\]

### 2.2.Screen <a id="2-2"></a>

Screen is the Readme input screen description.ppt

> ![](../../../.gitbook/assets/xnpGetTextFileEditBlock1%20%282%29.gif)

When you press the Edit button, the following screen will open:

> ![](../../../.gitbook/assets/xnpGetTextFileEditBlock2%20%282%29.gif)

When you close the window by pressing the the OK button, the data of the TEXTAREA is transferred to the original form. The window closes without saving only if you press the Cancel button．

### 2.3. Submit data <a id="2-3"></a>

Upload button →

* $\_FILES\['text'\]
* $\_POST\['name'\]

Submit button → to the confirmation screen

* $\_POST\["${name}EncText"\]

## 3. array xnpGetTextFileConfirmBlock\( int item\_id, string name, int maxlen=65535 \) <a id="3-array-xnpgettextfileconfirmblock-int-item-id-string-name-int-maxlen-65535"></a>

To generate the HTML for the Confirm screen.

### 3.1. Referenced in the internal $\_POST variable <a id="3-1-post"></a>

* $\_POST\["${name}EncText"\]

### 3.2.Screen <a id="3-2"></a>

> ![](../../../.gitbook/assets/xnpGetTextFileConfirmBlock%20%282%29.gif)

### 3.3. Submit Data <a id="3-3"></a>

* $\_POST\["${name}EncText"\]

### 3.4. Input <a id="3-4"></a>

* maxlen: The size of the column DB

## 4. array xnpGetTextFileRegisterBlock\( string name \) <a id="4-array-xnpgettextfileregisterblock-string-name"></a>

→ same as section 2: array xnpGetTextFileEditBlock\( int item\_id, string name, string text \)

## 5. string xnpGetTextFile\( string name \) <a id="5-string-xnpgettextfile-string-name"></a>

Which is a function of the order to get the page in $\_POST \["${name} EncText"\] that is loaded in the Submit of the Confirm screen. Each item type module saves the string obtained in this function to the DB.

### 5.1. Referenced in the internal $\_POST variable <a id="5-1-post"></a>

* $\_POST\["${name}EncText"\]

### 5.2. 戻り値 <a id="5-2"></a>

array \('value' =&gt; html for the confirmation screen display input string, 'within' =&gt; what was cut out head $maxlen bytes from the input string, 'without' =&gt; remaining cut out, 'html\_string '=&gt; html of the input string\).

