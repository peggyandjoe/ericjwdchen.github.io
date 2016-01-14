---
layout: page
title: Title Case
weight: 1
---



<form action="http://brettterpstra.com/titlecase/" id="titleCase-form">
  <input id="titleCase-input" class="textinput" name="title" type="text">
  <input id="titleCase-button" type="submit" value="Tt" class="clearbutton">
</form>

<header>
   <h1>Front Row</h1>
</header>
<section id="fetch">
   <input type="text" placeholder="Enter a movie title" id="term" />
   <button id="search">Find me a poster</button>
</section>
<section id="poster">
</section>


$(document).ready(function(){

   $('#term').focus(function(){
      var full = $("#poster").has("img").length ? true : false;
      if(full == false){
         $('#poster').empty();
      }
   });

   var getPoster = function(){

        var film = $('#term').val();

         if(film == ''){

            $('#poster').html("<h2 class='loading'>Ha! We haven't forgotten to validate the form! Please enter something.</h2>");

         } else {

            $('#poster').html("<h2 class='loading'>Your poster is on its way!</h2>");

            $.getJSON("http://api.themoviedb.org/2.1/Movie.search/en/json/
23afca60ebf72f8d88cdcae2c4f31866/" + film + "?callback=?", function(json) {
               if (json != "Nothing found."){
                     $('#poster').html('<h2 class="loading">Well, gee whiz! We found you a poster, skip!</h2><img id="thePoster" src=' + json[0].posters[0].image.url + ' />');
                  } else {
                     $.getJSON("http://api.themoviedb.org/2.1/Movie.search/en/json/
23afca60ebf72f8d88cdcae2c4f31866/goonies?callback=?", function(json) {
                        console.log(json);
                        $('#poster').html('<h2 class="loading">We're afraid nothing was found for that search. Perhaps you were looking for The Goonies?</h2><img id="thePoster" src=' + json[0].posters[0].image.url + ' />');
                     });
                  }
             });

          }

        return false;
   }

   $('#search').click(getPoster);
   $('#term').keyup(function(event){
       if(event.keyCode == 13){
           getPoster();
       }
   });

});
