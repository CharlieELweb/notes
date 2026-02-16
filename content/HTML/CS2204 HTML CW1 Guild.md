---
title: CS2204 HTML CW1 Guild
draft: false
tags:
---
***Update:** 15 Feb 2026, fixed `index.html` relative path.*

---

> **Due Date:** 23 Feb 2026, **Monday**, 23:59 PM<br>
> **Deliverable:** Compress the root folder into a `zip` file.
## 1.  Requirements of Structure
![[HTML_CW1.png]]

***After this step, your folder should looks like this:***

> [!abstract]+ **ChengNg_Jessica_CW1**
> - **index.html** *(created by your own)*
> 
> > [!example]+ **html**
> > - **order.html** *(created by your own)*
> > - **design.html** *(created by your own)*
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
> > 
> > *(Total 12 images, download from Canvas)*
>
> > [!example]+ **css**
> > - **theme.css** _(created by your own)_
>
> > [!example]+ **javascript**
> > *(leave the folder empty for CW1)*
> 

> [!note]
> When you download the image from canvas, the original folder name is `images` with **s**. Remember to **rename** it to `image` without **s**, as the requirement says.
### Preparation
Let's prepare the basic structure of the html files. You may copy this structure to all 3 html files (`index.html`, `order.html`, `design.html`).
> [!info]
> You may quickly copy all the code of a block from this website, by clicking the code block, and the click the icon on the top-right conner.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Disneyland</title>
    <link rel="stylesheet" href="../css/theme.css" media="screen" type="text/css">
</head>
<body>
    [Write your webstie body here...]
</body>
</html>
```

> [!hint]
>  Here, `<title>Disneyland</title>` set the title of each page. You may change the title for different pages to distinguish them. For example: **Order | Disneyland**.
>  
>  Also,`<link rel="stylesheet" href="../css/theme.css" media="screen" type="text/css">` links the `theme.css` file to the html file, which corresponds to **step 6** in the requirements. Check the file name and `href` address if error occurs.

> [!caution]
> For `index.html`, the relative `href` path of `link` shoud be `"./css/theme.css"`, one dot instead of two dots, because it's inside the root folder!
## 2.  Common Information
These elements should be copied and pasted to all 3 html files (`index.html`, `order.html`, `design.html`) after competed.
> [!note]
> For the following code provided, the `class` attributes' value is just as a reference, these values are useful for css selectors.
> 
> You may add the `class` attribute to any of the tag if necessary, or change the value in your preference.
### 2.1 Header/Banner Block
> A header/banner block consists of a **logo** (could be designed by you or use the provided image) and **heading** of the Web site; these are **separated**, should not be done in one single image.

- We use `img` for the logo image, and `<h1>` for the heading.
- The `alt` attributes of `img` is for the accessibility functions, like screen readers for visually impaired users.
- Although haven't mentioned in the requirement, but from the screenshot it provided, we should add another `welcome` text in the header. We wrap it into a division block `<div>`, convenience us to select this element for css.

```html
<!-- Header -->
<header>
	<img src="../image/logo.png" alt="Disneyland Logo" id="logo">
	<h1>DisneyLand</h1>
	<div class="welcome">Welcome</div>
</header>
```
> [!caution]
> For `index.html`, the relative `src` path of `img` shoud be `"./image/logo.png"`, one dot instead of two dots, because it's inside the root folder!
### 2.2 Footer
> A footer with information about the copyright and a link pointing to the Design page
“@CityU 2024 – sources of images and text from official website of Hong Kong Disneyland,
Wikipedia and Courtesy of Icon pack by Icons8 – designed by [Your name] **name including a**
**link the Design page**”

- According to the screenshot, we correct the provided text by changing the year to 2026, and use escape code `&copy;` to represent copyright icon, instead of `@`.
- We use `<a>` to link your name to the design page.

```html
<!-- Footer -->
<footer>
	&copy; CityU 2026 - Sources of images and text from official website of Hong Kong Disneyland, Wikipedia and Courtesy of Icon pack by Icons8 - Designed by <a href="../html/design.html">Cheng Ng Jessica</a>.
