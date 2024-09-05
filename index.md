---
layout: base
title: Student Home 
description: Home Page
hide: true
---

My journey starts here. - Kicking projects 2.0
<style>
    // Style looks pretty compact, but it has a repeat 4, what if we wanted it dynamic
</style>

<!-- This is orignal grid_container class, but now we are adding an id for JavaScript -->
<div class "grid_container" id="grid_container">
    <!-- We are hoping to make the insides with a JavaScript object -->
</div>

<script>
    // 1. Make a connection to the HTML container
    var container = document.getElementById("grid_container");

    // 2. Define a Javascript object for our data
    var living_in_the_world = {
        {"flag": "Flag_of_California", "time_lived": "Forever", "greeting": "Hey"},
        {"flag": "Flag_of_Oregon", "time_lived": "9-years", "greeting": "Hello"},
        {"flag": "Flag_of_England", "time_lived": "2-years", "greeting": "Alright mate"},
        {"flag": "Flag_of_Oregon", "time_lived": "2-years", "greeting": "Aloha"},
    }; 
    
    // 3a. Consider how to update style count for size of container
    // 3b. Build a grid items inside of our container for each row of data
    for (var row of living_in_the_world) {
        // make a "div" with "class grid_item "div" for each row
        // add "img" tag and "p" tags for data
    }
</script>
