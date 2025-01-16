<?php
$registered=0;
$userexists=0;
if($_SERVER['REQUEST_METHOD']=='POST')
{
    include 'php3.php';
    $name=$_POST['name'];
    $password=$_POST['password'];
    $conpassword=$_POST['conpassword'];
    $email=$_POST['email'];
    if($password != $conpassword)
    {
        echo "password does not match";
    
    }
    else{
    $sql= "SELECT * FROM usersdetails WHERE username='$name'";
    $result=mysqli_query($con,$sql);
    if($result)
    {
        $num=mysqli_num_rows($result);
        if($num>0)
           {
            $userexists=1;
           }
        else
          {
            $sql="INSERT INTO usersdetails (username,email,password) VALUES('$name','$email','$password')";
            $result=mysqli_query($con,$sql);
            if($result)
               {
                $registered=1;
               }
            else
               {
                die(mysqli_error($con));
               }
          }
    }
}
}
?>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="stylesign.css">
    <script>
        function formValidation()
        {
            let x =document.forms['form2']['name'].value;
            if(x== "")
            {
                alert("name must be filled out");
                return false;
            }
        }
        function newFunction()
        {
            document,getElementById("form2").reset();
        }
    </script>
</head>
<body>
<?php
if($userexists)
{
    echo '<b>User Already Exist</b>';
}
if($registered)
{
    echo '<b>Registered Successfully</b>';
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
    <div class="container signup-container">
        <div class="signup-form">
            <h1 class="text-center">EZ TRANSLATOR</h1>
            <form action="sign.php" method="post" id="form2" name="form2" onSubmit="return formValidation()">
                <div class="form-group">
                    <label for="username">Username</label>
                    <input type="text" class="form-control" id="username" name="name" placeholder="Username">
                </div>
                <div class="form-group">
                    <label for="email">Email Address</label>
                    <input type="email" class="form-control" id="email" name="email" placeholder="Email Address">
                </div>
                <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" class="form-control" id="password" name="password" placeholder="Password">
                </div>
                <div class="form-group">
                    <label for="confirmPassword">Confirm Password</label>
                    <input type="password" class="form-control" id="confirmPassword" name="conpassword" placeholder="Confirm Password">
                </div>
                <div class="form-group form-check">
                    <input type="checkbox" class="form-check-input" id="terms">
                    <label class="form-check-label" for="terms">I accept the <a href="#">Terms of Use & Privacy Policy</a></label>
                </div>
                <button type="submit" class="btn btn-primary btn-block">Sign Up</button>
                <div class="login-link">
                    Already have an account? <a href="login.php">Login here</a>
                </div>
            </form>
        </div>
    </div>

    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.5.4/dist/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
</body>
</html>