</footer>
```

>[!hint]
>Here, you should enter the design page by clicking your name. Check the `href` address if error occurs.

> [!caution]
> For `index.html`, the relative `href` path of `a` shoud be `"./html/design.html"`, one dot instead of two dots, because it's inside the root folder!

## 3. Home Page (`index.html`)
### 3.1 Common Information
> **the common information** specified in Section 2.

- Copy the header and footer of **2.1** and **2.2**.

> [!hint]
> Header should be put at the top of body section, footer should be put at the end of body section. 
> 
> I.e. You should add more blocks between the two blocks.

### 3.2 Basic Information Block
> the basic information block contains 5 types of information as shown in the screen shot: address, telephone, business hours, brief introduction, and location (an image, not an embedded Google Map); use the **most structured** elements to present such information. At the end, there is an **image link** pointing to the Order page (“order.html”).

- The most structured elements here is [Description Lists](https://www.w3schools.com/html/html_lists_other.asp)(`<dl>`). We put each of the information type (e.g. address) to the data term (`<dt>`) and the details to the data description (`<dd>`).
- For the data of **location** information, the description should be a `<a>` tag nested with an `<img>` tag, links to the order page.
- We also adds the `alt` value for each images.
- Although haven't mentioned in the requirement, but from the screenshot it provided, we should add another `booking_button` image also link to the order page.

```html
<!-- Basic Information Blcok -->
<div class="info block">
	<dl>
		<dt>Address</dt>
			<dd>
				Hong Kong's Disneyland Resort,<br>
				Penny's Bay, Lantau Island,<br>
				Hong Kong
			</dd>
		<dt>Tel</dt>
			<dd>
				+852 1-830-830
			</dd>
		<dt>Business Hours</dt>
			<dd>
				10:30 AM - 8:30 PM
			</dd>
		<dt>Brief Introduction</dt>
			<dd>
				Enter a magical kingdom inspired by fairy-tale dreams and explore 7 lands - Adventureland, Grizzly Gulch, Mystic Point, Toy Story Land, Fantasyland, Tommorrowland and Main Street, USA - filled with beauty, excitement and Disney Characters.
			</dd>
		<dt>Location</dt>
			<dd>
				<a href="./html/order.html"><img src="./image/location.jpg" alt="Map of Disneyland Resort"></a>
			</dd>
	</dl>
	<a href="./html/order.html" class="booking_button"><img src="./image/button.jpg"></a>
</div>
```
### 3.3 Promotion Information Block
> [!error] Typo
> The requirement pdf wrongly assign this section to 3.2.

> the promotion information block contains a text passage for promotion of Disney Premier
Access, followed by a video which plays **automatically** (note: check out the autoplay policy
for browsers) and **continuously**

- We use `<h3>` for the promotion text passage.

- We use `<video>` to display the promotion video. As required, we should provide all the available `source` format `.mp4` and `.ogg`, with an error message if not loaded.
- We use `autoplay` attribute to let the video plays automatically. We use `loop` attribute to let the video plays continuously.
- Optionally, we may use `controls` and `mute` attribute to let the user controls the video process and mute the music by default.

```html
<!-- Promotion Information Block -->
<div class="promotion_information block">
	<h3>DISNEY PREMIER ACCESS & 1-DAY TICKET COMBO, STARTING FROM HK $798</h3>
	<video controls autoplay muted loop>
		<source src="https://personal.cs.cityu.edu.hk/~cs2204/video/Castle.mp4" type="video/mp4">
		<source src="https://personal.cs.cityu.edu.hk/~cs2204/video/Castle.ogg" type="video/ogg">
		Your browser does not support this video of Disneyland.
	</video>
</div>
```

### 3.4 Booking Block
> [!error] Typo
> The requirement pdf wrongly assign this section to 3.3.

> the booking block is a form as shown (the form can be submitted to any dummy internal
location in CW1, e.g., “#”). The exact number of time slots is not required. You can design 5 ~
6 reasonable time slots.
- The form is submitted(`action`) to the dummy internal location (i.e. `#`). The `method` of `post` or `get` are both fine.
- We use `<fieldset>` to create the outline of the form section.
- We use `<legend>` for the title of the form section.
- For each form input section, we use `<label>` to show the title, and `<input>` for the box.
> [!Note]
> The `for` attribute of `<label>` should be the same as `id` attribute of corresponding `<input>`. To test this, you should able to focus on the input boxes when clicking the corresponding label text.
>
> As for the `name` attribute of `<input>`, this is the name to be sent when submitting the form, which could be any value. We use the same value as `id` here to prevent any errors.
> 
> Here, we also use the `required` attribute to validate the input, prevent invalid errors.
- The time slots could be represented by `<select>` and `<option>`.
> [!Note]
> The `value` of option is the actual string passed to the form, and the actual content between `<option>xxx</option>`tag is the content shown in the website.
>
> You may change or made up 5-6 time slots by your own.
- For the two operation buttons to submit and reset the form, we use the special `type` of `input`, `submit` and `reset`. The `value` attributes can control the text to display on the button.
```html
<!-- Booking Block -->
<div class="booking block">
	<form action="#" method="post">
		<fieldset>
			<legend>Booking Information</legend>
			<div class="booking_item">
				<label for="bookdate">Date:</label>
				<input type="date" name="bookdate" id="bookdate" required>
			</div>
			<div class="booking_item">
				<label for="booktime">Time:</label>
				<select name="booktime" id="booktime" required>
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
				<input type="number" name="novisitor" value="" id="novisitor" min="0" required>
			</div>
			<div class="booking_operation">
				<input type="submit" value="Check Availability">
				<input type="reset" value="Reset">
			</div>
		</fieldset>
	</form>
</div>
```


