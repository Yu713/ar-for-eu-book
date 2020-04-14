## **Tutorial 3: AI dialog understanding**

#### by Xinyu Huang, Performance Augmentation Lab, Oxford Brookes University

The tutorial will introduce how to create a Chatbox using IBM Watson.

IBM Watson is a system, and it offers artificial intelligence (AI) tools to apply advanced natural language processing, including  speech to text, text to speech, Watson assistant, language translator, and so on.  



**Section 1: Create an IBM Cloud account** **& services****

1. Register an account https://cloud.ibm.com/login <- **create an IBM Cloud account** <- you'll be asked to **verify your email** (check your registered email)<- complete **personal information** <- **Login** (see pic1) <- **accept the privacy notices**

<img src="E:\PhD-2\Russia\Lesson\Pic\1-1.PNG" alt="1-1" style="zoom:60%;" />

​                                                                                   pic1   

1.1 Now, you enter the IBM Cloud services. Click on **Create+** (see pic1-1)<- select **AI (15)** (see pic1-2)<- We need **Watson Assistant**. 

<img src="E:\PhD-2\Russia\Lesson\Pic\1-2.png" alt="1-2" style="zoom:67%;" />

​                                                                           pic1-1

<img src="E:\PhD-2\Russia\Lesson\Pic\1.1.jpg" alt="1.1" style="zoom:67%;" />

​                                                                                      pic1-2

1.2 Click on the **title of Watson Assistant**<- **Create** at the bottom right, and also ensure the **region** is right.

****

**Section 2: Create a chatbox**

Before that, let's take an example. If you call a dessert shop, what the seller asks you questions?  Firstly, you may say I'd like to order some food, and the seller needs to know what you like to buy, and ask your phone number, and your name. This is a basic content of conversation to buy or order something. 



2.1 Click on <img src="E:\PhD-2\Russia\Lesson\Pic\4.JPG" alt="4" style="zoom:50%;" /> <- Select **Resource List** (pic 2-1) <- Click on **Services** <-**Watson Assistant-xx** <- **Launch Watson Assistant**<- **Create assistant**<- called AI training (or something you like) <- **Add a dialog skill**<- **Click on your assistant** 

<img src="E:\PhD-2\Russia\Lesson\Pic\2.1.png" alt="2.1" style="zoom:67%;" />

​                                                                                      pic 2-1

