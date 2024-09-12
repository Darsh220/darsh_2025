---
layout: page
title: About
permalink: /about/
---

# Im Darsh and Im 17 years old



I have lived in these places my whole life 

Flags Source - Wikipedia Images

<style>
    /* Style looks pretty compact, trace grid-container and grid-item in the code */
    .grid-container {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); /* Dynamic columns */
        gap: 10px;
    }
    .grid-item {
        text-align: center;
    }
    .grid-item img {
        width: 100%;
        height: 100px; /* Fixed height for uniformity */
        object-fit: contain; /* Ensure the image fits within the fixed height */
    }
    .grid-item p {
        margin: 5px 0; /* Add some margin for spacing */
    }
</style>

<!-- This grid_container class is for the CSS styling, the id is for JavaScript connection -->
<div class="grid-container" id="grid_container">
    <!-- content will be added here by JavaScript -->
</div>

<script>
    // 1. Make a connection to the HTML container defined in the HTML div
    var container = document.getElementById("grid_container"); // This container connects to the HTML div

    // 2. Define a JavaScript object for our http source and our data rows for the Living in the World grid
    var http_source = "https://upload.wikimedia.org/wikipedia/commons/";
    var living_in_the_world = [
        {"flag": "4/41/Flag_of_India.svg", "greeting": "Namaste", "description": "I have lived here for 7 months"},
        {"flag": "4/48/Flag_of_Singapore.svg", "greeting": "Ni Hao", "description": "I have lived here for my whole life pretty much"},
        {"flag": "0/01/Flag_of_California.svg", "greeting": "Hey", "description": "I have lived here for about one and a half years now"},


      
    ]; 
    
    // 3a. Consider how to update style count for size of container
    // The grid-template-columns has been defined as dynamic with auto-fill and minmax

    // 3b. Build grid items inside of our container for each row of data
    for (const location of living_in_the_world) {
        // Create a "div" with "class grid-item" for each row
        var gridItem = document.createElement("div");
        gridItem.className = "grid-item";  // This class name connects the gridItem to the CSS style elements
        // Add "img" HTML tag for the flag
        var img = document.createElement("img");
        img.src = http_source + location.flag; // concatenate the source and flag
        img.alt = location.flag + " Flag"; // add alt text for accessibility

        // Add "p" HTML tag for the description
        var description = document.createElement("p");
        description.textContent = location.description; // extract the description

        // Add "p" HTML tag for the greeting
        var greeting = document.createElement("p");
        greeting.textContent = location.greeting;  // extract the greeting

        // Append img and p HTML tags to the grid item DIV
        gridItem.appendChild(img);
        gridItem.appendChild(description);
        gridItem.appendChild(greeting);

        // Append the grid item DIV to the container DIV
        container.appendChild(gridItem);
    }
</script>

My life so far
Here are all the things that I have done before coming here and what I did in those places. 

India
 - I have lived here for around 7 months and I started the foundation of my education here
 - I developed my love for Badminton and Soccer and learnt the necessary skills needed to support my learning in school. 


Singapore
 - I have lived here for the majority of my life and have grown up with many different and cool people. 
 - I have also developed my badminton skills and have grown to a significant level and most of my school education was also done here and it is my favorite place to visit right after Europe
 - The food in singapore is TOP TIER!!! and is very very popular and this was also the best part of my life in singapore. 

 
 California
 - I have just recently moved to here and I love the weather as it is sunny and pleasant almost all year round. 
 - I really like the people I met and enjoy the vast amount of opportunities here.
 - I also became an advanced level badminton player and was able to culminate my skills here. 



<style>
div.gallery {
  margin: 5px;
  border: 1px solid #ccc;
  float: left;
  width: 180px;
}

div.gallery:hover {
  border: 1px solid #777;
}

div.gallery img {
  width: 100%;
  height: auto;
}

div.desc {
  padding: 15px;
  text-align: center;
}
</style>



<div class="gallery">
  <a target="_blank" href="https://www.thoughtco.com/thmb/C1Nbj1M6jZK9Xm_lgD1ndDPPAk4=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/singapore--garden-by-the-bay--supertree-grove-638256268-fa59e7e78b6449aaa40f68eafe6ff1a1.jpg">
    <img src="https://www.thoughtco.com/thmb/C1Nbj1M6jZK9Xm_lgD1ndDPPAk4=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/singapore--garden-by-the-bay--supertree-grove-638256268-fa59e7e78b6449aaa40f68eafe6ff1a1.jpg" alt="Singapore" width="600" height="400">
  </a>
  <div class="desc">Singapore is the best</div>
</div>

<div class="gallery">
  <a target="_blank" href="https://i.natgeofe.com/k/42e832f5-fd48-43ff-b338-091bdf4048ca/india-tajmahal_16x9.jpg?w=1200">
    <img src="https://i.natgeofe.com/k/42e832f5-fd48-43ff-b338-091bdf4048ca/india-tajmahal_16x9.jpg?w=1200" alt="India" width="600" height="400">
  </a>
  <div class="desc">India is also cool</div>
</div>

<div class="gallery">
  <a target="_blank" href="https://ktla.com/wp-content/uploads/sites/4/2023/10/GettyImages-1247639634.jpg?w=2560&h=1440&crop=1">
    <img src="https://ktla.com/wp-content/uploads/sites/4/2023/10/GettyImages-1247639634.jpg?w=2560&h=1440&crop=1" alt="California" width="600" height="400">
  </a>
  <div class="desc">I love California</div>
</div>

<div class="gallery">
  <a target="_blank" href="https://lp-cms-production.imgix.net/features/2017/09/dubai-marina-skyline-2c8f1708f2a1.jpg?w=1440&h=810&fit=crop&auto=format&q=75.">
    <img src="https://lp-cms-production.imgix.net/features/2017/09/dubai-marina-skyline-2c8f1708f2a1.jpg?w=1440&h=810&fit=crop&auto=format&q=75" alt="Dubai" width="600" height="400">
  </a>
  <div class="desc">My dream place.</div>
</div>



