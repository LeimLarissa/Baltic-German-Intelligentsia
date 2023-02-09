# Task 1: Clean errors generated through OCR to improve data quality 

## Background
All my sources are generated from scans of historic documents. 
They are all in German and printed between 1870 and 1925. 
As common for the time (and region) the type script used for the documents is "Fraktur". 
This type script can be difficult to read for contemporary German speakers, who are unfamiliar with historic documents, and needs to be considered if OCR is applied.  

The quality of OCR (Optical Character Recognition) heavily depends on the selected package and therefore on what data the applied pattern recognition modell has been trained. 
Luckily there has been quite some reseach on OCR for historic German documents and there are quite a few (historic) German language packages available.  

However, I have no insight into what package/model was applied by the University of Tartu on the scanned documents I'm working with. 
Judging from the quality of the source text it worked quite well in recognizing the correct letters for the German language sections. 
Other languages (Estonian, Latin, French) are not recognised as well and of course other alphabets such as kyrilic have not been transcribed at all (creative gibberish of punctuation and letters).  

The OCR problem I face within the documents is not with the transcription of the letters themselves, but additional spaces that were set between letters. 
This is hardly an issue for the human readability of the text, but it makes it harder to further computationally process the data. 
I'm not completely sure where such an error could come from, but most likely the letters appeared further apart either because of the historical printing itself or by how the page was scanned (pages not lying completely flat). 

## Different types of space errors
While examining the source documents I found this additional space error in almost all of the texts. 
However, they were not all exactly the same and needed to be processed differently.

### Normal Space Error (NomSpace) 
The most common space error affects a whole line. There is a space between each letter of the line and two spaces between the end and beginning of a word. 
This is the easiest type to restore because the smalles denominator "letter+space"-pair can be replaced by just the letter. 
Leaving regular words with a single space between words. 

Example: T h i s  &nbsp;i s &nbsp;a n  &nbsp;e x a m p l e .   
Result: This is an example.  

### Special Space Error (SpecSpace) 
The other type of space error also affects the whole line, however, here there are only individual spaces between letters including words. 
This makes it much more difficult to restore the sentence to its original structure. 
Applying the same process as for the NomSpace Error would lead to lines with no spaces at all. 
Depending on what you want to do with the text, this is arguably not much better as spaces in between letters. 
To improve the quality of the data a bit I first added additional spaces in front of capital letters. 
In German all nouns and proper names are capitalized, which does give a line a bit of a structure. 
Since I'm a historian and not a linguist (I assume) I'll be mostly interested in key information such as person + place names as well as maybe roles (teacher, student etc.) or identifying objects (book, coin, bone etc.). All of which would be capitalized in German. 
With that and a bit of fuzzy search I hope to get to the data I need even though it is not perfecly clean.  

Example: D a s i s t e i n n o r m a l e r d e u t s c h e r S a t z i n d i e s e n D o k u m e n t e n .  
Result: &nbsp;Dasisteinnormalerdeutscher Satzindiesen Dokumenten.  

### Very Special Space Error (VSpecSpace)
This type of error I only noticed while cleaning the other two types. 
Under this type falls everything that does have "letter-space" pairs within a line, but it is not the whole line and it doesn't necessarily occur at the beginning. 
To identify the other two types I was looking for a "letter-space"-pair (regex: \S\s) at the beinning of any line. 
This does not detect all instances of the thrid error type, which is why it is currently not included in any of my statistics on these errors. 
Right now I don't know yet how I could effectively isolate these instances and remove only the spaces that are too much within a line. 
Removing all spaces from a line such error occurs in (or applying the less ideal technique from above) would in many cases make the rest of the line less readable then the original. 
For now I will keep these errors as they are until I run into problems with it. Maybe this would be something that needs to be removed by hand.  

Example: This is a normal sentence and a l l &nbsp;o f a &nbsp;s u d d e n w i l d spaces appear. 


## Error statistics for the different societies 
