# taleghani11
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>page login</title>
	<style>
body {
     background-color:aqua;
}
	</style>
</head>
<body>
	<center>
    <form action="" method="post">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required><br>
<br>
        <label for="lastName">Last Name:</label>
        <input type="text" id="lastName" name="lastName" required><br>
<br>
        <label for="code meli">code meli:</label>
        <input type="text" id="codemeli" name="codemeli" required><br>
		<br>
        <input type="submit" value="کلیک کنید">
    </form>
		</center>

    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        $name = $_POST["name"];
        $lastName = $_POST["lastName"];
        $codemeli = $_POST["codemeli"];

        $link = mysqli_connect("localhost", "root", "", "page login");

        if (mysqli_connect_errno()) {
            exit("مشکلی به وجود امده:" . mysqli_connect_error());
        }

        $query = "INSERT INTO page login (name,lastname,codemeli) VALUES 
        ('$name','$lastName','$codemeli')";

        mysqli_query($link,$query);

        mysqli_close($link);
    }
    ?>
</body>
</html>
