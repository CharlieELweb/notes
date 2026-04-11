---
title: CS2204 HTML CW2
draft: false
tags:
---
***Update: fixed `order.js` to fulfil requirement 5.1***
 
---

> **Due Date:** 14 April 2025, **Tuesday**, 23:59 PM<br>
> **Deliverable:** Compress the root folder into a `zip` file.

## 1.  Requirements of Structure
- Duplicate your CW1 assignment folder
- Change the folder name to `ChengNg_Jessica_CW2`
- Create 1 new file in the `/css` sub-folder: `order.css`
- Create 2 new files in the `/javascript` sub-folder: `homepage.js` and `order.js`

***After this step, your folder should look like this:***
> [!abstract]+ **ChengNg_Jessica_CW2**
> - **index.html**
> 
> > [!example]+ **html**
> > - **order.html**
> > - **design.html**
>
> > [!example]+ **image**
> > - **button.jpg** 
> > - **dining-1.jpge**
> > - **dining-2.jpge**
> > - **hotel-1.jpge**
> > - **hotel-2.jpge**
> > - **hotel-3.jpge**
> > - **hotel-4.jpge**
> > - **location.jpg**
> > - **logo.png**
> > - **ticket-1.jpge**
> > - **ticket-2.jpge**
> > - **ticket-3.jpge**
>
> > [!example]+ **css**
> > - **theme.css** 
> > - **order.css** _(NEW)_
>
> > [!example]+ **javascript**
> > - **homepage.js** _(NEW)_
> > - **order.js** _(NEW)_

## 2. Home page web elements positioning

> [!info]
> You may quickly copy all the code of a block from this website by clicking the code block and then clicking the icon in the top-right corner.

- Change the `index.html` structure as follows, and replace each **\*\*block content\*\***  from the CW1:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Disneyland</title>
    <link rel="stylesheet" href="./css/theme.css" media="screen" type="text/css">
    <script src="https://personal.cs.cityu.edu.hk/~cs2204/cs2204cw3.js"></script>
    <script src="./javascript/homepage.js"></script>
</head>
<body>
    <!-- Header -->
    <header class="block">
        ** Header Content **
    </header>
    <div class="welcome block">Welcome</div>
    <div id="main">
        <!-- Basic Information Blcok -->
        <div class="info block">
            ** Basic Information Content **
        </div>
        <!-- Page Content -->
        <div class="page_content block">
            <!-- Promotion Information Block -->
			<div class="promotion_information">
				<h3 id="promotion_message">DISNEY PREMIER ACCESS & 1-DAY TICKET COMBO, STARTING FROM HK $798</h3>
				<video id="promotion_video" controls autoplay muted>
					<source src="https://personal.cs.cityu.edu.hk/~cs2204/video/Castle.mp4" type="video/mp4">
					<source src="https://personal.cs.cityu.edu.hk/~cs2204/video/Castle.ogg" type="video/ogg">
					Your browser does not support this video of Disneyland.
				</video>
			</div>
    
            <!-- Booking Block -->
            <div class="booking">
                <form action="#" method="get">
                    <fieldset>
                        <legend>Booking Information</legend>
                        <div class="booking_item">
                            <label for="bookdate">Date:</label>
                            <input type="date" name="bookdate" id="bookdate">
                        </div>
                        <div class="booking_item">
                            <label for="booktime">Time:</label>
                            <select name="booktime" id="booktime">
                                <option value="8:00AM-10:00AM">8:00AM-10:00AM</option>
                                <option value="10:00AM-12:00NN">10:00AM-12:00NN</option>
                                <option value="12:00NN-2:00PM">12:00NN-2:00PM</option>
                                <option value="2:00PM-4:00PM">2:00PM-4:00PM</option>
                                <option value="4:00PM-6:00PM">4:00PM-6:00PM</option>
                                <option value="6:00PM-8:00PM">6:00PM-8:00PM</option>
                            </select>
                        </div>
                        <div class="booking_item">
                            <label for="novisitor">No.of Visitors:</label>
                            <input type="number" name="novisitor" value="" id="novisitor" min="0">
                        </div>
                        <div id="warning" style="display:none;">Data not completed. Please re-enter.</div>
                        <div class="booking_operation">
                            <input id="booking_submit" type="submit" value="Check Availability">
                            <input type="reset" value="Reset">
                        </div>
                    </fieldset>
                </form>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="block">
        &copy;CityU 2026 - Sources of images and text from official website of Hong Kong Disneyland, Wikipedia and Courtesy of Icon pack by Icons8 - Designed by <a href="./html/design.html">Cheng Ng Jessica</a>.
    </footer>
 
</body>
</html>
```

- Inside `theme.css`, add the following lines to create the **two-column layout**:
```css
#main {
    height: 800px;
    margin-bottom: 30px;
}
.info {
    width: calc(40% - 25px);
    height: 100%;
    float: left;
}

