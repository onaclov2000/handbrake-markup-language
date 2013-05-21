handbrake-markup-language
=========================

This *should* be a document describing how to write up an HML file (handbrake-makup-language).


Format
=========================
An HML file is a file (of JSON Object format) containing information about a particular DVD you are ripping, if it's a Series, then the format will look like this:

     T.V. Series
    {
       Title Handbrake Finds : "Some name",
       Disc Title : "Name of Series",
       Type       : Series,
       Season     : "NN"
       Titles     : 
                    {
                     X : { 
                           Displayed Title : "Name_Of_Episode", 
                           Episode Number : "NN"
                          }
                    }
    }


     Movies
    {
        Title Handbrake Finds : "Some name",
        Disc Title : "Name of Movie"
        Type       : Movie
        Titles     : {
                       X : {
                             Displayed Title : "Name of Output",
                           }
                    }
     }

High Level
=========================
When we store data in a MongoDB (which is my ultimate plan), it'll contain the above formats.


So the idea is that we can take a disk title that handbrake finds, do a lookup in our DB and return a list of Valid Titles.
This means that DVD's that have 99 titles will know which titles are what (if they've been discovered before).

This *should* work well using Handbrake CLI.