### Home Page Full Code

The full structure of the `index.html` should looks like this:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Disneyland</title>
    <link rel="stylesheet" href="./css/theme.css" media="screen" type="text/css">
</head>
<body>
    <!-- Header -->
    <header>
        <img src="./image/logo.png" alt="Disneyland Logo" id="logo">
        <h1>DisneyLand</h1>
        <div class="welcome">Welcome</div>
    </header>

    <!-- Basic Information Blcok -->
	<div class="info block">
		<dl>
			<dt>Address</dt>
				<dd>
					Hong Kong's Disneyland Resort,<br>
					Penny's Bay, Lantau Island,<br>
					Hong Kong
				</dd>
			<dt>Tel</dt>
				<dd>
					+852 1-830-830
				</dd>
			<dt>Business Hours</dt>
				<dd>
					10:30 AM - 8:30 PM
				</dd>
			<dt>Brief Introduction</dt>
				<dd>
					Enter a magical kingdom inspired by fairy-tale dreams and explore 7 lands - Adventureland, Grizzly Gulch, Mystic Point, Toy Story Land, Fantasyland, Tommorrowland and Main Street, USA - filled with beauty, excitement and Disney Characters.
				</dd>
			<dt>Location</dt>
				<dd>
					<a href="./html/order.html"><img src="./image/location.jpg" alt="Map of Disneyland Resort"></a>
				</dd>
		</dl>
		<a href="./html/order.html" class="booking_button"><img src="./image/button.jpg"></a>
	</div>

    <!-- Promotion Information Block -->
    <div class="promotion_information block">
        <h3>DISNEY PREMIER ACCESS & 1-DAY TICKET COMBO, STARTING FROM HK $798</h3>
        <video controls autoplay muted loop>
            <source src="https://personal.cs.cityu.edu.hk/~cs2204/video/Castle.mp4" type="video/mp4">
            <source src="https://personal.cs.cityu.edu.hk/~cs2204/video/Castle.ogg" type="video/ogg">
            Your browser does not support this video of Disneyland.
        </video>
    </div>

    <!-- Booking Block -->
    <div class="booking block">
        <form action="#" method="post">
            <fieldset>
                <legend>Booking Information</legend>
                <div class="booking_item">
                    <label for="bookdate">Date:</label>
                    <input type="date" name="bookdate" id="bookdate" required>
                </div>
                <div class="booking_item">
                    <label for="booktime">Time:</label>
                    <select name="booktime" id="booktime" required>
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
                    <input type="number" name="novisitor" value="" id="novisitor" min="0" required>
                </div>
                <div class="booking_operation">
                    <input type="submit" value="Check Availability">
                    <input type="reset" value="Reset">
                </div>
            </fieldset>
        </form>
    </div>


    <!-- Footer -->
    <footer>
        &copy; CityU 2026 - Sources of images and text from official website of Hong Kong Disneyland, Wikipedia and Courtesy of Icon pack by Icons8 - Designed by <a href="./html/design.html">Cheng Ng Jessica</a>.
    </footer>