.page_content {
    width: calc(60% - 25px);
    height: 100%;
    float: right;
}
```
- Inside `theme.css`, add a **border** to the `.block` class:
```css
.block {
    border-radius: 10px;
    border: 1px solid gray;
    margin-bottom: 5px;
    padding: 10px;
}
```
> [!note]
> This is a very basic example. You may design your own border style. 
- Inside `theme.css`, add the following lines to justify the booking form:
```css
.booking fieldset {
    display: flex;
    flex-direction: column;
    gap: 5px;
    align-items: center;
}

.booking fieldset>div {
    width: 70%;
    max-width: 500px;
    display: flex;
    justify-content: space-between;
}

.booking .booking_operation>input{
    width: calc(50% - 5px);
}

.booking #warning {
    text-align: center;
}
```
> [!note]
> For other requirements, we've already fulfilled in the CW1.
## 3. Order Page Web elements positioning and effects
- Change the `html/order.html` structure as follows, and replace the **\*\*Header Content\*\***  from the CW1:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Order | Disneyland</title>
    <link rel="stylesheet" href="../css/theme.css" media="screen" type="text/css">
    <link rel="stylesheet" href="../css/order.css" media="screen" type="text/css">
    <script src="../javascript/order.js"></script>
</head>
<body>
    <!-- Header -->
    <header class="block">
        ** Header Content **
    </header>
    <div class="welcome block">Welcome</div>
    <div id="main">
        <!-- Menu Block -->
        <div class="menu block">
            <h2>Menu</h2>
            
            <h3 class="menu_heading ticket">Tickets</h3>
            <h3 class="menu_heading dining">Dinings</h3>
            <h3 class="menu_heading hotel">Hotels</h3>
            <div class="menu_content ticket">
                    <form action="#" method="get" id="ticket1_form">
                        <img src="../image/ticket-1.jpeg" alt="1-Day Ticket">
                        <label for="ticket1">1-Day Ticket</label>
                        <div class="menu_operation">
                            <input type="number" name="ticket1" id="ticket1" min="1" required>
                            <input type="submit" id="ticket1_sumbit" value="Add">
                        </div>
                    </form>
                    <form action="#" method="get" id="ticket2_form">
                        <img src="../image/ticket-2.jpeg" alt="1-Day Ticket (Child)">
                        <label for="ticket1">1-Day Ticket (Child)</label>
                        <div class="menu_operation">
                            <input type="number" name="ticket2" id="ticket2" min="1" required>
                            <input type="submit" id="ticket2_sumbit" value="Add">
                        </div>
                    </form>
                    <form action="#" method="get" id="ticket3_form">
                        <img src="../image/ticket-3.jpeg" alt="2-Day Ticket">
                        <label for="ticket3">2-Day Ticket</label>
                        <div class="menu_operation">
                            <input type="number" name="ticket3" id="ticket3" min="1" required>
                            <input type="submit" id="ticket3_sumbit" value="Add">
                        </div>
                    </form>
                </div>
            
            <div class="menu_content dining">
                    <form action="#" method="get" id="dining1_form">
                        <img src="../image/dining-1.jpeg" alt="Explorer's Semi Buffet">
                        <label for="dining1">Explorer's Semi Buffet</label>
                        <div class="menu_operation">
                            <input type="number" name="dining1" id="dining1" min="1" required>
                            <input type="submit" id="dining1_sumbit" value="Add">
                        </div>
                    </form>
                    <form action="#" method="get" id="dining2_form">
                        <img src="../image/dining-2.jpeg" alt="3-in-1 Park Meal Voucher">
                        <label for="dining1">3-in-1 Park Meal Voucher</label>
                        <div class="menu_operation">
                            <input type="number" name="dining2" id="dining2" min="1" required>
                            <input type="submit" id="dining2_sumbit" value="Add">
                        </div>
                    </form>
                </div>
            
            <div class="menu_content hotel">
                    <form action="#" method="get" id="hotel1_form">
                        <img src="../image/hotel-1.jpeg" alt="Standard Room">
                        <label for="hotel1">Standard Room</label>
                        <div class="menu_operation">
                            <input type="number" name="hotel1" id="hotel1" min="1" required>
                            <input type="submit" id="hotel1_sumbit" value="Add">
                        </div>
                        
                    </form>
                    <form action="#" method="get" id="hotel2_form">
                        <img src="../image/hotel-2.jpeg" alt="Deluxe Room">
                        <label for="hotel1">Deluxe Room</label>
                        <div class="menu_operation">
                            <input type="number" name="hotel2" id="hotel2" min="1" required>
                            <input type="submit" id="hotel2_sumbit" value="Add">
                        </div>
                    </form>
                    <form action="#" method="get" id="hotel3_form">
                        <img src="../image/hotel-3.jpeg" alt="Sea View Room">
                        <label for="hotel3">Sea View Room</label>
                        <div class="menu_operation">
                            <input type="number" name="hotel3" id="hotel3" min="1" required>
                            <input type="submit" id="hotel3_sumbit" value="Add">
                        </div>
                    </form>
                    <form action="#" method="get" id="hotel4_form">
                        <img src="../image/hotel-4.jpeg" alt="Kingdom Club Room">
                        <label for="hotel4">Kingdom Club Room</label>
                        <div class="menu_operation">
                            <input type="number" name="hotel4" id="hotel4" min="1" required>
                            <input type="submit" id="hotel4_sumbit" value="Add">
                        </div>
                    </form>
                </div>
        </div>
        <!-- Ordered Item Block -->
        <div class="ordered_item block">
            <h2>Ordered Items</h2>
            <h4>XX Feb 2026 XX:XX [YOU SHOULD CHANGE THIS LINE TO THE EXACT DATE/TIME NOW]</h4>
            <table>
                <caption>Table:4-No. of Guests 3</caption>
                <thead>
                <tr>
                    <th class="description">Description</th>
                    <th class="quantity">Qty</th>
                </tr>
                </thead>
                
                <tbody>
                    <tr>
            <td class="description" id="total">Total</td>
            <td class="quantity" id="totalqty">0</td>
          </tr>
          <tr>
            <td class="description" id="total">Total</td>
            <td class="quantity" id="totalqty">0</td>
          </tr>
          <tr>
            <td class="description" id="total">Total</td>
            <td class="quantity" id="totalqty">0</td>
          </tr>
                </tbody>
        
                <tfoot>
                <tr>
                    <td class="description" id="total">Total</td>
                    <td class="quantity" id="totalqty">0</td>
                </tr>
                </tfoot>
            </table>
            <a id="undo" href="#">undo</a>
        </div>
    </div>
    
    <!-- Footer -->
    <footer class="block">
        &copy; CityU 2026 - Sources of images and text from official website of Hong Kong Disneyland, Wikipedia and Courtesy of Icon pack by Icons8 - Designed by <a href="../html/design.html">Cheng Ng Jessica</a>.
    </footer>
</body>
</html>
```
- Inside `order.css`, add the following lines to create the **two-column layout**:
```css
.menu {
    width: calc(78% - 50px);
    height: 100%;
    float: left;
}

.ordered_item {
    width: 22%;
    height: 100%;
    float: right;
}
```
- Inside `theme.css`, add the following lines to format and add the required hover effect to the **menu**:
```css
.menu_heading {
    width: calc(33.33% - 9px);
    text-align: center;
    display: inline-block;
    border: 1px solid black;
    padding: 2px;
    margin: 0;
    background-color: lightgray;
    border-radius: 10px 10px 0 0 ;
}

.menu_content {
    display: none;
}

.menu_heading:hover {
    background-color: white;
}

.menu_content:hover,
.menu_heading.ticket:hover ~ .menu_content.ticket,
.menu_heading.dining:hover ~ .menu_content.dining,
.menu_heading.hotel:hover ~ .menu_content.hotel
{
    display: block;
}

.menu_content {
    border: 1px solid black;
}

.menu_content form {
    width: 30%;
    display: inline-block;
    padding: 10px;
}

.menu_content form img {
    float: left;
}
```
- Inside `theme.css`, add the following lines to format the **ordered item table**:
```css
.ordered_item table {
    width: 100%;
}

.ordered_item .description {
    text-align: left;
}

.ordered_item .quantity {
    text-align: right;
}

.ordered_item #undo {
    display: block;
    width: 100%;
    text-align: center;
}
```
-  Inside `theme.css`, add the following lines to change the colour of the table.
```css
.ordered_item table thead
{
    background-color: #ccc;
}

.ordered_item table tfoot
{
    background-color: #ccc;
}

.ordered_item table tbody tr:nth-child(odd) {
    background-color: white;
}

.ordered_item table tbody tr:nth-child(even) {
    background-color: whitesmoke;
}
```
> [!note]
> You may choose your own color here.
> - `.ordered_item table thead` is the first row
> - `.ordered_item table tfoot` is the last row
> - `.ordered_item table tbody tr:nth-child(odd)` is the odd body row (1, 3, 5, ...)
> - `.ordered_item table tbody tr:nth-child(even)` is the even body row (2, 4, 6, ...)
## 4. Home page interaction
Below is the full code of `javascript/homepage.js`:
```js
const message = [
    "DISNEY PREMIER ACCESS & 1-DAY TICKET COMBO, STARTING FROM HK $798",
    "DISNEY PREMIER ACCESS & 8-ATTRACTIONS WITH 1 SHOW, STARTING FROM HK $379",
    "DISNEY PREMIER ACCESS - 1-ATTRACTION, STARTING FROM HK $79"
];

const video = [
    "https://personal.cs.cityu.edu.hk/~cs2204/video/Castle.mp4",
    "https://personal.cs.cityu.edu.hk/~cs2204/video/Musical_Journey.mp4"
];

let message_id = 0;
let video_id = 0;

// Set Promotion Message
function SetMessage(id) {
    document.getElementById("promotion_message").innerHTML = message[id];
}

// Update Promotion Message
function ChangeMessage() {
    if(message_id == 2){
        message_id = 0
    } else {
        message_id++;
    }
    SetMessage(message_id);
}

window.onload = function () {
    // Promotion Message
    message_id = Math.floor(Math.random() * 3);
    SetMessage(message_id);
    // Update every 3 seconds
    setInterval(`ChangeMessage()`, 3000);
    // Chnage Video
    document.getElementById("promotion_video").onended = function() {
        video_id = 1 - video_id;
        this.src = video[video_id];
        this.play();
    };
    // Sumbmit Form
    document.getElementById("booking_submit").onclick = function() {
        let date = document.getElementById("bookdate").value.trim();
        let time = document.getElementById("booktime").value.trim();
        let visitor = document.getElementById("novisitor").value.trim();
        if(date == "" || time == "" || visitor == "") {
            document.querySelector("#warning").style.display="block"; //display the message
        } else {
            document.querySelector("#warning").style.display="none"; //hide the message
            if (reserve(date, time, visitor) == true) {
                alert("Reservation done. Thank you.");
            } else {
                alert("Disneyland has reached the maximum number of visitors for the day");
            }
            event.preventDefault(); // Cancel the form submission
        }
        
    }
}
```
> [!hint]
> This is the best solution for this problem. You may copy the code directly without any plagiarism concerns, since I'll submit a completely different method to solve this problem.
## 5. Order Page Interaction
> [!note] Update
> ***Fixed `order.js` to fulfil requirement 5.1***

