#ajax异步上传文件

var formData = new FormData();
$.each(self.files, function(idx, file) {
formData.append(idx, file);
})
formData.append(‘_csrf’, $(‘#csrf’).data(‘csrf’));
$.ajax({
url: url,
type: ‘POST’,
data: formData,
cache: false,
processData: false, // Don't process the files
            contentType: false, // or jquery will never send the file
            success: function(data){
});


see also:
http://stackoverflow.com/questions/2320069/jquery-ajax-file-upload#

https://developer.mozilla.org/en-US/docs/Web/API/FormData
