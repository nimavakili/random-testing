List of current step structures for Behat/Mink
----------------------------------------------

	*	All the following structures should start with one of these words: Given, When, And, But, Then
	*	For Behat it doesn't matter which starting word you use, choose one that makes more sense
	*	Brackets ([]) in a structure means that part is optional


	1.	I reload the page


	2.	I move backward one page


	3.	I move forward one page


	4.	I set [the] authentication username "USER" and password "PASS"

		Sets the username and password to be used in the following steps that require authentication
		USER:
			Username
		PASS:
			Password
		Example:
			Given I set the authentication username "autotester" and password "somepassword"


	5.	I am on "PAGE"
   		I go to "PAGE" [providing authentication]

   		Opens specified page.
   		'providing authentication' requires you to set the username and password in a previous step
   		PAGE:
   			URL of the page (it should start with http or https)
   			The URL can be relative to the base URL you set in the config file
   			You can use 'homepage' or 'the homepage' without quotaion marks for going to the base URL set in the config file
   		Example:
   			And I go to "http://www.google.com"
   			Given I am on "/login"
   			Given I go to the homepage
   			And I go to "/archive" providing authentication


   	6.	I am on any page

   		If current page url doesn't start with the base URL set in the config file then it will open homepage
   		Example:
   			Given I am on any page


   	7.	I should be on "PAGE"

   		Checks, that current page URL is equal to specified.
   		PAGE:
   			URL of the page (it should start with http or https)
   			The URL can be relative to the base URL you set in the config file
   			You can use 'homepage' or 'the homepage' without quotaion marks
		Example:
			Then I should be on "https://images.google.com"
			And I should be on "/history"
			But I should be on the homepage


   	8.	I follow "LINK"

   		Clicks specified link.
   		It will complain if the link is not visible.
   		LINK:
   			Id or title or alt or text of the link
   		Example:
   			When I follow "Contact Us"


	9.	the response status code should [not] be NUM

		Checks, that current page response status is equal or is not equal to specified.
		NUM:
			HTTP response code
		Example:
			And the response status code should be 200
			Then the response status code should not be 401


 	10.	I should see the browser title is "TITLE"

 		Checks, that the browser (page) title matches the given title.
 		TITLE:
 			Title to be checked against
 		Example:
 			And I should see the browser title is "Contact Us"


   	11.	I should [not] see "TEXT"

   		Checks, that page contains or doesn't contain the specified text.
   		TEXT:
   			Text that the page should contain
   			Case sensitive
   		Example:
   			Then I should see "Welcome to the Machine!"
   			But I should not see "could not be found"


   	12.	I should see the TAG "TEXT" [in "ID"] with the ATTRIBUTE "VALUE"
   		I should see a/an TAG [in "ID"] with the ATTRIBUTE "VALUE"

   		Checks, that page or the element with specified ID contains the element with specified tag, attribute value and optional text
   		TAG:
   			Html tag of the element you're looking for
 			It's possible to use these words:
 				'link' instead of 'a'
 				'image' instead of 'img'
 				'paragraph' instead of 'p'
 				'division' instead of 'div'
 		TEXT:
 			The text that the element you're looking for should contain
 			Not case sensitive
 		ID:
 			Id of the parent element
 			Doesn't need to be a direct parent
 		ATTRIBUTE:
 			Name of the attribute you want to check its value
 			It's possible to use these words:
 				'url' instead of 'href'
 				'source' instead of 'src'
 			If the attribute is a url, it can be relative to the base URL set in the config file
 		VALUE:
 			Value of the attribute
 		Example:
 			Then I should see the link "Archive" in "site-nav" with the url "/archive"
 			And I should see an image with the source "/resources/banner.jpg"
 			And I should see a division in "site-nav" with the class "search"


 	14.	I should [not] see a/an "SELECTOR" element

 		Checks, that element with specified CSS selector exists or doesn't exist on page.
 		SELECTOR:
 			CSS selector
 		Example:
 			And I should see a "div.new-user#popup" element
 			But I should not see an "a#response" element


 	15.	I should [not] see "TEXT" in the "SELECTOR" element

 		Checks, that element with specified CSS selector contains or doesn't contain specified text.
 		TEXT:
 			The text that the element you're looking for should or should not contain
 			Case sensitive
 		SELECTOR:
 			CSS selector
 		Example:
 			And I should see "Welcome to the Machine!" in the "div.new-user#popup" element
 			But I should not see "Invalid username or password" in the "p#response" element


	16.	I should see NUM TAG [in "ID"]

		Checks, that the page or element with specified ID has specified number of elements with the given tag
		NUM:
			Number of the elements that should exist
		TAG:
   			html tag of the element(s) you're looking for
   			It can be plural
 			It's possible to use these words:
 				'link' instead of 'a'
 				'image' instead of 'img'
 				'paragraph' instead of 'p'
 				'division' instead of 'div'
		ID:
 			id of the parent element
 			Doesn't need to be a direct parent
 		Example:
 			And I should see 4 images in "page-footer"
 			Then I should see 2 sections


 	17.	I should see NUM "SELECTOR" elements

 		Checks, that specified number of elements with given CSS selector exist on the page
 		NUM:
			Number of the elements that should exist
 		SELECTOR:
 			CSS selector
 		Example:
			And I should see 4 "img#page-footer" elements
			Then I should see 2 "section" elements


 	18.	I move the mouse over the TAG "TEXT" in "ID"
		I move the mouse over "ID"

		Simluates moving the mouse pointer to the specified element.
   		TAG:
   			Html tag of the element you're looking for
 			It's possible to use these words:
 				'link' instead of 'a'
 				'image' instead of 'img'
 				'paragraph' instead of 'p'
 				'division' instead of 'div'
 		TEXT:
 			The text that the element you're looking for should contain
 			Not case sensitive
 		ID:
 			Id of the parent element or the element you're looking
 			Doesn't need to be a direct parent
 		Example:
 			When I move the mouse over the link "Archive" in "site-nav"
 			And I move the mouse over "sing-out"


	19.	I scroll the TAG "TEXT" in "ID" into view
		I scroll "ID" into view

		Scrolls the page so that the specified element is visible in the window frame
   		TAG:
   			Html tag of the element you're looking for
 			It's possible to use these words:
 				'link' instead of 'a'
 				'image' instead of 'img'
 				'paragraph' instead of 'p'
 				'division' instead of 'div'
 		TEXT:
 			The text that the element you're looking for should contain
 			Not case sensitive
 		ID:
 			Id of the parent element or the element you're looking
 			Doesn't need to be a direct parent
 		Example:
 			When I scroll the link "Archive" in "site-nav" into view
 			And I scroll "sign-out" into view


   	20.	I fill in "FIELD" with "VALUE"
   		I fill in "VALUE" for "FIELD"

   		Fills in specified form field with specified value.
   		FIELD:
   			Id or name or label or value of the form field
   		VALUE:
   			Value to fill the field with
   		Example:
   			Given I fill in "name" with "Testing User"
   			And I fill in "Autotester" for "pass"


   	21.	I press "BUTTON"

   		Presses specified button.
   		BUTTON:
   			Id or name or title or alt or value of the button
   		Example:
   			When I press "Login"


 	22.	I set the browser window size to WIDTH by HEIGHT

 		Sets the browser window size to the specified width and height
 		WIDTH:
 			Desirable width in pixels or percentage of the screen
 		HEIGHT:
 			Desirable height in pixels or percentage of the screen
 		Example:
 			Given I set the browser window size to 1024 by 768
 			When I set the browser window size to 1200 by %100


 	23.	the width of "ID" should be WIDTH
 		the height of "ID" should be HEIGHT

 		Checks, that the width or height of the element with specified ID matches the given width or height
 		WIDTH:
 			Width in pixels or percentage of body width to be checked against
 		HEIGHT:
 			Height in pixels or percentage of body height to be checked against
 			Using percentage for height doesn't make much sense and is not recommended
 		Example:
 			Then the width of "slideshow" should be %100
 			And the height of "logo" should be 200


 	24.	I take a picture of the page named "FILENAME"

 		Takes a picture of the current page and saves it as png file.
 		FILENAME:
 			Name of the file
 			All the files will be placed in a folder called screenshots in the working directory of Behat
 		Example:
 			Then I take a picture of the page named "homepage.png"


 	25.	the page should have been loaded in less than NUM seconds

 		Checks, that the current page has been loaded in less than given threshold or not.
 		This step only calulates the total load time and doesn't provide more details.
 		If you need to analyze the performance of a page in detail you can use the structures below.
 		NUM:
 			Number of seconds for the threshold
 		Example:
 			Then the page should have been loaded in less than 4 seconds


 	Detailed performance testing structures


 	15.	I turn metrics monitoring on "URL"

 		Connects to BrowserMob Proxy on the given url, starts a proxy listener and sets the browser to tunnel through that proxy.
 		Everytime you use this step the browser will restart in order to set the proxy unless it has already been started.
  		URL:
 			Address where BrowserMob Proxy is running on
 		Example:
 			Given I turn metrics monitoring on "192.168.0.10:9090"


 	16.	I start recording metrics with the label "LABEL"

 		Sends a request to BrowserMob Proxy to start a new HAR (http archive) recording and to capture all the following http traffic.
 		LABEL:
 			Label you want to give to this recording
 		Example:
 			And I start recording metrics with the label "somerandomsite-homepage"


 	17.	I save the metrics as "FILENAME"

 		Saves the current state of a previously started HAR recording on disk.
 		Output file is a JSON.
 		FILENAME:
 			Name of the file
 			All the files will be placed in a folder called 'HAR' in the working directory of Behat
 		Example:
 			Then I save the metrics as "homepage.har"


 	18.	I upload the metrics to "URL"

 		Uploads the previously saved HAR file to a HAR Storage server.
 		HAR Storage is a HAR visualizer designed for performance analytics.
 		URL:
 			Address where HAR Storage is running on
 		Example:
 			And I upload the metrics to "192.168.0.10:5000"


 	19.	I should not see any broken resources

 		Looks for bad http responses in the previously saved HAR file.
 		It will complain if there's any response code other than 200.
 		Example:
 			Then I should not see any broken resources


 	20.	I turn metrics monitoring off

 		Removes the proxy listener and proxy configuration of the browser
 		The browser will restart after calling this step unless it has already been turned off
 		You don't need to use this step if this is always the last step
 		Example:
 			And I turn metrics monitoring off









