
# A452 APP INVENTOR COURSEWORK

## Research

###Gannt Graph:

I decided that to complete the task in the stated time, I would need to properly plan out my time to ensure that I use the time efficently and properly. Here is my time graph:

![Gannt Graph](https://i.imgsafe.org/540569b.png)

As you can see from this Gannt graph, I have planned ahead in hope time management, and have gave myself time for each section to which I believe it would take, for example I have gave myself two hours to complete my evaluation whilst I gave myself one hour to complete both question 5 and 6.

###Question Research:

When I started my research, I looked at the question I was going to complete and from my original analysis I concluded that I was going to need to need to research:

> - Canvases
> - Image Sprites
> - Event functions (when IMAGESPRITE.TOUCHED and when NOTIFIER.AFTERCHOOSING)
> - How to use arrays effectively

Initially, I went to YouTube where I watched a video on how to use text to speech functions, which gave me a thorough understanding of how to successfully utilize event functions as I needed to make the text to speech only speak after pressing a button, which taught me how to use event functions. After this I started attempting to discover how to successfully use Arrays and Lists.  I started this off by defining a basic global array which contained 10 variables, and made it so when you touched the screen, it will slowly send alerts to the user with the 10 variables one by one, by indexing the array and printing the integer at that point in the indexed array. 

After this, I attempted to create a two dimensional as in my eyes, I could save the main base array as the part of the array that would store the computers so computers[1] would be the first computer block, and from there I could index either [1] for the x components of the computer room position, [2] for the y component of the computer room position or [3] for the amount of computers in the room, so depending on what I wanted I could index the computer. So for example if I wanted the X component of the 4th computer room I could index computers [4][1] which would return what I wanted, however after creating the array using the tedious method of the blocks, I came to the unfortunate conclusion that either the App Inventor software cannot handle 2D arrays or that I was trying to implement it in a poor fashion.

After this I had concluded that I did not need to do anymore external resources and that for any other needed information I will refer to App Inventors documentation which provides in depth explanation of each type of block and its purpose and how to use it.

> **Source(s):** https://www.youtube.com/watch?v=MH3VkVnu0E4 ,  http://appinventor.mit.edu/explore/library.html


##Questions:

###Question 1:

####Planning

To start off, I knew that my goal was to get a picture of a campus, label 10 buildings where computers could be and then set it up with App Inventor to display the map onto the device I was using. I can do this by creating a canvas item and then changing its background image property to the picture of the campus with the labelled 10 buildings.

> **Source:** http://ai2.appinventor.mit.edu/reference/components/animation.html#Canvas

####Development

I started off by getting the picture of a campus given to me in the A452 PDF document and saving it and opening it up in Photoshop, after this I created 10 text labels and labelled each building in numerical order to create the first half of the task. After this, I created a new project on App Inventor, separate from the one I used for my research and initial tests, and created a canvas item and parented it to Screen1, from there I changed the Canvas to fill the parent in both the X and Y dimensions. After this, I changed the Background Image to the Map Image thereby completing the task. 

####Testing

To test that his question had been successfully completed I ran the emulator and checked if the campus was visible, here is what my emulator looks like after this task:

![Campus Screenshot](https://i.imgsafe.org/4413785.png)

This screenshot concludes that this stage had been successfully completed.

###Question 2

####Planning

My goal was to create a store of data which will store the number of computers available and display this data specific to each building after being touched or clicked. Originally, I had the idea to use the X and Y components of each building and running an event function so that when the Canvas is touched it will check if the X and Y position touched is within a 15 pixel radius of a building and if so running the code needed for that section. However I concluded that this method would be inefficent to complete and a poor choice, Instead of this method I opted into using Image Sprites upon each of the buildings displayed on the canvas since I can run event loops on each Image Sprite for when they are touched which solves the key issues of the previous method. I also decided that the use of Procedures with the code will greatly shorten the amount of code that will need to be produced and will increase the efficiency of the program.

> **Source(s):** http://ai2.appinventor.mit.edu/reference/components/animation.html#ImageSprite ,  http://appinventor.mit.edu/explore/ai2/support/blocks/procedures.html , http://appinventor.mit.edu/explore/ai2/support/blocks/lists.html#makealist

####Development

The first part of development I decided to tackle was the tedious task of placing Image Sprites over each building with a number on the canvas image and then naming each Image Sprite according to which building it was over on the canvas, so for example the Image Sprite over building 3 was called "cBlock3". This part of the development took the most time to complete as it was a very repetitive task and needed to be repeated 10 times. After I completed this part of the task, I created a text label called Label1 which  is positioned just above the canvas which will later display the information regarding each building. I then created all the event functions for each Image Sprite in Blocks, I had decided that each touched event function should call a procedure which greatly shorten the amount of blocks needed to complete this segment and shorten the time taken to complete this task, this procedure will have a parameter 'x' which will be used to inform the procedure which Computer Block the user has referenced, the procedure will get this information given to it when the touched event is triggered and it will send the number at the end of the Image Sprite name to the procedure, this was hard coded in. An example of this would be when Image Sprite 6 is touched, the procedure will be invoked from the touched event function with the parameter of 6 to specificy to the function that it needs to change values of building 6.I created the 'Run' Procuedure with a single parameter named 'x' and put the call function with the needed parameter in each block. Here is what my blocks looked like after this part:

![Touched Events](https://i.imgsafe.org/a25f46b.png)

After I had created the 10 touched event functions, I created two global Lists, one called c_Rooms and the other called c_Booked. Both these tables had 10 Items, however c_Rooms contained the integer number of the amount of free computers in each room whilst c_Booked contained boolean values for each room in order to store if the user has already booked a computer in each room, to prevent the user from accidentally booking to many computers. I filed in each Item in these two tables with the correct data, I also created a global variable called c_CurrentRoomValue which will be set inside of the Run Prodecure so that if any point in the code I need to find out what room is currently being booked, I can quickly access this variable. So inside the Run Procedure, I set the c_CurrentRoomVal to x and then set Label1.Text to use a join the strings "There are:", a select item list from the c_Rooms list and index's and x variable which will return the value of x at the list index, "Computers available in this building." After I had completed this, the main part of development for this question had been completed, here is what my blocks looked like: 

![Question 2 Code](https://i.imgsafe.org/7dbdefc.png) 

Here is what my emulator looked like:

![Question 2 Emulator](https://i.imgsafe.org/42792a4.png)

####Testing

For this segment, I needed to test that the code was working correctly and when each building is clicked the current ammount of available computers is displayed by the text label, here is a test table to show the results I recieved when testing each button:

| Button Clicked |                   Expected Outcome                  |                    Actual Outcome                   | Did it function as expected? |
|----------------|:---------------------------------------------------:|:---------------------------------------------------:|------------------------------|
| 1              | "There are 19 computers available in this building" | "There are 19 computers available in this building" | Yes.                         |
| 2              | "There are 18 computers available in this building" | "There are 18computers available in this building"  | Yes.                         |
| 3              | "There are 17 computers available in this building" | "There are 17 computers available in this building" | Yes.                         |
| 4              | "There are 16 computers available in this building" | "There are 16 computers available in this building" | Yes.                         |
| 5              | "There are 15 computers available in this building" | "There are 15 computers available in this building" | Yes.                         |
| 6              | "There are 14 computers available in this building" | "There are 14 computers available in this building" | Yes.                         |
| 7              | "There are 13 computers available in this building" | "There are 13 computers available in this building" | Yes.                         |
| 8              | "There are 12 computers available in this building" | "There are 12 computers available in this building" | Yes.                         |
| 9              | "There are 11 computers available in this building" | "There are 11 computers available in this building" | Yes.                         |
| 10             | "There are 0 computers available in this building"  | "There are 0 computers available in this building"  | Yes.                         |

After the results I received from this test table, I had concluded that I had successfully completed this task and had no more to develop or change, The main reason for the code not having any errors is due to the use of the procedure, this improves both the efficiency of the program and greatly shorten the time taken to debug the code as any issue that would come up, would come up in each instance as the same code is used.

###Question 3

####Planning

As stated on the task sheet, the goal of this question was to create two functioning buttons which will reserve a computer, and show the user that one less computer is available in the selected in the building and the inverse for the cancel button, so making one more computer available.

####Development

I started going around this by adding a HorizontalArrangement Object to Screen 1 and adding two buttons, both with the instructions to fill parent on the width axis, but keep a 50 pixel on Height, this meant that App Inventor made both the buttons have an equal size, leaving the time and stress it would require for me to create two buttons which are of equal size, that both fill up the screen which was a nice touch which was one of the only things I actually enjoyed about using this program. After this I changed the text on both buttons to state their purpose to the User and also changed the buttons actually title, allowing it to be easier for me to use with blocks. I also decided that I should add a single boolean variable which will contain a boolean to prevent the user to only book a single room so I created this variable, entitled c_BookedRoom with a default value of false, so that when you book a room, you can only book a single room.

![](https://i.imgsafe.org/804b2d8.png)

After I had completed this, I went to start doing the blocks for the reserve button. So I started off by creating the Reserve_Button clicked event function. I then added an if loop and inside the if loop, I added a math operator block, to check if the input on the left side is greater than or equal to 1 and then in the left side added a select item block, which got the item from the c_Rooms block with the index of C_CurrentRoomValue, which will allow the if block to check if the room selected has enough rooms and allow the user to book. After this I check if the user has booked a room by using yet another if loop and checking the c_BookedRoom variable to see if it is false, if it was then I used two replace list item block, one to change the c_Booked list at the index of c_CurrentRoomVal to true, and one to change the c_Rooms list at the index of c_CuurentRoomVal to one less that it currently is. After this I decided to add two else statements to each if statement block, so for the second if statement, it changes label1.text so that it says: "You already have a computer booked!", this way it can inform the user why their request to book did not go through and for the first if statement makes it so it will say "There are not any computers spare here" for the same reason as the other if statement.

![](https://i.imgsafe.org/942e8cd.png)

Now I had to complete the second half of the task by finishing the Cancel_Button click function. I then did the complete inverse of the Reserve_Button, so instead of the if statement checking if the c_BookedRoom was false, it checks if c_BookedRoom is true, and then if so will continue with the program to do yet again the complete inverse of the replace list items in the Reserve_Button event, so instead of changing the item of c_Booked at the index of c_CurrentRoomVal to true, it turns it to false and instead of taking away one from the item of c_Rooms at the index of c_CurrentRoomVal it instead adds one. I also added an else statement to the if block so that if the user does not have a booked room, but is pressing  Cancel_Button then it will change Label1.Text to "You don't have a computer booked!". 

![](https://i.imgsafe.org/2c34def.png)

> **Source(s):** http://ai2.appinventor.mit.edu/reference/components/layout.html#HorizontalArrangement , http://ai2.appinventor.mit.edu/reference/components/userinterface.html#Button , http://appinventor.mit.edu/explore/ai2/support/blocks/logic.html , http://appinventor.mit.edu/explore/ai2/support/blocks/control.html#if , http://appinventor.mit.edu/explore/ai2/support/blocks/math.html#subtract , http://appinventor.mit.edu/explore/ai2/support/blocks/lists.html#selectlistitem , http://appinventor.mit.edu/explore/ai2/support/blocks/lists.html#replace

####Testing

For this segment, I had to check that the code I had created for this question was functioning correctly, yet again I decided to present this by using a test table to show my results, here are my results for reserve_button:


| Button Clicked | Expected Outcome                                     | Actual Outcome                                      | Did it function as expected? |
|:--------------:|------------------------------------------------------|-----------------------------------------------------|------------------------------|
| 1              | "There are 18 computers available in this building"  | "There are 18 computers available in this building" | Yes.                         |
| 2              | "There are 17 computers available in this building"  | "There are 17 computers available in this building" | Yes.                         |
| 3              | "There are 16 computers available in this building"  | "There are 16 computers available in this building" | Yes.                         |
| 4              | "There are 15 computers available in this building"" | "There are 15 computers available in this building" | Yes.                         |
| 5              | "There are 14 computers available in this building"  | "There are 14 computers available in this building" | Yes.                         |
| 6              | "There are 13 computers available in this building"  | "There are 13 computers available in this building" | Yes.                         |
| 7              | "There are 12 computers available in this building"  | "There are 12 computers available in this building" | Yes.                         |
| 8              | "There are 11 computers available in this building"  | "There are 11 computers available in this building" | Yes.                         |
| 9              | "There are 10 computers available in this building"  | "There are 10 computers available in this building" | Yes.                         |
| 10             | "There are not any computers spare here"             | "There are not any computers spare here"            | Yes.                         |


Here are my results for cancel_button, for this test I reserved the computer prior to doing the cancel where possible to ensure that it was actually testing the actual code for the button, the results can be seen here:


| Button Clicked |                   Expected Outcome                  |                    Actual Outcome                   | Did it function as expected? |
|----------------|:---------------------------------------------------:|:---------------------------------------------------:|------------------------------|
| 1              | "There are 19 computers available in this building" | "There are 19 computers available in this building" | Yes.                         |
| 2              | "There are 18 computers available in this building" | "There are 18computers available in this building"  | Yes.                         |
| 3              | "There are 17 computers available in this building" | "There are 17 computers available in this building" | Yes.                         |
| 4              | "There are 16 computers available in this building" | "There are 16 computers available in this building" | Yes.                         |
| 5              | "There are 15 computers available in this building" | "There are 15 computers available in this building" | Yes.                         |
| 6              | "There are 14 computers available in this building" | "There are 14 computers available in this building" | Yes.                         |
| 7              | "There are 13 computers available in this building" | "There are 13 computers available in this building" | Yes.                         |
| 8              | "There are 12 computers available in this building" | "There are 12 computers available in this building" | Yes.                         |
| 9              | "There are 11 computers available in this building" | "There are 11 computers available in this building" | Yes.                         |
| 10             | "You don't have a computer room booked!"  | "You don't have a computer room booked!"  | Yes.                         |


From these results, I can conclude that I have successfully finish this question and had nothing else to change.

###Question 4

####Planning

This questions requires me to create a feature which will display which computers available when a user touches a building that has no spaces left. To do this, I had several ideas like placing a marker above each building however I stuck with the most logical and easiest method of changing a text label to inform the user which buildings are available so for example, this text label would change to "There are no computers available here, try: "C1,C2,C3,C4,C5,C6,C7" and so on. The only new aspect of App Inventor which I needed to use for this was a local variable and a for each item in list both which I found how to use via the App Inventor documentation which can be seen below.

> **Source(s):** http://appinventor.mit.edu/explore/ai2/support/blocks/control.html#foreach , http://appinventor.mit.edu/explore/ai2/support/blocks/variables.html#do

####Development

I started off the development with creating yet another new Procedure called "empty", inside here I declare a local variable called n with the integer value of 1. I then loop through each Item in the c_Rooms list using the for each n in list block stated in the planning stage, I then get an if statement alongside a math block to find out if n (the item in the list at this point) is greater than 1 and if so, it will set Label2 to itself plus "C" plus n. After this I will increase the value of n by one. I will do this for each loop of the for each in list, this will make sure that the text label will only tell the user which computer rooms are available so that the user will be correctly informed. 

Now all I needed to do was add the procedure call to an event, since it only needed to be called when there was no space in the room being booked, I decided to append this to the Reserve_Button first else statement where it tells the user that there are no computers spare. I changed the code so that it will instead tell the user:

> "There are not any computers spare here - Below you can see where computers are available."

And then I call the empty procedure, this can be seen here followed by the code I had created for this segment:

![](https://i.imgsafe.org/bb2b57f.png)

![](https://i.imgsafe.org/1f7f74c.png)

####Testing

I now had to test if the code I had created for this segment has function correctly and if the new text label was in fact displaying the buildings that are available, for this I manually edited the c_Rooms list so that I could properly test if this worked, below is my testing table.

| Button Clicked | Data edited                                                              | Expected Outcome                   | Actual Outcome               | Did it function as expected? |
|----------------|---------------------------------------------------------------------------|------------------------------------|------------------------------|------------------------------|
| 10             | None.                                                                     | "C1,C2,C3,C4,C5,C6,C7,C8,C9"       | "C1,C2,C3,C4,C5,C6,C7,C8,C9" | Yes.                         |
| 2              | None.                                                                     | For the procedure to not be called | Procedure was not called.    | Yes.                         |
| 6              | I changed c_Rooms 1 and 5 to 0                                            | "C2,C3,C4,C6,C7,C8,C9"             | "C2,C3,C4,C6,C7,C8,C9"       | Yes.                         |
| 4              | Changed all of c_Rooms to 0 except c_Rooms 7, which maintained same value | "C7"                               | "C7"                         | Yes.                         |

After I received these results, I yet again concluded that I have successfully completed this task and I reset all data augmented by this stage to its original values to maintain consistency throughout development/testing.

###Question 5

####Evaluation of progress so far.

As of this point, I have completed task 1 through 4 and my application is fully functioning and has no bugs what I can find, I believe that the app would be a relatively useful addition to a member of a university as I personally believe that the application carries many benefits for the user, especially from the standpoint of a student in a university. For example, it will allow the student to see which computer rooms are actually open and have available spaces, this factor in itself will free students of time wasted walking around from building to building attempting to find an computer room with available spaces. Also the feature of allowing the student to book a space in the computer room also removes the risk that the student checks the application, goes to the building just to find that in fact there are not any free spaces available and the student would of wasted their time walking over, which clearly is not good.

Overall, I believe that as of this point, the application would heavily benefit a student as it would allow the student to efficiently use their time to the utmost possible in regards to wasting time traveling around from building to building in an attempt to complete tasks which the user needs a computer to complete.


###Question 6

To complete this question, I need to describe a usefull additional feature to implement to my exisitng application. I had several ideas for this segment, like disabling the reserve/cancel button for each room depending on if they have already booked a room. However, I ended up deciding that implementing a sound that will play when you book a room to be a better implementation, my reasoning behind this is that the sound can act as a confirmation to the user so that they can know without a doubt that the app has processed there request and that the room is booked, ready and waiting for them.


###Question 7

####Planning

My goal for this question was simple, I had to work on the idea stated in the latter question and implement it into my application. I started off by browsing through youtube to find a suitable sound to play to the user when they had booked the room, after searching for around 10 minutes, I had decided on a sound entilted "Fast Swish" as I believe the sound to be loud, clear and not irritating, three features which I personally believe to be a necessity to a sound for this purpose. The sound can be seen here: 

> https://www.youtube.com/watch?v=OUXFL1twa90

Now my goal was to convert and download this sound to an MP3 sound to allow it to be implemented into the application, after googling for a 'Youtube to MP3 converter', I decided to use a site called "clipconverter.cc" for its simple UI and fast conversion, so I used the site and downloaded the sound which allowed me to move onto the development stage of this question.

> **Source(s)** https://www.youtube.com/watch?v=OUXFL1twa90 , http://www.clipconverter.cc/

####Development

Inside the App Inventor designer tab, I added a Player Item from the Media tab on the left side of the screen. I then clicked onto the Player item and clicked onto the 'source' property and uploaded the Fast swish sound which I downloaded from the clipconverter website. Now I had to make the sound play when a room is booked, so I went to reserve_button and went into where the actual booking occurs, in here I added a event from the Player item called "start" and added it to the segment in the reserve button where the values of c_Room and c_Booked are changed. The changes I have made can be seen here:

![](https://i.imgsafe.org/9a5264e.png)

####Testing

Now, I had to test the code I had added to ensure that it successfully works, to this, I yet again use another test table, here are my results:

| Button Clicked | Expected Outcome                                           | Actual Outcome                                                 | Did it function as expected? |
|----------------|------------------------------------------------------------|----------------------------------------------------------------|------------------------------|
| 1              | Sound to be played                                         | Sound was played                                               | Yes.                         |
| 3              | Sound to be played                                         | Sound was Played                                               | Yes.                         |
| 10             | Sound to not be played, display buildings with free spaces | Sound was not player and buildings with spaces were displayed. | Yes.                         |

After this, I can successfully conclude that I have completeted this question.

###Question 8

The goal of this question is to discuss the issues of the real-world implementation of this as it would require an onliine database and to discuss the issues of using an online database.
 
 **What is an online database?**
 > An online database is a database accessible from a network, including from the Internet. It differs from a local database, held in an individual computer or its attached storage, such as a CD.
 
 > **Source:** https://en.wikipedia.org/wiki/Online_database 
 
 In real life, An online database is usually used to host data online where it is, for the most part, more secure to be held and additionally allows for than a single user to access the data at a single instance. A good example of where an online database would be used is by the police when enforcing Car Tax and other laws relating to vehicles. A police officer can scan a vehicles license plate and recieve information about the vehicle almost instantaneously by querying the database with the license plate and recieve all information required about the vehicle, this allows them to enforce the law straight away instead of pulling over the driver unnecessarily.
 
 The first clear issue of using an online database is security, firstly the issue of an unauthorised user gaining access to the database, this would allow them to book and unbook rooms at well, this is obviously very detrimental to the success of the app as this would mean that students could not actually use the app for its intended purpose. From wikipedia, I have found multiple methods to maintain data integrity and security, this can be seen here:
 
 > **Source:** http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=08265121F6FB80D5AF5C2E2FD6B93AF8?doi=10.1.1.192.736&rep=rep1&type=pdf
 
 Two methods stand out to me from that source, SSL connections and SQL Injection Detection. These two methods are important for different reasons. Firstly, SSL connections between the host and the client would that all data is encrypted and therefore the information remains private and secure. Also, SSL connections protects the data from being 'stolen' by 'man in the middle' attacks as it will drop all information if interupted. The second method of protection would be implementing detection of SQL Injection so that outside sources cannot directly inject information into an entry field, implementation of this would ensure that an outisde source cannot inject malicious code into the database which would allow them to dump the database countents to the attack giving them all the contents of the database, This would ensure that data security is ensured.
 
 > **Source:** https://www.digicert.com/ssl.htm, http://thehackernews.com/2014/09/how-to-detect-sql-injection-attacks.html
 
 Whilst on the topic of database security, I must bring up the point around 'Anderson's Rule'.
 
**What is Anderson's rule?**
> Ross J. Anderson has often said that by their nature large databases will never be free of abuse by breaches of security; if a large system is designed for ease of access it becomes insecure; if made watertight it becomes impossible to use. This is sometimes known as Anderson's Rule

> **Source:** https://en.wikipedia.org/wiki/Database_security 

If Anderson's rule is to be true then a good middle ground must be found between usability and security to ensure integrity of user data but also to ensure that the database is easy to access and does not require large bulky code on the client side just to query and send data. 

Data validation would also need to be present on the database, this is a neccasity because without data validation two user would be able to book the same room at the same time, this would could cause the database to stop and possibly break. A method of database validation would be by recording each attempt to reserve a computer, and only allow the user who sent the request first to reserve the computer and then telling each other client who attempted to book the room that the computer has been taken and to try to book another room.

Now we must talk about how the online database would actually be used. I believe that the best method of communication with an online database would be with SQL, I have several reasons why I believe SQL to be the best choice:

- SQL can execute queries against a database
- SQL can retrieve data from a database
- SQL can insert records in a database
- SQL can update records in a database
- SQL can delete records from a database
- SQL can create new databases
- SQL can create new tables in a database
- SQL can create stored procedures in a database
- SQL can create views in a database
- SQL can set permissions on tables, procedures, and views

All these features are very valuable to us as we will need to execute queries, retrieve data and update records constantly in the application if it were to be used in the real world, for example when the user needs to find out how many computers are free, instead of indexing the local list, they would need to send a query to the database to find out how many people are in computer block x and to display the information, and when they want to reserve a room, insetad of indexing two local lists, the user would need to update records in the database to inform it that the user has booked a room, and to show the in the database. The type of data needing to be stored by the database would be majoritly integer based as only computers available would generally need to be stored, however this could possibly change upon real world implementation as new issues may arise.

###Evaluation

####Justification

Throughout my solution, I have always attempted to use the most efficent and practical methods possible. The tests I have completed have been to test the specific points of each question and overall I am happy with the outcome of my program and this write-up.

####Effects of time-restrains.

Having a strict time restraint throughtout the coursework has been quite a stressfull for me, as I usually like to take my time with things like this to ensure that I get all information required for each question, I went through some parts of developing the solution where I wanted to go back and re-start the whole process however due to the time restrictions this was not possible to do.

####Code Optimisation

In hindsight, I can see one specific area where I could improve my code which would be with the use of c_Booked and c_BookedRoom as they both are restricitve to each other, for example my code will only allow one room to be booked at a single instance so the use of c_Booked is unjustified and unnecessary, if I had the required time, I would go back and remove these parts.

####Overall feelings about the project.

At first I was not very happy at using App inventor as in my own personal opinion I felt like this was a step-down in comparison to my ususual standard and some concepts seemed absurd to me, however as I went through the project, these concepts became more and more familiar to me and has got me to the point that I am at now where I believe that I completley understand all of the blocks and concepts inside App Inventor and could use them if asked too. My solution has been wrote to be the most efficent and pratical possible, which I beleive I have achieved, I have stored all data in table instead of individual variables to keep the code clean and have used procuedures where possible to yet again, minimise repeated code. In conclusion, I believe my App is easy to use, as proven by my testing tables and bug-free to use and would be very usefull if ever put into a real life situation, this has all been discussed in Question 8. This coursework has taught me methods of picking up alternative programming languages from that I am used to and overall I have found doing this coursework helpfull.


