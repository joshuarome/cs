
# A452 APP INVENTOR COURSEWORK

## Introduction:

###Gannt Graph:

![Gannt Graph](https://i.imgsafe.org/540569b.png)

As you can see from this Gannt graph, I have planned ahead in hope time management, and have gave myself time for each section to which I believe it would take, for example I have gave myself two to complete my evaluation whilst I gave myself one hour to complete both question 5 and 6

Question Research:
When I started my research, I looked at the question I was going to complete and from my original analysis I concluded that I was going to need to need to research:
-	Canvases
-	Image Sprites
-	Event functions (when IMAGESPRITE.TOUCHED and when NOTIFIER.AFTERCHOOSING)
-	How to use arrays effectively

Initially, I went to YouTube where I watched a video on how to use text to speech functions, which gave me a thorough understanding of how to successfully utilise event functions as I needed to make the text to speech only speak after pressing a button, which taught me how to use event functions. After this I started attempting to discover how to successfully use Arrays and Lists.  I started this off by defining a basic global array which contained 10 variables, and made it so when you touched the screen, it will slowly send alerts to the user with the 10 variables one by one, by indexing the array and printing the integer at that point in the indexed array. 
After this, I attempted to create a two dimensional as in my eyes, I could save the main base array as the part of the array that would store the computers so computers[1] would be the first computer block, and from there I could index either [1] for the x components of the computer room position, [2] for the y component of the computer room position or [3] for the amount of computers in the room, so depending on what I wanted I could index the computer. So for example if I wanted the X component of the 4th computer room I could index computers [4][1] which would return what I wanted, however after creating the array using the tedious method of the blocks, I came to the unfortunate conclusion that either the App Inventor software cannot handle 2D arrays or that I was trying to implement it in a poor fashion. 

Questions:

Question 1:

To start off with question one, I knew that my goal was to get a picture of a campus, label 10 buildings where computers could be and then set it up with App Inventor to display the map onto the device I was using. I started off by getting the picture of a campus given to me in the A452 pdf document and saving it and opening it up in Photoshop, after this I created 10 text labels and labelled each building in numerical order to create the first half of the task.
After this, I created a new project on App Inventor, separate from the one I used for my research and initial tests, and created a canvas item and parented it to Screen1, from there I changed the Canvas to fill the parent in both the X and Y dimensions. After this, I changed the Background Image to the Map Image thereby completing the task.


To test that his question had been successfully completed I ran the emulator and checked if the campus was visible, here is what my emulator looks like after this task:



Here is a screenshot to conclude that this stage had been successfully completed.


Question 2:

My goal for question two was to create a store of data which will store the number of computers available and display this data specific to each building after being touched or clicked. Originally, I had the idea to use the X and Y components of each building and running an event function so that when the Canvas is touched it will check if the X and Y position touched is within a 15 pixel radius of a building and if so running the code needed for that section. However, I encountered several issues for that, firstly there was no ‘set’ method of getting the X and Y components of each position on screen so to avoid inaccuracy of pixel locations, I avoided this method. Additionally, if there is an intersection within the 15 pixel radius there would more than likely require large chunks of mathematical operations which I personally believe would not be possible to run due to the awkward method of defining local variables, I would be forced to use global variables, the code required would be too intense to run every time the screen is clicked so I opted out of this.
I eventually came to the Idea that I should use Image Sprites upon each of the buildings on the Screen since I can run event loops on each of the Image Sprites which solves the both of the key issues I pointed out in the latter paragraph. I also decided to attempt to use procedures with the code, which has a single parameter x, Called from the original call event function to Index an List to get which room the user was attempting to Reserve/Cancel and any information in that entry of the table. This solved the issue of needing to repeat any code as I can just Index the tables I will define with the variable carried from the Image Sprite event.
After this I defined a global variable named ‘c_Rooms’ and made it a list with 10 entries, which is what I will use to define the amount of computers available to the user. I gave each entry random Integer values to avoid any obvious issues with Float variables, since you obviously can’t have ‘.x’ of a computer available.
Now I continued by finishing ‘writing’ the run procedure, I started off by setting a global variable called currentRoomVal to x so that if I have another procedure running at the same time, it can use this value to know which value is currently being accessed by the user. Then, I called another procedure I created entitled display, with the intended function to change a text label to display to the user the amount of computers available in the selected room, I used a set text label and used a join string function to join the words ‘There are: ‘, a list index function which indexed the c_Rooms list, indexed which the initial value passed from the run function which was passed to it by the touched event function from each block and a ‘Computers available in this building.’ This displayed correct to the user the amount of computers available to the user in the selected block each time. 
After this, I continued to write some code that will remove the chances that the user will ‘mass-reserve’ computers by checking if the index in the c_Booked table was true or false and making the reserve and cancel button enabled depending on the current Boolean value of the indexed value in the c_Booked table, the workings on the reserve and the cancel buttons will be expanded on in the answer to the next question. Here is what my code looks like from this section:


Question 3:
As stated on the task sheet, the goal of this question was to create two functioning buttons which will reserve a computer, and show the user that one less computer is available in the selected in the building and the inverse for the cancel button, so making one more computer available. I started going around this by adding a HorizontalArrangement Object to Screen 1 and adding two buttons, both with the instructions to fill parent on the width axis, but keep a 50 pixel on Height, this meant that App Inventor made both the buttons have an equal size, leaving the time and stress it would require for me to create two buttons which are of equal size, that both fill up the screen which was a nice touch which was one of the only things I actually enjoyed about using this program. After this I changed the text on both buttons to state their purpose to the User and also changed the buttons actually title, allowing it to be easier for me to use with blocks.
After this, I went through the audaciously tedious task of having to use the blocks to create for loops, index specific tables and use Boolean logic with a global variables for the before stated reason that local variables are confusing to use considering how the block function in the same way that for loops function. Firstly, I index the c_Rooms table with the current room value, which is changed when the user clicks a new button meaning that it is always updates, and check if it is more than or equal to 1, if it is, then it continues and will check the global variable c_BookedRoom and check if it is false or not, if it is false then the program will replace the item in the c_Booked room at the index of c_CurrentRoomVal and set it to true, and it will also replace the item in the c_Rooms list with the index of c_CurrentRoomVal and replace it with the same number but with one thanks to the maths blocks.

However, if the user has already booked a room, the program will set Label1’s text to tell the user that they have already booked a room. Also, if there is not sufficient rooms available, it changed Label1’s text to inform the user that there is not any spare computers and I left a space there as I will need to create a procedure to do Question 4.
Luckily, the process of creating the cancel button was much simpler, firstly when clicked, I make it check if they already have a computer booked, just in case the original run procedure does not correctly disable the cancel button when required. After this, it goes straight into the barebones of a cancel button, it index’s the c_Booked list with the index of c_CurrentRoomVal and replaces the item at the index with false and then it index’s the c_Rooms list with the index of c_CurrentRoomVal and replaces the item with the same integer as it previous had however with an additional value (+1). Overall, my code from this section looked as following:


Question 4:
In order to conclude this section of the task, I had to create a new procedure that will change the text label to show the user that will change the text of a label to inform the user which computer rooms are able to hold new bookings and for it to only be called when the user attempts to book in a computer room with no computers available.
I started off by creating a new empty procedure, from here I create a local variable as other methods I had attempted to use to go around this question had failed due to being returned the item at an index and not the index itself and a variety of other reasons, overall I concluded that using a local variable would be the most efficient, so I entitled the new local variable one and gave it the value of one. 
From here, I looped through each item inside of the c_Rooms table and checked accordingly if the item had an integer value of higher or equal to one, if so the program would set Label2.Text to use a join string function, of which would join what text was already in Label2.Text with another join string function which would join “C” and join the integer value of the local variable n to the computer rooms. After this, I added it so that it will increment the n variable by 1 to ensure that that wrong computer room is not displayed to the user and that only the computer rooms that have space are displayed to the user. Overall, my code from this section looked as following:
		







Question 5:
As of this step, my app is fully functioning and has no bugs of which I can find, I believe that the app would be a relatively useful addition to a member of a university as I personally believe that the app carries many benefits for the user, especially from the standpoint of a student, for example it will allow the student to see which computer rooms are actually available to the student and allow them to actually reserve the computers, to avoid the chance that by the time they get to the computer room, it has already been taken. 
This avoids the obvious issues of the student having the computer the student want to use being taken as it will have been and additionally, it has the advantage that if the computer room the user wanted to book is taken, they can choose another room and reserve straight from their phone as the application displays to the user the available rooms after the failed attempted booking. 	
Question 6:
To complete this step of the task, I am required to describe a useful additional feature which I could add to the existing app. My Idea is for the addition of a sound to the booking button so that once the booking is confirmed, the sound is played, giving the user a feedback of some sort to ensure that user that their reservation has in fact went through, after looking through YouTube for some button sounds, I decided on an effect entitled ‘Fast Swish’ which has a nice sound to it, which should not irritate the users ears whilst also providing feedback to the user. 
I believe that the idea of giving the user this sound as a sort of feedback to the user when an action has been completed, this in self has many positive features, for example as a secondary confirmation to the user that a booking has occurred which will remove any doubt in the users head relating to booking issues.

Question 7:
Now my task was to implement the sound idea which I provided information about in the previous question. I started the idea by using a YouTube to mp3 converter online [Reference 1] to download the sound clip. Inside of the App Inventor Web Client I added a Player item from the media tab and dragged it onto the screen, after this I clicked onto the source tab and uploaded the swish sound.
Now, my goal was to implement the sound into the application, so I opened up the blocks section and opened the reserve_button section and went to the end of the actual reservation code. Here I added an event function so that the Player would play the sound, after this I tested the code I had added, no new bugs have arisen and the code was working flawlessly.



Question 8:
To answer this question successfully, I will need to discuss the issues that would arise if implementing this app into a real life situation due to the fact that an online database will have to be used. In this section I will need to discuss several key points in a large amount of detail to successfully convey the issues of using an online database.
An online database is a database which is accessible from a network. In real life, an online database is usually implemented to host data online where it is usually more secure to be held and also allows more than one person to access the data at a single instance. Good examples of where online databases have been implemented would be in enforcing Car Tax and other laws relating to Motor Vehicles. A police officer can scan a vehicles license plate and get information almost instantaneously about the vehicle and if it is properly licensed and if car tax or MOT has been paid on the motor vehicle.
The first issue that comes to mind is the clear security issues that would need to be addressed, when thinking about possible security issues, two come to mind. Firstly the issue that would happen if an unauthorized user got access to the database and started booking and unbooking rooms at will, this would clearly detriment the success of implementing the app as some rooms will become fully booked on the database whilst in reality, no-one actually has booked a room and additionally, a person could book a room, go at the desired time to find that his reservation had been unbooked, which would in itself be a big issue. 
From [Reference 2] I have found many methods to maintain data integrity and security. The most important method of security which I have noted from Reference 2 is the use of some sort of encryption between the database and the client, like SSL which will ensure that all data transmitted to the database cannot be retrieved by a ‘man in the middle’ attack as SSL ensures that all data passed between the host and the client remains private and integral. 
Another method of security would be implementing a method of detection for SQL Injection so that outside sources cannot directly inject information into an entry field, Implementation of this would ensure that an outside source cannot inject malicious code into the database which would allow them to dump the database contents to the attacker giving them all the contents of the database, This would ensure that data security is ensured. 
However, whilst on the topic of database security I must bring up a point around ‘Anderson’s Rule’ [Reference 3] – Anderson’s Rule states that if a large system is designed for ease of access, it will become insecure; if made ‘watertight’ it will become impossible to use. If we were to follow this rule then we must find a good middle ground between usability and security to ensure integrity of user data and security.
Onto the actually subject of using an online database, I need to tackle how it will actually function. When the client opens the application and finds a suitable room to book and reserves the room via the internet the database will be sent some SQL code to decrement the current value of the selected room field by one to lem




References
-	www.clipconverter.cc/ - Used to convert the online video found on YouTube onto the Application
-	http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=08265121F6FB80D5AF5C2E2FD6B93AF8?doi=10.1.1.192.736&rep=rep1&type=pdf – I used this to find methods of database security.
-	https://en.wikipedia.org/wiki/Database_security - Used for quote about database security ( Anderson’s Rule)

