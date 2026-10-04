# Laboratory Activity: Laravel Multi-Page Migration

**Student Name:** Karl Wayne M. Padullon  
**Course & Section:** ITMWD5M2 WebDev 3 Lab
**Sir:** Amstrong Luiese landeza

---

## 🎥 Video Demonstration
* 🔗 [Panoorin ang Video Demo sa Loom](https://www.loom.com/share/b3d46c177060490a8ecb9cc40d3ffab8)

---

**Screenshot of Code & File Location**
<img width="1920" height="1080" alt="Screenshot (84)" src="https://github.com/user-attachments/assets/48193443-6045-429b-b28e-d9e49e1ed370" />





## 💻 Code Snippets Compilation

**Home.blade.php** 

@extends('layouts.app') 

 

@section('title', 'Home Page') 

 

@section('content') 

    <h1>Welcome to Our Homepage</h1> 

    <p>This page was successfully migrated from native PHP to Laravel Blade templates!</p> 

    <p>Explore our navigation bar above to view other pages seamlessly without duplicating HTML structure.</p> 

@endsection 

 

**About.blade.php** 

@extends('layouts.app') 

 

@section('title', 'About Us') 

 

@section('content') 

    <h1>About Our System</h1> 

    <p>Learn more about our institutional mission, course objectives, and student web development projects.</p> 

@endsection 

 

**Contact.blade.php** 

@extends('layouts.app') 

 

@section('title', 'Contact Us') 

 

@section('content') 

    <h1>Get in Touch</h1> 

    <p>Reach out to our team via email or visit our university laboratory workstation.</p> 

@endsection 

 

 

**App.blade.php** 

<!DOCTYPE html> 

<html lang="en"> 

<head> 

    <meta charset="UTF-8"> 

    <title>@yield('title', 'My Laravel App')</title> 

    <!-- Linking CSS using Laravel asset helper --> 

    <link rel="stylesheet" href="{{ asset('css/style.css') }}"> 

</head> 

<body> 

    <!-- Shared Navigation Bar --> 

    <nav style="background: #f4f4f4; padding: 10px; margin-bottom: 20px;"> 

        <a href="/">Home</a> |  

        <a href="/about">About Us</a> |  

        <!-- <a href="/services">Services</a> | --> 

        <a href="/contact">Contact</a> 

    </nav> 

    <hr> 

    <!-- Dynamic Page Content Injection Point --> 

    <div class="container"> 

        @yield('content') 

    </div> 

    <hr> 

    <!-- Shared Footer --> 

    <footer> 

        <p>&copy; 2026 Web Development 3 Class. All rights reserved.</p> 

    </footer> 

</body> 

</html> 

 

**Web.php** 

<?php 

 

use Illuminate\Support\Facades\Route; 

 

/* 

|-------------------------------------------------------------------------- 

| Multi-Page Migration Routes 

|-------------------------------------------------------------------------- 

*/ 

 

// Home Route 

Route::get('/', function () { 

    return view('home'); 

}); 

 

// About Route 

Route::get('/about', function () { 

    return view('about'); 

}); 

 

// Services Route 

Route::get('/services', function () { 

    return view('services'); 

}); 

 

// Contact Route 

Route::get('/contact', function () { 

    return view('contact'); 

}); 

 
