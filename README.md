

<?php 
$conn = mysql_connect('lhosthost','root','root') or die ('bed');
mysql_query("SET NAMES utf-8");
mysql_select_db('sqltest',$conn) OR emMsg("BED");
$id = isset($_GET['id']) ? $_GET['id'] :1;
$sql = "SELECT * FROM news WHERE ID = {'id'}";
$result = mysql_query($sql,$conn) or die(musql_error());
?>

<!DOCTYPE html>
<html>
<head>
    <meta charset= "utf-8" />
    <title>SQL注入</title>
</head>
</html>
<body>
<?php
$row = mysql_fetch_array($result,MYSQLI_ASSOC);
echo "SQL语句 ： SELECT * FROM news WHERE id =<font colour='red>{$id}</font>";
echo "<hr>";
echo "<center><table bordern= '2'><tr><td>标题</td><td>内容</td></tr><tr><td>{$row['title']}</tr><td>{$row['contect']}</td></tr></table></center>";
mysql_free_result($result);
?>
</body>
</html>
