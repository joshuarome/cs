
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

Initially, I went to YouTube where I watched a video on how to use text to speech functions, which gave me a thorough understanding of how to successfully utilise event functions as I needed to make the text to speech only speak after pressing a button, which taught me how to use event functions. After this I started attempting to discover how to successfully use Arrays and Lists.  I started this off by defining a basic global array which contained 10 variables, and made it so when you touched the screen, it will slowly send alerts to the user with the 10 variables one by one, by indexing the array and printing the integer at that point in the indexed array. 

After this, I attempted to create a two dimensional as in my eyes, I could save the main base array as the part of the array that would store the computers so computers[1] would be the first computer block, and from there I could index either [1] for the x components of the computer room position, [2] for the y component of the computer room position or [3] for the amount of computers in the room, so depending on what I wanted I could index the computer. So for example if I wanted the X component of the 4th computer room I could index computers [4][1] which would return what I wanted, however after creating the array using the tedious method of the blocks, I came to the unfortunate conclusion that either the App Inventor software cannot handle 2D arrays or that I was trying to implement it in a poor fashion.

After this I had concluded that I did not need to do anymore external resources and that for any other needed information I will refer to App Inventors documentation which provides indepth explanation of each type of block and its purpose and how to use it.

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

My goal was to create a store of data which will store the number of computers available and display this data specific to each building after being touched or clicked. Originally, I had the idea to use the X and Y components of each building and running an event function so that when the Canvas is touched it will check if the X and Y position touched is within a 15 pixel radius of a building and if so running the code needed for that section. However I concluded that this method would be unefficent to complete and a poor choice, Instead of this method I opted into using Image Sprites upon each of the buildings displayed on the canvas since I can run event loops on each Image Sprite for when they are touched which solves the key issues of the previous method. I also decided that the use of Procedures with the code will greatly shorten the ammount of code that will need to be produced and will increase the efficiency of the program.

> **Source:** http://ai2.appinventor.mit.edu/reference/components/animation.html#ImageSprite ,  http://appinventor.mit.edu/explore/ai2/support/blocks/procedures.html

####Development

The first part of development I decided to tackle was the tedious task of placing Image Sprites over each building with a number on the canvas image and then naming each Image Sprite according to which building it was over on the canvas, so for example the Image Sprite over building 3 was called "cBlock3". This part of the development took the most time to complete as it was a very repetitive task and needed to be repeated 10 times. After I completed this part of the task, I created a text label called Label1 which  is positioned just above the canvas which will later display the information regarding each building. I then created all the event functions for each Image Sprite in Blocks, I had decided that each touched event function should call a procedure withto greatly shorten the ammount of blocks needed to complete this segment and shorten the time taken to complete this task, this procedure will have a parameter 'x' which will be used to inform the precedure which Computer Block the user has referenced, the procedure will get this information given to it when the touched event is triggered and it will send the number at the end of the Image Sprite name to the procedure, this was hard coded in. An example of this would be when Image Sprite 6 is touched, the procedure will be invoked from the touched event funtion with the parameter of 6 to specificy to the function that it needs to change values of building 6.I created the 'Run' Procuedure with a single parameter named 'x' and put the call function with the needed parameter in each block. Here is what my blocks looked like after this part:

![Touched Events](https://i.imgsafe.org/a25f46b.png)

After I had created the 10 touched event functions, I created two global Lists, one called c_Rooms and the other called c_Booked. Both these tables had 10 Items, however c_Rooms contained the integer number of the ammount of free computers in each room whilst c_Booked contained boolean values for each room in order to store if the user has already booked a computer in each room, to prevent the user from accidently booking to many computers. I filed in each Item in these two tables with the correct data, I also created a global variable called c_CurrentRoomValue which will be set inside of the Run Prodecure so that if any point in the code I need to find out what room is currently being booked, I can quickly access this variable. So inside the Run Procedure, I set the c_CurrentRoomVal to x and then set Label1.Text to use a join the strings "There are:", a select item list from the c_Rooms list and index's and x variable which will return the value of x at the list index, "Computers available in this building." After I had completed this, the main part of development for this question had been completed, here is what my blocks looked like: 

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

After the results I recieved from this test table, I had conlcuded that I had successfully completeted this task and had no more to develop or change, The main reason for the code not having any errors is due to the use of the procedure, this improves both the efficency of the program and greatly shorten the time taken to debug the code as any issue that would come up, would come up in each instance as the same code is used.