</body>
</html>
```
## 4. Order Page (`order.html`)
### 4.1 Common Information
> **the common information** specified in Section 2.

- Copy the header and footer of **2.1** and **2.2**. Again, you should add more blocks between the two blocks.

### 4.2 Menu Block
> The menu block for showing the tickets and additional offers provided by Disneyland for
ordering; it has a **heading** “Menu” followed by 3 **smaller headings** with names (one
example is Tickets, Dining and Hotel, you may choose your own offers)

- We use `<h2>` for the Menu heading, and `<h3>` for the smaller headings.
- Here, we adds a `selected` class to one of the smaller headings, making it easier to implement tab function in the CW2.
```html
<h2>Menu</h2>
<h3 class="selected">Tickets</h3>
<h3>Dinings</h3>
<h3>Hotels</h3>
```
> **Design 9 forms** where each form is for one menu item. Each menu item consists of a photo, a text label, a box to fill in the quantity and a button labelled “Add”.
> - Group these forms into three groups using `<div>` and each group is for one offer tab, e.g., Tickets, Dining and Hotel.
> - The first offer contains 3 menu items, while the second and the last ones contain 2
and 4 menu items [hint: for these items, you must build up the structures as described above, i.e., the overall block, offer tabs and menu items are all structural units]

- For each form, we use `<img>` for image, `<label>` for text label, `<input>` with `type` of `number` for box to fill the quantity, and `<input>` of special `type` of `sumbmit` to post the form. We may change `value` attribute of `<input>` to "Add" to change the text to display in the button.
```html
<form action="#" method="post" id="ticket1">
	<img src="../image/ticket-1.jpeg" alt="1-Day Ticket">
	<label for="ticket1">1-Day Ticket</label>
	<div class="menu_operation">
		<input type="number" name="ticket1" id="ticket1" min="1" required>
		<input type="submit" id="ticket1_sumbit" value="Add">
	</div>
</form>
```
> [!Note]
> Again, The `for` attribute of `<label>` should be the same as `id` attribute of corresponding `<input>`.
> We add the attribute `min="1"` to make sure the quantity is none-zero positive number. We also use the `required` attribute to prevent any empty submissions.

- Then, duplicate the form 8 more times and change each of the `id`, `name` with a unique value. We also need to use division `<div>` to group each offer.
> [!hint]
> This process is boring and annoying, you may just copy the code below.

So this is the full code for the **4.2 Menu Block**:

```html
<!-- Menu Block -->
<div class="menu block">
	<h2>Menu</h2>
	<h3 class="selected">Tickets</h3>
	<h3>Dinings</h3>
	<h3>Hotels</h3>
	<div class="menu_content">
		<div class="ticket">
			<form action="#" method="post" id="ticket1">
				<img src="../image/ticket-1.jpeg" alt="1-Day Ticket">
				<label for="ticket1">1-Day Ticket</label>
				<div class="menu_operation">
					<input type="number" name="ticket1" id="ticket1" min="1" required>
					<input type="submit" id="ticket1_sumbit" value="Add">
				</div>
			</form>
			<form action="#" method="post" id="ticket2">
				<img src="../image/ticket-2.jpeg" alt="1-Day Ticket (Child)">
				<label for="ticket1">1-Day Ticket (Child)</label>
				<div class="menu_operation">
					<input type="number" name="ticket2" id="ticket2" min="1" required>
					<input type="submit" id="ticket2_sumbit" value="Add">
				</div>
			</form>
			<form action="#" method="post" id="ticket3">
				<img src="../image/ticket-3.jpeg" alt="2-Day Ticket">
				<label for="ticket3">2-Day Ticket</label>
				<div class="menu_operation">
					<input type="number" name="ticket3" id="ticket3" min="1" required>
					<input type="submit" id="ticket3_sumbit" value="Add">
				</div>
			</form>
		</div>
		<div class="dining">
			<form action="#" method="post" id="dining1">
				<img src="../image/dining-1.jpeg" alt="Explorer's Semi Buffet">
				<label for="dining1">Explorer's Semi Buffet</label>
				<div class="menu_operation">
					<input type="number" name="dining1" id="dining1" min="1" required>
					<input type="submit" id="dining1_sumbit" value="Add">
				</div>
			</form>
			<form action="#" method="post" id="dining2">
				<img src="../image/dining-2.jpeg" alt="3-in-1 Park Meal Voucher">
				<label for="dining1">3-in-1 Park Meal Voucher</label>
				<div class="menu_operation">
					<input type="number" name="dining2" id="dining2" min="1" required>
					<input type="submit" id="dining2_sumbit" value="Add">
				</div>
			</form>
		</div>
		<div class="hotel">
			<form action="#" method="post" id="hotel1">
				<img src="../image/hotel-1.jpeg" alt="Standard Room">
				<label for="hotel1">Standard Room</label>
				<div class="menu_operation">
					<input type="number" name="hotel1" id="hotel1" min="1" required>
					<input type="submit" id="hotel1_sumbit" value="Add">
				</div>
				
			</form>
			<form action="#" method="post" id="hotel2">
				<img src="../image/hotel-2.jpeg" alt="Deluxe Room">
				<label for="hotel1">Deluxe Room</label>
				<div class="menu_operation">
					<input type="number" name="hotel2" id="hotel2" min="1" required>
					<input type="submit" id="hotel2_sumbit" value="Add">
				</div>
			</form>
			<form action="#" method="post" id="hotel3">
				<img src="../image/hotel-3.jpeg" alt="Sea View Room">
				<label for="hotel3">Sea View Room</label>
				<div class="menu_operation">
					<input type="number" name="hotel3" id="hotel3" min="1" required>
					<input type="submit" id="hotel3_sumbit" value="Add">
				</div>
			</form>
			<form action="#" method="post" id="hotel4">
				<img src="../image/hotel-4.jpeg" alt="Kingdom Club Room">
				<label for="hotel4">Kingdom Club Room</label>
				<div class="menu_operation">
					<input type="number" name="hotel4" id="hotel4" min="1" required>
					<input type="submit" id="hotel4_sumbit" value="Add">
				</div>
			</form>
		</div>
	</div>
