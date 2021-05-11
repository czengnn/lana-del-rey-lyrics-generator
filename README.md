# Motivation
I wanted to explore using the LSTM RNN, one of the application it has is to generate new text based on existing text.  
I chose to generate lyrics as if they were from a Lana Del Rey song, because she is the only artist I listen to who produces music with lyrics, and I have listened to her for 10 years, so I'm very familiar with her lyrical style and would be able to tell if something is written in this style. 

# Data Source
I pulled latest 5 Lana Del Rey studio albums from Genius.com using the package lyricsgenius.  
There are 83 songs in total, the albums are: 
- Born to Die: The Paradise Edition
- Ultraviolence
- Honeymoon
- Lust for Life
- Norman F***ing Rockwell!

# Models
I built 2 versions of the text generator model, first model predicts character by character, the second model predicts word by word.  
In each model, a seed is required, it's a starting point that promts the model to start the prediction, it can be a randomly chosen word such as "beach" or 
"james dean".  

## Model 1: Character
example input: "I want to b"  
example target: "e"  

The model was trained to use 100 characters to predict the 101th character. 


## Model 2: Word
example input: "I want to dance all"  
example target: "night"

The model was trained to use various lengths of sentences (lyrical paragraph broken up by line break) to predict the next word.
The predictions from this model does not include line break, so I manually broke the lyrics into lines for easier interpretation.  
### Example 1 of Lyrics Generator:
#### seed = "lolita"  
lolita hey design  
single to me to me anyway  
down in the garden of evil beauty queen of the hollywood sign  
yeah i also call home  
~~when i'm not as rock them all work with~~  
to leave my head  
get crazy in the pale rocky  
what what what what what  
all newer  
~~can you are~~  
who get with you 'round here lately  
get with you on these beaches  
got a party  
we'll dance 'til dawn  
put you higher and higher  
and over there out of time  

Interpretation from a Lana Fan (me):  
I have looked it up to make sure "evil beauty queen of the hollywood sign" is not an actual phrase from any Lana songs, and it makes sense this is something Lana would say. This generator lyrics seems to be talking about Lana wanting to be free by the hollywood sign where she calls home, she asks who has been getting with you around the beaches here lately, do you have a party? And she wants to dance 'til dawn.

### Example 2 of Lyrics Generator:
#### seed = "baby blue"  

baby blue yeah you do  
it's hard to leave  
blue and forever 
seeing pants on the floor of your new car 
baby oh i'm la than i left 
making me crazy 
but we're glance 
baby i don't know what you do 
it's unbelievable 
love you 
gathered me the fame and the fortune and the legend 
a stairway stairway to heaven 
it to lie like her rival 
in my car got a bad desire 
on the ipad side of the american dream 
down and now low down 
and maybe think that you try to take to start your life over 

