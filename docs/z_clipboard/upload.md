<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Upload to DigitalOcean Spaces</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .upload-container {
            max-width: 400px;
            margin: 0 auto;
            text-align: center;
        }
        input[type="file"] {
            margin: 10px 0;
        }
        .progress-bar {
            width: 100%;
            background: #f3f3f3;
            border: 1px solid #ccc;
            height: 20px;
            margin-top: 10px;
            position: relative;
        }
        .progress-bar div {
            background: #4caf50;
            width: 0;
            height: 100%;
            text-align: center;
            color: white;
            line-height: 20px;
        }
    </style>

    <title>Scoped Roboto Mono Font</title>
  <link href="https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@400;700&display=swap" rel="stylesheet">

</head>
<body>
    <div class="upload-container">
    <p>This is normal text.</p>
    <p><span style="font-family: 'Roboto Mono', monospace;">This is text in Roboto Mono.</span></p>

        <h1>Upload a File</h1>
        <input type="file" id="fileInput">
        <button id="uploadButton">Upload</button>
        <div class="progress-bar">
            <div id="progress" style="width: 0%;">0%</div>
        </div>
        <p id="status"></p>
    </div>

    <script>
        document.getElementById('uploadButton').addEventListener('click', async () => {
            const fileInput = document.getElementById('fileInput');
            const status = document.getElementById('status');
            const progress = document.getElementById('progress');

            if (!fileInput.files.length) {
                status.textContent = 'Please select a file.';
                return;
            }

            const file = fileInput.files[0];
            status.textContent = 'Uploading...';

            try {
                // Step 1: Get a pre-signed URL from the backend
                const response = await fetch('https://your-backend-server.com/generate-presigned-url', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify({ fileName: file.name, fileType: file.type }),
                });

                if (!response.ok) {
                    throw new Error('Failed to get pre-signed URL.');
                }

                const { url } = await response.json();

                // Step 2: Upload file to DigitalOcean Space
                const uploadResponse = await fetch(url, {
                    method: 'PUT',
                    body: file,
                    headers: {
                        'Content-Type': file.type,
                    },
                });

                if (uploadResponse.ok) {
                    status.textContent = 'File uploaded successfully!';
                } else {
                    throw new Error('Upload failed.');
                }
            } catch (error) {
                status.textContent = `Error: ${error.message}`;
            }
        });
    </script>
</body>
</html>
