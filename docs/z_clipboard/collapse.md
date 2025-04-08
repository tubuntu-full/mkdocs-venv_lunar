<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Collapsible Text</title>
    <style>
        .collapsible {
            background-color: #f1f1f1;
            color: #333;
            cursor: pointer;
            padding: 10px;
            width: 100%;
            border: none;
            text-align: left;
            outline: none;
            font-size: 16px;
            margin-top: 10px;
        }

        .content {
            padding: 10px;
            display: none;
            overflow: hidden;
            background-color: #fafafa;
            border: 1px solid #ddd;
        }
    </style>
</head>
<body>

<h2>Collapsible Text Example</h2>

<button class="collapsible">Click to Expand</button>
<div class="content">
    <p>This is the content that was hidden. You can add more text or elements here!</p>
</div>

<script>
    const collapsibles = document.querySelectorAll('.collapsible');
    collapsibles.forEach(button => {
        button.addEventListener('click', function () {
            this.classList.toggle('active');
            const content = this.nextElementSibling;
            content.style.display = content.style.display === 'block' ? 'none' : 'block';
        });
    });
</script>

</body>
</html>
