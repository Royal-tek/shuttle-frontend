    <template>
    <div id="holder">
        <nav class="navbar navbar-expand-lg bg-light py-3">
    <div class="container-fluid" id="navHolder">
        <a class="navbar-brand text-white" href="/" style="font-weight:bold; color:pink;"><b>SHUTTLE</b></a>
        <button class="navbar-toggler bg-white" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavDropdown">
        <ul class="navbar-nav ms-auto">
            <li class="nav-item">
            <a class="nav-link text-white" href="/">Home</a>
            </li>
            <li class="nav-item">
            <a class="nav-link text-white" href="/booking">BookNow</a>
            </li>
            <li class="nav-item me-2">
            <a class="nav-link text-white" href="/driver-admin">Admin</a>
            </li>

        

            <li class="nav-item dropdown">
            
            <a class="nav-link dropdown-toggle text-white" href="#" id="navbarDropdownMenuLink" role="button" data-bs-toggle="dropdown" aria-expanded="false">
            <a class="imgg me-1" style="display:inline-block"></a>
            </a>
            <ul class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
                <li><a class="dropdown-item" style="font-weight:bold;" href="/profile">Profile</a></li>
                <li><a class="dropdown-item" style="font-weight:bold;" href="/settings">Settings</a></li>
                <li><a class="dropdown-item" style="font-weight:bold;" href="/login">Login</a></li>
            </ul>
            </li>

        </ul>
        </div>
    </div>
    </nav>
    </div>
    </template>

    <script>
    export default {
        name : 'Navbar',
    }
    </script>

    <style lang="scss" scoped>
    #navHolder{
        width: 75%;
    }
    .navbar{
        background-color: rgb(82, 176, 104) !important;
    
    }
    .user{
        border-radius: 100%;
        width: 10px;
        height: 10px;
        background-color: red;
    }
    .imgg{
        width: 20px;
        height: 20px;
        border-radius: 100%;
        border: 2px solid white;
        // background: url(../assets/logo.png);
        background-color: rgb(0, 0, 0);
        
    }
    </style>