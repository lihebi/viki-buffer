#jsonp


A
<script type="text/javascript">
 //回调函数
 function callback(data) {
     alert(data.message);
 }
 </script>
 <script type="text/javascript" src="http://localhost:20002/test.js"></script>

B
callback({message:"success"}); 