2.2 Add the **General** part of intents on the **Content Catalog**  <- Click on **Add to skill** (see pic 2-"General" offers lots of basic and useful contents of chat, such as thanks, good morning, good day, and etc. 

<img src="E:\PhD-2\Russia\Lesson\Pic\2.2.png" alt="2.2" style="zoom:67%;" />



2.3 Click on **Dialog** <- Click the **Node options  the on Welcome node****<img src="E:\PhD-2\Russia\Lesson\Pic\2.2.1.png" alt="2.2.1" style="zoom:50%;" /> <- **Add folder** <- named Dessert (see pic 2.3)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.3.png" alt="2.3" style="zoom:67%;" />

​                                                                               pic 2.3

2.4 Click on **Welcome** <-  **Customize the Welcome node prompt with （Assistant responds）**: Hello, Welcome to AI dessert shop. How can I help you? <- **Press Enter** add the other respond: Hi welcome to AI dessert shop, what can I do for you? <- Response variations are set to **random** (see pic 2.4)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.4.1.png" alt="2.4.1" style="zoom:67%;" />

​                                                                                   pic 2.4

2.5 Click on **Node options on the Dessert folder** <- **Add node to folder**  <- **called Name**<- Add responds below: OK, how can I call you? / what's your name? <- Response variations are set to **random** again (see pic 2.5)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.5.png" alt="2.5" style="zoom:67%;" />

​                                                                                        pic 2.5

 2.6 We need to create **intents** (Intents are used to set a customer's input, Watson assistant and select the correct dialog flow), Click **Intents** tab<- **Create Intent <- create a # name<- add example: I'm **@username**, my name is **@username**, call me **@username**; I'm **@sys-name (see pic 2.6). For example when I say my name is Yu (@username), the assistant will say nice to see you, Yu (@username)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.6.png" alt="2.6" style="zoom:67%;" />

​                                                                                 pic 2.6 

2.7  We need to add @username on **an entity**, Click on **My entities** <- **Create entities** <- 

Entity name is **@username, Value is name_syntax, type is Patterns, pattern is**<img src="E:\PhD-2\Russia\Lesson\Pic\2.6.1.JPG" alt="2.6.1" style="zoom:70%;" />

<- **Add value** (see **pic** 2.7)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.7.png" alt="2.7" style="zoom:67%;" />

​                                                                                   pic 2.7

2.8 Back on **Entities**<- Click on **System entities** <- you can select all of them (see pic 2.8)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.8.1.png" alt="2.8.1" style="zoom:67%;" />

​                                                                                 pic 2.8

2.9 Go back to **Intents** <- **Create intent** <- **Intent name is #order** <- **user example** can be: hi there, I'd like to order cakes; I wanna order some desserts. (or something like that)

2.10 Click **Dialog** tab<- Click on the **icon of dessert folder** <- **select Name node** <- **Enter condition**: #intents <- select **#order** (see pic 2.10)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.9.png" alt="2.9" style="zoom:67%;" />

​                                                                   pic 2.10

2.11 Click on **node options on the Name node**<- **Add child node**<- called **Dessert** <- **Enter condition**: **# intents, #name** , **add or**, select **@username**, and **add or**, **select @sys-person** <- Click on **node options on Assistant responds** <- Select **Open context editor**<- Variable is **username**, and value is <img src="E:\PhD-2\Russia\Lesson\Pic\2.10.png" alt="2.10" style="zoom:70%;" /><- **Assistant responds**: What desserts would you like to order, $username? <- Select **random** (see 2.11.1 and 2.11.2)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.11.1.png" alt="2.11.1" style="zoom:67%;" />

​                                                                         pic 2.11.1

<img src="E:\PhD-2\Russia\Lesson\Pic\2.11.2.png" alt="2.11.2" style="zoom:67%;" />

​                                                                            pic 2.11.2

2.12 **Create newline**: on **Dessert node**, we can **add the other response type**<img src="E:\PhD-2\Russia\Lesson\Pic\2.12.png" alt="2.12" style="zoom:60%;" /> <- **text**: Do you need a menu? or I can provide specials?

2.13 Obviously, there are **three options to answer**: first, I need a menu (2.13); second is the assistant recommends me (2.14); third, I know what I want to buy (2.15). 

2.13.1 **Make a menu**: **Create a new intent called #menu**<- **user example** can be like: I need a menu<- Back to **Dialog** <- **Create a new child node on the Dessert node called menu**<- condition is  **#menu** <- **respond**: OK, here is our menu <- **add new response type and select Option** <- **Title** is which dessert/menu you like <- **List labels** are Pudding and Cake, **values** are pudding menu and cake menu  (see pic 2.13.1 & 2.13.1.1)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.13.1.png" alt="2.13.1" style="zoom:67%;" />

​                                                                         pic 2.13.1

<img src="E:\PhD-2\Russia\Lesson\Pic\2.13.2.png" alt="2.13.2" style="zoom:67%;" />

​                                                                                   pic 2.13.1.1

2.13.2 Click **Entities** tab<- **Create a new entity** called **@menu** <-**Value**: cake, **type**: **Synonyms**, **Synonyms**: cookies and cream cake, chocolate cake, cream cake, and etc...Again, you can create a new value for pudding menu (see pic 2.13.2.1) 

Then,  Click **Intents** tab <- **Create Intent** called **#alldesserts** <- **list desserts** as more as possible (see pic 2.13.2.2)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.13.2.2.png" alt="2.13.2.2" style="zoom:67%;" />

​                                                                        pic 2.13.2

<img src="E:\PhD-2\Russia\Lesson\Pic\2.13.2.2.2.png" alt="2.13.2.2.2" style="zoom:67%;" />

​                                                                         pic 2.13.2.2



2.13.3 Back to **Dialog**<- **Create a new child node on the menu node** called pudding menu <- **If assistant recognizes**: @menu:pudding, add **or**, **#alldesserts** <- **Assistant responds:** We provide chocolate puddings, vanilla puddings, and milk puddings <- **Add child node on pudding menu**<- called pudding finish with **#alldesserts** **condition <- Assistant responds**: No problem! (it's possible that the client also wants to know the cake menu, you can create new nodes) <- Next, you can add a cake menu by yourself. (see pic 2.13.3)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.13.3.png" alt="2.13.3" style="zoom:50%;" />

​                                                                                     pic 2.13.3

2.14 & 2.15 It's the same way to create the cake menu nodes, and please **Add nodes below** **on the menu node** called specials and by clients (see pic 2.14 & 2.15)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.14 and 2.15.png" alt="2.14 and 2.15" style="zoom:67%;" />

​                                                                            pic 2.14 & 2.15

2.16 The assistant will ask phone numbers to send message to the client. **Add node below** on the **Dessert node** <- **called Phone number** <- **Assistant responds**: What's your phone number?  *(Don't add anything on the condition)*

2.17 **Create a new intent called #phonenumber** <- **examples are**: my phone number is @sys-number; number is @sys-number <- Go to **Dialog** tab <- **Add a child node on the phone number node** <- called end with conditions: **#phonenumber, and or, @sys-number**<- **assistant responds:** Thanks, we'll send a message to you.  

2.18 **Back to the pudding finish <- **Wait for reply** on "Then assistant should" need to **change to Jump on** <- **Select phone number node, click on Respond** (see pic 2.18.1 &2.18.2)

(so you don't need to add response types on each finish node)

<img src="E:\PhD-2\Russia\Lesson\Pic\2.17.1.png" alt="2.17.1" style="zoom:67%;" />

​                                                                              pic 2.18.1 

<img src="E:\PhD-2\Russia\Lesson\Pic\2.17.2.png" alt="2.17.2" style="zoom:67%;" />

​                                                                        pic 2.18.2







