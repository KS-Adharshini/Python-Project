<?php
$logged=0;
$invalid=0;
if($_SERVER['REQUEST_METHOD']=='POST')
{
    require 'php3.php';
    $name=$_POST['uname'];//form input tag
    $password=$_POST['pswd'];
    $sql="SELECT * FROM usersdetails WHERE username='$name' AND password='$password'";
    $result=mysqli_query($con,$sql);
    
  if($result)
  {$num=mysqli_num_rows($result);
            if($num>0)
            {
            $logged=1;  //echo '<center><p style="color: green;">account verified</p></center>';
            session_start();
            $_SESSION['username']=$name;
            header('location: newindex.php');
            }
            else
            {
              $invalid=1;
            }
  }
  }
?>

 <!DOCTYPE html>
  <html lang="en">

  <head>
      <meta charset="UTF-8" />
      <meta name="viewport" 
            content="width=device-width, 
                     initial-scale=1,
                     shrink-to-fit=no" />
      <link rel="stylesheet" 
            href=
  "https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" />
    <link rel="stylesheet" href="stylelogin.css">
    <script>
    function formValidation(){
        let x=document.forms["form1"]["username"].value;
        if (x==''){
            alert("username must be filled out");
            return false;
        }
    }
    function newFunction(){
        document.getElementById("form1").reset();
    }
  </script>
  </head>

  <body>
  <?php
  if($logged)
  {
    echo'<div class="alert alert-success">
    <strong>Success!</strong><p>login successfully.</p></div>';
  }
  ?>
<?php
  if($invalid)
  {
    echo'<div class="alert alert-danger">
    <strong>Error!</strong><p>Invalid username.</p></div>';
  }
  ?>
      <nav class="navbar navbar-expand-sm ">
        <div class="container-fluid">
          <a class="navbar-brand" href="#"><img src="logo.png" style="width: 40px; height: 40px; border-radius: 25%; margin: 1;"></a>
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#collapsibleNavbar">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="collapsibleNavbar">
            <ul class="navbar-nav navbar-custom">
              <li class="nav-item">
                <a class="nav-link" href="index.php">HOME</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="login.php">LOG IN</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="sign.php">SIGN UP</a>
              </li>  
              <li class="nav-item dropdown">
                <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown">REPORT</a>
                <ul class="dropdown-menu">
                  <li><a class="dropdown-item" href="#">MALFUNCTION</a></li>
                  <li><a class="dropdown-item" href="#">FEEDBACK</a></li>
                </ul>
              </li>
            </ul>
          </div>
        </div>
      </nav>
      <div class="container mt-3">
        <h1>LOG-IN</h1>
        

        <form action="login.php" method="post" id="form1" name="form1" onSubmit="return formValidation()">
          <div class="mb-3 mt-3">
            <label for="uname" class="form-label">Username:</label>
            <input type="text" class="form-control" id="uname" placeholder="Enter username" name="uname" required>
            <div class="valid-feedback">Valid.</div>
            <div class="invalid-feedback">Please fill out this field.</div>
          </div>
          <div class="mb-3">
            <label for="pwd" class="form-label">Password:</label>
            <input type="password" class="form-control" id="pwd" placeholder="Enter password" name="pswd" required>
            <div class="valid-feedback">Valid.</div>
            <div class="invalid-feedback">Please fill out this field.</div>
          </div>
        
        <button type="submit" class="btn btn-primary">LOGIN</button>
        </form>
      </div>
  </body>

  </html>