</div>
```
### 4.3 Ordered Item Block
> Ordered Item block with a **heading** and **date time information** (the date and time when
you solve this problem)
> - The table contains the table caption, table header, table body and table footer. Table
body is empty in CW1
> - At the bottom of this block, there is a link labelled “undo”; it could be set as a
dummy link, which will be useful in CW2

- We use `<h2>` for heading, and `<h4>` for date time information.
- We use `<table>` to create a table, `<caption>` for table caption. `<thead>` `<tbody>` `<tfoot>` for 3 section of the table. `<tr>` for table row, `<th>` for table heading cells, and `<dt>` for table data cells.
- The table body remains empty for CW1.
- At the bottom, we use `<a>` link for undo. The `href` of the link could be a dummy link (i.e. `#`)
```html
<!-- Ordered Item Block -->
<div class="ordered_item block">
	<h2>Ordered Items</h2>
	<h4>XX Feb 2026 XX:XX [YOU SHOULD CHANGE THIS LINE TO THE EXACT DATE/TIME NOW]</h4>
	<table>
		<caption>Table:4-No. of Guests 3</caption>
		<thead>
		<tr>
			<th>Description</th>
			<th>Qty</th>
		</tr>
		</thead>
		
		<tbody>
			<!-- Table Body -->
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
```
### Order Page Full Code

The full structure of the `order.html` should looks like this:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Order | Disneyland</title>
    <link rel="stylesheet" href="../css/theme.css" media="screen" type="text/css">
