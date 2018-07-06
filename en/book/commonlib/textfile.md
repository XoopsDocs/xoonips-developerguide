## Chapter 7 TextFile

Here we handle the PlainText. Mainly in the form that assumes a long input, you can read the contents of a text file in place of the key input. Key input is also possible.

($name for discussion see chapter 14. Supplement: Attachment, for $name argument of TextFile system function )

## 1\. array xnpGetTextFileDetailBlock( int item_id, string name, string text ) {#1-array-xnpgettextfiledetailblock-int-item-id-string-name-string-text}

### 1.1\. Referenced in the internal $_POST variable

None

### 1.2\.Screen {#1-2}

※ Add as Text ・Add as File become this display.

※ the text of the argument, is displayed in the，&lt;TEXTAREA&gt; … &lt;/TEXTAREA&gt;．

> ![](../../assets/commonlib/xnpGetTextFileDetailBlock.gif)

### 1.3\. Submit data {#1-3}

None

## 2\. array xnpGetTextFileEditBlock(int item_id, string name, string text ) {#2-array-xnpgettextfileeditblock-int-item-id-string-name-string-text}

※ Text を外から引数として与える必要があります．

### 2.1\. 内部で参照する $_POST 変数 {#2-1-post}

* $_POST[&quot;${name}EncText&quot;]

### 2.2\.Screen {#2-2}

Screen is the Readme input screen description.ppt 

> ![](../../assets/commonlib/xnpGetTextFileEditBlock1.gif)

When you press the Edit button, the following screen will open:

> ![](../../assets/commonlib/xnpGetTextFileEditBlock2.gif)

When you close the window by pressing the the OK button, the data of the TEXTAREA is transferred to the original form. The window closes without saving only if you press the Cancel button．

### 2.3\. Submit data {#2-3}

Upload button →

* $_FILES[&#039;text&#039;]

* $_POST[&#039;name&#039;]

Submit button → to the confirmation screen

* $_POST[&quot;${name}EncText&quot;]

## 3\. array xnpGetTextFileConfirmBlock( int item_id, string name, int maxlen=65535 ) {#3-array-xnpgettextfileconfirmblock-int-item-id-string-name-int-maxlen-65535}

To generate the HTML for the Confirm screen.

### 3.1\. Referenced in the internal $_POST variable {#3-1-post}

* $_POST[&quot;${name}EncText&quot;]

### 3.2\.Screen {#3-2}

> ![](../../assets/commonlib/xnpGetTextFileConfirmBlock.gif)

### 3.3\. Submit Data {#3-3}

* $_POST[&quot;${name}EncText&quot;]

### 3.4\. Input {#3-4}

* maxlen: The size of the column DB

## 4\. array xnpGetTextFileRegisterBlock( string name ) {#4-array-xnpgettextfileregisterblock-string-name}

→ same as section 2: array xnpGetTextFileEditBlock( int item_id, string name, string text ) 

## 5\. string xnpGetTextFile( string name ) {#5-string-xnpgettextfile-string-name}

Which is a function of the order to get the page in $_POST ["${name} EncText"] that is loaded in the Submit of the Confirm screen. Each item type module saves the string obtained in this function to the DB.

### 5.1\. Referenced in the internal $_POST variable {#5-1-post}

* $_POST[&quot;${name}EncText&quot;]

### 5.2\. 戻り値 {#5-2}

array ('value' => html for the confirmation screen display input string, 'within' => what was cut out head $maxlen bytes from the input string, 'without' => remaining cut out, 'html_string '=> html of the input string).
