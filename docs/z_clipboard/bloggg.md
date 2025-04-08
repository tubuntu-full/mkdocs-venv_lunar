<!-- ***************************************** -->

<!-- begin wwww.htmlcommentbox.com -->
 <div id="HCB_comment_box"><a href="http://www.htmlcommentbox.com">HTML </a> is loading comments...</div>
 <link rel="stylesheet" type="text/css" href="https://www.htmlcommentbox.com/static/skins/bootstrap/twitter-bootstrap.css?v=0" />
 <script type="text/javascript" id="hcb"> /*<!--*/ if(!window.hcb_user){hcb_user={};} (function(){var s=document.createElement("script"), l=hcb_user.PAGE || (""+window.location).replace(/'/g,"%27"), h="https://www.htmlcommentbox.com";s.setAttribute("type","text/javascript");s.setAttribute("src", h+"/jread?page="+encodeURIComponent(l).replace("+","%2B")+"&opts=16798&num=10&ts=1731652241287");if (typeof s!="undefined") document.getElementsByTagName("head")[0].appendChild(s);})(); /*-->*/ </script>
<!-- end www.htmlcommentbox.com -->

<!-- ***************************************** -->

<br>
---

# Uploads

<!-- #raw -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>File Upload</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
      text-align: center;
    }
    .file-upload {
      margin: 20px 0;
    }
    .preview {
      margin-top: 20px;
      padding: 10px;
      border: 1px solid #ddd;
      border-radius: 5px;
    }
  </style>
</head>
<body>
  <h1>File Upload Example</h1>
  <p>Select a file to upload and preview its name below:</p>

  <div class="file-upload">
    <input type="file" id="fileInput">
    <p id="fileName">No file selected</p>
  </div>

  <div class="preview" id="filePreview">
    <p>No file uploaded yet.</p>
  </div>

  <script>
    const fileInput = document.getElementById('fileInput');
    const fileName = document.getElementById('fileName');
    const filePreview = document.getElementById('filePreview');

    fileInput.addEventListener('change', () => {
      const file = fileInput.files[0];

      if (file) {
        fileName.textContent = `Selected file: ${file.name}`;

        // Optional: If the file is an image, preview it
        if (file.type.startsWith('image/')) {
          const reader = new FileReader();
          reader.onload = function (e) {
            filePreview.innerHTML = `<img src="${e.target.result}" alt="Preview" style="max-width: 100%; height: auto;">`;
          };
          reader.readAsDataURL(file);
        } else {
          filePreview.innerHTML = `<p>Preview is not available for this file type.</p>`;
        }
      } else {
        fileName.textContent = 'No file selected';
        filePreview.innerHTML = '<p>No file uploaded yet.</p>';
      }
    });
  </script>
</body>
</html>

<!-- #endraw -->
<br>
---

<!-- ***************************************** -->