</head>
<body>
    <!-- Header -->
    <header>
        <img src="../image/logo.png" alt="Disneyland Logo" id="logo">
        <h1>DisneyLand</h1>
        <div class="welcome">Welcome</div>
    </header>
    <!-- Menu Block -->
    <div class="menu block">
        <h2>Menu</h2>
        <h3 class="selected">Tickets</h3>
        <h3>Dinings</h3>
        <h3>Hotels</h3>
        <div class="menu_content">
            <div class="ticket">
                <form action="#" method="post" id="ticket1">
                    <img src="../image/ticket-1.jpeg" alt="1-Day Ticket">
                    <label for="ticket1">1-Day Ticket</label>
                    <div class="menu_operation">
                        <input type="number" name="ticket1" id="ticket1" min="1" required>
                        <input type="submit" id="ticket1_sumbit" value="Add">
                    </div>
                </form>
                <form action="#" method="post" id="ticket2">
                    <img src="../image/ticket-2.jpeg" alt="1-Day Ticket (Child)">
                    <label for="ticket1">1-Day Ticket (Child)</label>
                    <div class="menu_operation">
                        <input type="number" name="ticket2" id="ticket2" min="1" required>
                        <input type="submit" id="ticket2_sumbit" value="Add">
                    </div>
                </form>
                <form action="#" method="post" id="ticket3">
                    <img src="../image/ticket-3.jpeg" alt="2-Day Ticket">
                    <label for="ticket3">2-Day Ticket</label>
                    <div class="menu_operation">
                        <input type="number" name="ticket3" id="ticket3" min="1" required>
                        <input type="submit" id="ticket3_sumbit" value="Add">
                    </div>
                </form>
            </div>
            <div class="dining">
                <form action="#" method="post" id="dining1">
                    <img src="../image/dining-1.jpeg" alt="Explorer's Semi Buffet">
                    <label for="dining1">Explorer's Semi Buffet</label>
                    <div class="menu_operation">
                        <input type="number" name="dining1" id="dining1" min="1" required>
                        <input type="submit" id="dining1_sumbit" value="Add">
                    </div>
                </form>
                <form action="#" method="post" id="dining2">
                    <img src="../image/dining-2.jpeg" alt="3-in-1 Park Meal Voucher">
                    <label for="dining1">3-in-1 Park Meal Voucher</label>
                    <div class="menu_operation">
                        <input type="number" name="dining2" id="dining2" min="1" required>
                        <input type="submit" id="dining2_sumbit" value="Add">
                    </div>
                </form>
            </div>
            <div class="hotel">
                <form action="#" method="post" id="hotel1">
                    <img src="../image/hotel-1.jpeg" alt="Standard Room">
                    <label for="hotel1">Standard Room</label>
                    <div class="menu_operation">
                        <input type="number" name="hotel1" id="hotel1" min="1" required>
                        <input type="submit" id="hotel1_sumbit" value="Add">
                    </div>
                    
                </form>
                <form action="#" method="post" id="hotel2">
                    <img src="../image/hotel-2.jpeg" alt="Deluxe Room">
                    <label for="hotel1">Deluxe Room</label>
                    <div class="menu_operation">
                        <input type="number" name="hotel2" id="hotel2" min="1" required>
                        <input type="submit" id="hotel2_sumbit" value="Add">
                    </div>
                </form>
                <form action="#" method="post" id="hotel3">
                    <img src="../image/hotel-3.jpeg" alt="Sea View Room">
                    <label for="hotel3">Sea View Room</label>
                    <div class="menu_operation">
                        <input type="number" name="hotel3" id="hotel3" min="1" required>
                        <input type="submit" id="hotel3_sumbit" value="Add">
                    </div>
                </form>
                <form action="#" method="post" id="hotel4">
                    <img src="../image/hotel-4.jpeg" alt="Kingdom Club Room">
                    <label for="hotel4">Kingdom Club Room</label>
                    <div class="menu_operation">
                        <input type="number" name="hotel4" id="hotel4" min="1" required>
                        <input type="submit" id="hotel4_sumbit" value="Add">
                    </div>
                </form>
            </div>
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
                <th>Description</th>
                <th>Qty</th>
            </tr>
            </thead>
            
            <tbody>
                <!-- Table Body -->
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
    <!-- Footer -->
    <footer>
        &copy; CityU 2026 - Sources of images and text from official website of Hong Kong Disneyland, Wikipedia and Courtesy of Icon pack by Icons8 - Designed by <a href="../html/design.html">Cheng Ng Jessica</a>.
    </footer>
</body>
</html>
```
## 5. Design Page (`design.html`)
In this page, except the common header and footer copied of **2.1** and **2.2**, we should declare the css selector we used for the website (*will be covered in section 6*) and any reference from the Internet.
Here's an example of the design page. But you may also change the structure by your own using other visual elements like [Table](https://www.w3schools.com/html/html_tables.asp).
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Design | Disneyland</title>
    <link rel="stylesheet" href="../css/theme.css" media="screen" type="text/css">
</head>
<body>
    <!-- Header -->
    <header>
        <img src="../image/logo.png" alt="Disneyland Logo" id="logo">
        <h1>DisneyLand</h1>
        <div class="welcome">Welcome</div>
    </header>
    
    <h2>Design Page</h2>
    <h3>CSS selector:</h3>
    <ul>
        <li>
            <b>Tag Selector(s): </b><br>
            h1 (color: blue, font-size:20px),<br>
            ...
        </li>
        <li>
            <b>Class Selector(s): </b><br>
            .welcome (color: blue, font-size:20px),<br>
            ...
        </li>
        <li>
            <b>Id Selector(s): </b><br>
            #logo (width: 100px, height: 100px),<br>
            ...
        </li>
        <li>
            <b>Contextual Selector(s): </b><br>
            .info dt (color: blue, font-size:20px),<br>
            .menu h3.selected (color: blue, font-size:20px),<br>
            ...
        </li>
        <li>
            <b>Advanced Selector(s): </b><br>
            a:hover (color: blue, font-size:20px),<br>
            input[type="submit"] (color: blue, font-size:20px),<br>
            ...
        </li>
    </ul>
    <h3>Additional Source Cited:</h3>
    <ul>
        <li>
            <b>Logo: </b>
            <a href="https://icons8.com/icons/set/disneyland-pari">
                https://icons8.com/icons/set/disneyland-pari
            </a>
        </li>
        <li>
            <b>Fonts: </b>
            <a href="https://fonts.google.com">
                https://fonts.google.com
            </a>
        </li>
    </ul>
    <h3>Name: CHENG NG Jessica</h3>
    <h3>SID: 59284858</h3>
    <!-- Footer -->
    <footer>
        &copy; CityU 2026 - Sources of images and text from official website of Hong Kong Disneyland, Wikipedia and Courtesy of Icon pack by Icons8 - Designed by <a href="../html/design.html">Cheng Ng Jessica</a>.
    </footer>
</body>
</html>
```
## 6. Website styling and accessibility (`theme.css`)
Now, here's where the creativity flies! We've already linked the `theme.css` to all three pages. So we can directly edit the css code inside the `theme.css`.

