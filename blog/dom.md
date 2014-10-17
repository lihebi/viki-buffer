#DOM Element VS jQuery Element

有时候，需要一个dom element而不是jquery element。

从jquery转成dom
1.
$(‘#foo’)[0]
2.
$(‘#foo’).get(0)
3.
$(‘#foo’).get() ==> retrieve a true array of DOM elements.


实际例子：
 <div id="editor" contenteditable="true"></div>
定位到文件末尾


function setCursorToEnd(ele)
{
  var range = document.createRange();
  var sel = window.getSelection();
  console.log(range);
  range.setStart(ele, 1);
  range.collapse(true);
  sel.removeAllRanges();
  sel.addRange(range);
  ele.focus();
}

function setEndOfContenteditable(contentEditableElement)
{
  var range,selection;
  if(document.createRange)//Firefox, Chrome, Opera, Safari, IE 9+
  {
    range = document.createRange();//Create a range (a range is a like the selection but invisible)
    range.selectNodeContents(contentEditableElement);//Select the entire contents of the element with the range
    range.collapse(false);//collapse the range to the end point. false means collapse to end rather than the start
    selection = window.getSelection();//get the selection object (allows you to change selection)
    selection.removeAllRanges();//remove any selections already made
    selection.addRange(range);//make the range you have just created the visible selection
  }
  else if(document.selection)//IE 8 and lower
  {
    range = document.body.createTextRange();//Create a range (a range is a like the selection but invisible)
    range.moveToElementText(contentEditableElement);//Select the entire contents of the element with the range
    range.collapse(false);//collapse the range to the end point. false means collapse to end rather than the start
    range.select();//Select the range (make it the visible selection
    }
  }


$('#editor').focus();
elem = document.getElementById('editor’);
这时候用下面两个都行
setEndOfContenteditable($('#editor')[0]);
setCursorToEnd(elem);
但是括号中的元素只能是：
$(‘#editor’)[0]
$(‘#editor’).get(0)
elem
不能是
$(‘#editor’)
否则报错为：
Uncaught NotFoundError: Failed to execute 'selectNodeContents' on 'Range': The node provided is null.