Below is the full code of `javascript/order.js`:
```js
items = [];

window.onload = function () {
    let ticket_heading = document.querySelector('.menu_heading.ticket');
    let ticket_content =  document.querySelector('.menu_content.ticket');
    ticket_heading.style.backgroundColor = "white";
    ticket_content.style.display = "block"
    document.querySelectorAll('.menu_heading').forEach(element => {
        element.addEventListener('mouseenter', () => {
            ticket_heading.style = '';
            ticket_content.style = '';
        });
    });

    document.querySelectorAll('.menu input[type="submit"]').forEach(submitButton => {
        submitButton.onclick = function() {
            let desc = this.parentElement.parentElement.querySelector("img").alt;
            let qty = document.getElementById(this.id.slice(0, -7)).value;
            if(qty == '' || parseInt(qty) <= 0) {
                return;
            }
            items.push({
                description: desc,
                quantity: qty
            })
            UpdateTable();
            event.preventDefault(); // Cancel the form submission
        }
    });

    document.getElementById("undo").onclick = function() {
        if(items.length == 0) {
            alert("The table is empty.");
            event.preventDefault();  // Cancel the form submission
            return;
        }
        items.pop();
        UpdateTable();
        event.preventDefault();  // Cancel the form submission
    }
}

function UpdateTable() {
    let tableBody = document.querySelector(".ordered_item table tbody");
    tableBody.innerHTML = "";
    items.forEach(item => {
        let tableRow = document.createElement("tr");
        tableRow.innerHTML = `
            <td class="description">${item.description}</td>
            <td class="quantity">${item.quantity}</td>
        `;
        tableBody.appendChild(tableRow);
    });
    Recal();
}

function Recal() {
    let sum = 0;
    items.forEach(item => {
        sum += parseInt(item.quantity);
    });
    let tableFooter = document.querySelector(".ordered_item table tfoot tr");
    tableFooter.innerHTML = `
        <td class="description">Total</td>
        <td class="quantity">${sum}</td>
    `;
}


```
> [!hint]
> This is the best solution for this problem. You may copy the code directly without any plagiarism concerns, since I'll submit a completely different method to solve this problem.
## 6. Free Design with CSS3
Use **at least two** different CSS3 techniques we covered in the lecture in your web pages,
including but not limited to **gradient colours**, **transitions**, and **animations**.

**You should list what you used in the Design page (“`design.html`”)**

Useful links:
- [Tutorial: CSS Gradient Colours](https://www.w3schools.com/css/css3_gradients.asp)
	- [CSS Gradient Generator](https://cssgradient.io)
- [Tutorial: CSS Transitions](https://www.w3schools.com/css/css3_transitions.asp)
- [Tutorial: CSS Animations](https://www.w3schools.com/css/css3_animations.asp)
	- [CSS Animation Samples](https://prismic.io/blog/css-animation-examples)

Good luck!