### CSS selectors
As required, we should involve:
-  At least one element (**tag**) selector, one **class** selector (for multiple elements),
and one **id** selector
- At least one **contextual** selector (e.g., descendent selector, child selector)
**OR** one **advanced** selector (e.g., pseudo class, pseudo element)

Heres some example for different selector that could be used in our website:

| Selector Type       | Example                                                                                           |
| ------------------- | ------------------------------------------------------------------------------------------------- |
| Tag Selector        | `body`<br>`header`<br>`footer`<br>`h2`<br>`img`<br>`video`                                        |
| Class Selector      | `.block`                                                                                          |
| ID Selector         | `#logo`                                                                                           |
| Contextual Selector | `.info dt`<br>`.menu_content>div`<br>`.menu h3.selected`                                          |
| Advanced Selector   | `a:hover`<br>`input[type="submit"], .booking input[type="reset"]`<br>`input[type="submit"]:hover` |

Next, for each selector, you may change the style using different parameters. Like `color`, `background-color`, `font-size`, `font-weight`, `text-decoration`, `border`, `border-radius`, `text-align`, `padding`, `margin`, etc.

Mind that **anything related to CSS layout, CSS animation, or JavaScript are NOT required in CW1.** This means some css parameter like `display:flex;`, `flex-direction`, `transition`, `animation` are not required. But you may use them if you really have time.

### Advanced Tips
To make the website looks consistent, one of the important thing to do is use as little as colour possible. In other words, use a colour palette.

In CSS code, to use the same colour for different elements, we could define some colour variable with the any(`*`) selector like this:
```css
* {
    --primary-purple: #9d52ff;
    --secondary-purple: #f174ff;
    --primary-blue: #00a2ff;
    --secondary-blue: #bcefff;
    --white: #ffffff;
    --black: #1e1e1e;
    --light-gray: #cccccc;
    --dark-gray: #999999;
}
```
Then, to use the colour, instead using Hexadecimal colour code like `#9d52ff`, we can use the `var(--primary-purple)` instead. Like this:

```css
a {
    color: var(--primary-purple);
    text-decoration: none;
}
input[type="submit"] {
    border: var(--primary-purple) solid 1px;
    background-color: var(--white);
    color: var(--primary-purple);
    font-weight: 600;
}
```
In this way, if we want to use a different colour palette, we could simply change the colour code in the any (`*`) sector, instead of surfing the codes and replace each individual elements.

For details off `var()` function, you may take a reference from this [link](https://www.w3schools.com/css/css3_variables.asp)
## Useful links
Heres some useful links to find colours, fonts, and css tutorials:
- Find color palettes: [Color Hunt](https://colorhunt.co)
- Find and use different fonts: [Google Fonts](https://fonts.google.com)
- Find different icons/logos: [Icon8](https://icons8.com/icons)
- CSS tutorial website: [W3 Schools](https://www.w3schools.com/css/css_colors.asp)
- Hong Kong Disneyland website: [Hong Kong Disneyland](https://www.hongkongdisneyland.com)
- California USA Disneyland webstie: [CA Disneyland](https://disneyland.disney.go.com/destinations/disneyland/)
