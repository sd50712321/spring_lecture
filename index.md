<style>
body {
  font-family: Arial, sans-serif;
  max-width: 800px;
  margin: 0 auto;
}

#table-of-contents {
  float: left;
  width: 20%;
  padding: 20px;
  background-color: lightgray;
}

#table-of-contents h2 {
  text-align: center;
}

#content {
  float: right;
  width: 78%;
  padding: 20px;
  background-color: white;
}

#table-of-contents a {
  display: block;
  margin-bottom: 20px;
  text-decoration: none;
  color: black;
}

#table-of-contents a:hover {
  background-color: gray;
}

h1, h2, h3 {
  text-align: center;
}
</style>

<html>
<head>
  <script>
    function showChapter(chapter) {
      var chapters = ['chapter1', 'chapter2'];
      for (var i = 0; i < chapters.length; i++) {
        document.getElementById(chapters[i]).style.display = 'none';
      }
      document.getElementById(chapter).style.display = 'block';
    }
  </script>
</head>
<body>
  <h1>My Book</h1>
  <div id="chapters">
    <a href="#" onclick="showChapter('chapter1');">Chapter 1</a>
    <a href="#" onclick="showChapter('chapter2');">Chapter 2</a>
  </div>
  <div id="chapter1" style="display:block;">
    <h2>Chapter 1</h2>
    [Chapter 1](./chapter1.md)
  </div>
  <div id="chapter2" style="display:none;">
    <h2>Chapter 2</h2>
    [Chapter 2](./chapter2.md)
  </div>
</body>
</html>
