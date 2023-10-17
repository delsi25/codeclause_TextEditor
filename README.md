# codeclause_TextEditor
<!DOCTYPE html>
<html>
<head>
    <title>Text Editor</title>
    <style>
        #editor {
            width: 100%;
            height: 300px;
        }
    </style>
</head>
<body>
    <div>
        <button onclick="changeFontSize('12px')">Font Size 12px</button>
        <button onclick="changeFontSize('16px')">Font Size 16px</button>
        <button onclick="changeFontSize('20px')">Font Size 20px</button>
        <button onclick="toggleStyle('bold')">Bold</button>
        <button onclick="toggleStyle('italic')">Italic</button>
        <button onclick="toggleStyle('underline')">Underline</button>
        <button onclick="setTextAlignment('left')">Left Align</button>
        <button onclick="setTextAlignment('center')">Center Align</button>
        <button onclick="setTextAlignment('right')">Right Align</button>
        <input type="color" id="colorPicker" onchange="changeTextColor()">
    </div>
    <div id="editor" contenteditable="true">
        Start typing here...
    </div>

    <script>
        function changeFontSize(fontSize) {
            document.execCommand('fontSize', false, fontSize);
        }

        function toggleStyle(style) {
            document.execCommand(style, false, null);
        }

        function setTextAlignment(align) {
            document.execCommand('justify' + align, false, null);
        }

        function changeTextColor() {
            var color = document.getElementById('colorPicker').value;
            document.execCommand('foreColor', false, color);
        }
    </script>
</body>
</html>
