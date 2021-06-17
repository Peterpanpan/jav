<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>biaoti</title>
</head>
 
<body>
<script   type="text/javascript">   
function setCaret(textObj) {
    if (textObj.createTextRange) {
        textObj.caretPos = document.selection.createRange().duplicate();
    }
}
function insertAtCaret(textObj, textFeildValue) {
    if (document.all) {
        if (textObj.createTextRange && textObj.caretPos) {
            var caretPos = textObj.caretPos;
            caretPos.text = caretPos.text.charAt(caretPos.text.length - 1) == '   ' ? textFeildValue + '   ' : textFeildValue;
        } else {
            textObj.value = textFeildValue;
        }
    } else {
        if (textObj.setSelectionRange) {
            var rangeStart = textObj.selectionStart;
            var rangeEnd = textObj.selectionEnd;
            var tempStr1 = textObj.value.substring(0, rangeStart);
            var tempStr2 = textObj.value.substring(rangeEnd);
            textObj.value = tempStr1 + textFeildValue + tempStr2;
        } else {
            alert("This   version   of   Mozilla   based   browser   does   not   support   setSelectionRange");
        }
    }
}   
 </script>  
    
  <form   id="form1"   action=""   onsubmit=""   method="post"   enctype="text/plain">    
  <p>  
  <textarea   name="tarea"   rows=""   cols=""   style="width:300px;height:120px;" 
  onselect="setCaret(this);" 
  onclick="setCaret(this);" 
  onkeyup="setCaret(this);"   >lizilizilizi</textarea>  
  <br/><br/>  
  <input   type="text"   name="textfield"   style="width:100px;"   value="$payment_id"/>  
  <br/>  
  <input   type="button"   value="$payment_id" style="width:100px;" name="paymentId"
  onclick="insertAtCaret(this.form.tarea,this.form.paymentId.value);"/>
  <input   type="button"   value="$service_id" style="width:100px;" name="service_id"
  onclick="insertAtCaret(this.form.tarea,this.form.service_id.value);"/>   
  </p>  
  </form>   
<div id="box" contenteditable="true" style="border:1px solid #ccc; width:300px; height:200px;">sljfldjfldf</div>
 
</body>
</html>
