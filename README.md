# Intermediate-JavaScript-Frames-and-Windows-

Popups and window methods 
Popups and window methods are commonly used in web development to interact with browser windows and pop-up windows. These methods allow you to open new browser windows, manipulate them, and perform various operations on them. Here are some key window methods and their purposes: 

window.open(): 
Opens a new browser window or tab with the specified URL. 
Allows you to control the window's dimensions, position, and appearance. 
Returns a reference to the newly opened window, which can be used to interact with it. 

window.close(): 
Closes the current browser window or tab. 
Note that it can only close windows that were opened using JavaScript (window.open()). 

window.alert(): 
Displays a simple dialog box with a message and an "OK" button. 
Used for showing information or alerts to the user. 

window.confirm(): 
Displays a confirmation dialog box with "OK" and "Cancel" buttons. 
Returns true if the user clicks "OK" and false if they click "Cancel." 

window.prompt(): 
Displays a dialog box with an input field where the user can enter text. 
Returns the text entered by the user or null if they cancel.  

window.scrollTo(): 
Scrolls the current window to a specified position. 
Allows you to control the scroll position both horizontally and vertically. 

window.scrollBy(): 
Scrolls the current window by a specified number of pixels. 
Useful for scrolling the window relative to its current position. 


window.location: 
Provides information about the current URL and allows you to navigate to a different URL. 
You can set window.location.href to navigate to a new URL or read properties like hostname and pathname. 

window.reload(): 
Reloads the current page, optionally forcing a fresh fetch from the server. 
You can call it true as an argument to force a server fetch. 


window.history: 
Provides access to the browser's session history. 
Allows you to navigate backward and forward in the history stack. 

window.open 
The window.open() method in JavaScript is used to open a new browser window or tab. It allows you to specify the URL of the page to be displayed in the new window and provides various options to control the appearance and behavior of the new window. Here is the basic syntax of window.open(): 
URL (required): The URL of the page to be opened in the new window or tab. 
windowName (optional): A string that specifies the name of the new window. If a window with the same name already exists, the content will be loaded in that window. If the name is _blank, a new window or tab will be opened each time. 
windowFeatures (optional): A string that specifies various window features, such as its dimensions, position, and behavior. These features are specified as a comma-separated list of key-value pairs. 

Here are some commonly used window features: 
width and height: Set the width and height of the new window in pixels. 
top and left: Set the position of the new window on the screen. 
resizable: Allow the user to resize the window (yes or no). 
scrollbars: Display scrollbars in the window (yes or no). 
menubar, toolbar, location, status, directories: Control the display of various browser elements (yes or no). 

Accessing popup from window 
To access the window object of a popup window or child window from the parent window, you typically need to store a reference to the child window when you open it using the window.open() method. Here's how you can access the window object of a popup window from the parent window: 

Opening the Popup Window: 
When you open the popup window using window.open(), assign the returned reference to a variable in the parent window. This reference allows you to interact with the popup window. 
Accessing the Popup Window's window Object: 
You can use the reference variable (popupWindow) to access the window object of the popup window. For example, you can set the location property to navigate the popup to a different URL:; 
You can also interact with the popup window's DOM and perform other operations, such as accessing properties or methods defined in the popup window's JavaScript code. 

Closing the Popup Window: 
To close the popup window programmatically from the parent window, you can use the close() method on the window object of the popup: 

Closing a popup 
To close a popup window programmatically from JavaScript, you can use the window.close() method. This method is called on the window object of the popup window you want to close. Here's how you can close a popup window: 

Open the Popup Window: 
First, you need to open the popup window and store a reference to it in a variable. 
 
Close the Popup Window: 
To close the popup window, you can call the close() method on the popupWindow reference: 

Scrolling and resizing 
In JavaScript, you can programmatically control scrolling and resizing of browser windows or elements: 

Scrolling: 
Scrolling the Entire Page: 
Use window.scrollTo(x, y) to set the scroll position in pixels from the top-left corner of the page. 
You can scroll to a specific position or scroll to a specific element by its ID using element.scrollIntoView(). 
Scrolling Within an Element: 
Set the scrollTop property of a specific element to control scrolling within that element. 

Resizing: 
Resizing a Browser Window: 
Use window.resizeTo(width, height) to resize the current browser window to specific width and height dimensions. 
Note that some browsers may restrict window resizing for security reasons. 

Resizing an Element: 
Set the style properties for width and height of an HTML element (e.g., a div) to control its size dynamically. 
This is commonly used to create resizable elements within web applications. 
Detecting Window Resize: 
Add an event listener to the window object using window.addEventListener("resize", function() {}) to detect and respond to window resize events. 

 

Scrolling a window 
To scroll a window in JavaScript, you can use the window.scrollTo() method. Here is a summary of how to use it: 
Scrolling to a Specific Position: 
Use window.scrollTo(x, y) to set the scroll position in pixels from the top-left corner of the document or viewport. 
The x argument represents the horizontal position (left), and the y argument represents the vertical position (top). 
This method allows you to scroll the entire window to a specified location. 

Scrolling to an Element: 
You can scroll to a specific HTML element on the page by using the element.scrollIntoView() method. 
This method scrolls the window so that the specified element becomes visible within the viewport. 

Focus/Blur on a window 
In JavaScript, you can use the focus() and blur() methods to control the focus and blur events on a browser window. These methods allow you to programmatically set focus to or remove focus from a window or tab, typically a popup window. Here is how to use them: 

1. Setting Focus on a Window: 
To set focus on a window, use the focus() method on the window object. This will bring the window to the front of the screen and make it active: 
In this example, clicking a button or invoking a function could trigger the focus() method to bring the popup window to the foreground. 
2. Removing Focus from a Window: 
To remove focus from a window or blur it, you can use the blur() method on the window object: 

Cross-Window Communication 

Same Origin 
The Same-Origin Policy is a security feature implemented in web browsers to prevent web pages from making requests to a different domain or origin than the one that served the web page. This policy is a fundamental security concept in web development, and it helps protect users from certain types of attacks, such as cross-site request forgery (CSRF) and cross-site scripting (XSS). 
Here is how the Same-Origin Policy works in JavaScript: 
Same-Origin Definition: Two web pages are considered to have the same origin if they have the same protocol (e.g., HTTP or HTTPS), domain (e.g., example.com), and port (e.g., 80 or 443). Any variation in these parts of the URL constitutes a different origin. 
Access Restrictions: JavaScript running on a web page is typically restricted by the Same-Origin Policy. This means that JavaScript code in one web page cannot directly access or interact with the content of a different origin. For example, JavaScript from one website cannot read or modify the DOM (Document Object Model) of a different website. 
Cross-Origin Requests: While JavaScript from one origin cannot directly access resources on a different origin, there are mechanisms to enable controlled interactions. For example, Cross-Origin Resource Sharing (CORS) headers can be set on a server to allow specific origins to make cross-origin HTTP requests to that server. Similarly, JSONP (JSON with Padding) and Cross-Origin XMLHttpRequest are techniques that can be used to fetch data from other origins in a controlled manner. 
Security Implications: Violations of the Same-Origin Policy can lead to security vulnerabilities. For instance, if an attacker can inject malicious JavaScript into a website and trick a user into executing that code, the attacker could potentially steal data from the user's session on that website 

In action: iframe 
An iframe (short for "inline frame") is an HTML element that allows you to embed another HTML document within the current document. It's like a window or viewport into another web page, and it is commonly used to display external content within a web page, such as advertisements, maps, or content from other websites. Here's how iframes work and how they can be used in action: 
Creating an iframe: To create an iframe in an HTML document, you use the <iframe> element and specify the source URL of the content you want to embed. Controlling the iframe: You can control various aspects of the iframe, such as its width, height, and scrolling behavior, by using attributes like width, height, and scrolling.This sets the width and height of the iframe and disables scrolling. 
Accessing the iframe's content: If the iframe's content is from the same origin (i.e., the same domain, protocol, and port), you can access and manipulate its content using JavaScript. Then, you can interact with the iframe's content just like you would with any other HTML document. 
Cross-Origin Restrictions: When the iframe's content comes from a different origin, JavaScript within the parent document is generally restricted from accessing the iframe's content due to the Same-Origin Policy. However, you can communicate between the parent and iframe using techniques like postMessage, which allows secure cross-origin communication. 

Use Cases: Iframes are commonly used for various purposes, including: 
Embedding videos, maps, or social media content from external sources. 
Displaying advertisements from ad networks. 
Integrating third-party widgets or components into a web page. 
Loading content from a different part of the same website. 
Security Considerations: Be cautious when embedding content from external sources, as it can introduce security risks, especially if the content is not trusted. Ensure that you trust the sources of the content and consider implementing security measures like content security policies (CSP) to mitigate potential risks. 

Windows on subdomains: document.domain 
The document.domain property is a feature in JavaScript that allows you to relax the same-origin policy for web pages on subdomains of the same root domain. This can be useful when you have multiple subdomains and need to enable cross-origin communication between them. Here is how it works: 
Same-Origin Policy: By default, web pages from different origins (domains, subdomains, or ports) are subject to the same-origin policy, which restricts their ability to interact with each other for security reasons. 
Using document.domain: You can use the document.domain property to relax the same-origin policy for pages on subdomains of the same root domain. To do this, both the parent and child pages set their document.domain property to the same value, which should be the root domain.  
Cross-Origin Communication: Once both the parent and child pages have set document.domain to the same value (in this case, "example.com"), they are considered to have the same origin. This allows JavaScript running in one page to access the DOM of the other, even though they are on different subdomains. 

Use Cases: This technique is often used for scenarios like: 
Implementing Single Sign-On (SSO) solutions across subdomains. 
Sharing data or variables between pages on different subdomains. 
Enabling cross-subdomain communication for widgets, iframes, or other embedded content. 
Security Considerations: Be cautious when using document.domain because it effectively relaxes the security boundaries imposed by the same-origin policy. Make sure you trust the content on both subdomains, as any script on one subdomain can access the DOM of the other subdomain once document.domain is set. 
Additionally, it is important to note that setting document.domain only works for subdomains of the same root domain. It cannot be used to relax the same-origin policy between entirely different domains. 
Browser Compatibility: document.domain is supported in most modern web browsers, but it must be used consistently on both the parent and child pages for it to work correctly. 

 
Iframe: wrong document pitfall  
Using iframes in web development can introduce various challenges, and one common pitfall is dealing with the "wrong document" problem. This issue arises when you attempt to manipulate or access the content of an iframe, but your JavaScript code ends up targeting the wrong document. Here is a closer look at this pitfall and how to avoid it: 

The "Wrong Document" Problem: 
The "wrong document" problem occurs when you have an iframe embedded in your web page, and you want to interact with the content within that iframe using JavaScript. However, due to the way iframes work, your JavaScript code might accidentally target the main document instead of the iframe's document. This can lead to unexpected behavior and errors. 

Common Causes: 
Timing Issues: If you try to access the iframe's content before it has fully loaded, your code may target the wrong document. 
Same-Origin Policy: The same-origin policy can prevent you from accessing the content of an iframe if it comes from a different domain. 
Nested iframes: When dealing with nested iframes (iframes within iframes), you need to be especially careful to target the correct iframe's document. 

How to Avoid the Pitfall: 
To ensure you target the correct document within an iframe, consider the following best practices: 
Wait for iframe to load: Use the load event to ensure the iframe has fully loaded before attempting to access its content. Check the Same-Origin Policy: Ensure that the iframe's content comes from the same origin as the parent document, as the same-origin policy may block access to cross-origin iframes. 
Use iframe IDs or Names: Give your iframes unique IDs or names and use those identifiers to access them. This reduces the chances of mistakenly targeting the wrong iframe. 
Be mindful of nesting: If you have nested iframes, be explicit about which iframe you want to interact with by traversing the iframe hierarchy. 

Security Implications: 
Be cautious when interacting with the content of iframes, especially if they come from different domains. Always consider security implications and avoid executing untrusted code within iframes. 

Collection: window.frames 
In JavaScript, the window.frames collection is an array-like object that represents all the frames (including iframes) within the current window or document. Each frame in the collection can be accessed using numeric indices, similar to an array. 

Here's how you can use the window.frames collection: 
Accessing Frames: 
You can access frames within the current window using numeric indices, starting from 0. For example, window.frames[0] represents the first frame, window.frames[1] represents the second frame, and so on. 
Iframes and frames within the current window are accessible through this collection. 
Manipulating Frames: 
Once you have a reference to a frame, you can interact with it just like you would with any other window or document. For example, you can access the document within a frame and manipulate its content:
Counting Frames: 
You can determine the number of frames within the current window by checking the length property of the window.frames collection: 
Named Frames: 
Iframes and frames can also have names, which allows you to access them by name instead of numeric index 

 

The “sandbox” iframe attribute 
The sandbox attribute is an HTML attribute that can be applied to an <iframe> element to restrict the behavior of the content displayed within the iframe. It provides a way to create a secure and isolated environment for potentially untrusted content, such as advertisements or third-party widgets, while preventing it from having full access to the parent web page. The sandbox attribute accepts a list of specific values that define the restrictions applied to the iframe. 

Here are some common values that can be used with the sandbox attribute: 
allow-same-origin: This value allows the iframe to navigate and interact with its own origin (the same domain, protocol, and port), but it restricts access to other origins. 
allow-scripts: This value allows the execution of JavaScript within the iframe. Without this value, JavaScript execution within the iframe is disabled. 
allow-forms: With this value, the iframe can submit forms. It allows form submission but does not grant access to the parent page's form data. 
allow-top-navigation: This value allows the iframe to navigate the top-level window, effectively allowing it to change the URL of the parent page. Use this with caution, as it can lead to security issues if not controlled. 
allow-modals: Allows the iframe to display modal dialogs (e.g., using window.alert() or window.confirm()). Without this value, modal dialogs are blocked. 
allow-popups: Allows the iframe to open new browser windows or tabs. It's typically used with allow-scripts to enable scripts within the iframe to open popups. 
allow-pointer-lock: Allows the iframe to use the Pointer Lock API for mouse control. This can be used for first-person games or immersive experiences. 
allow-orientation-lock: Allows the iframe to lock the device's orientation. This is commonly used for mobile applications and games. 
allow-popups-to-escape-sandbox: If the iframe has the allow-popups attribute, this value allows those popups to navigate outside of the sandbox. 
allow-storage-access-by-user-activation: This value allows the iframe to request access to storage (e.g., cookies and local storage) upon user activation (e.g., a user click). This enhances privacy by preventing automatic access to storage. 

Cross Window Messaging 
Cross-window messaging, often referred to as "Window.postMessage," is a mechanism in web development that allows different windows or iframes in a web page to communicate with each other securely, even when they originate from different origins (domains, protocols, or ports). This feature is important for creating interactive and coordinated experiences between different parts of a web page or between different web pages. 

The Clickjacking Attack 

Introduction to Clickjacking 
Clickjacking, also known as a "UI redress attack" or "user interface manipulation," is a web security vulnerability and an attack technique in which an attacker tricks a user into clicking on something different from what the user perceives, potentially causing them to take unintended actions without their knowledge or consent. Clickjacking attacks are designed to manipulate the user's interaction with a web page by placing a deceptive or transparent layer over the legitimate content. 

Here is an introduction to the concept of clickjacking: 
How Clickjacking Works: 
Deceptive Overlay: In a clickjacking attack, the attacker creates a malicious web page that contains an iframe or other HTML element. This iframe is typically positioned over a legitimate web page element, such as a button, link, or form, making it invisible or transparent. 
Tricking the User: When the victim visits the malicious web page, they see only the legitimate content and are unaware of the invisible iframe overlay. When they interact with what appears to be a harmless part of the page (e.g., clicking a button), they are, in fact, clicking on the transparent iframe. 
Unauthorized Actions: The victim's actions within the invisible iframe can be used to trigger unintended actions on the legitimate web page. These actions can range from making unauthorized purchases, changing account settings, sharing content on social media, or performing any action that the attacker desires. 

Key Characteristics of Clickjacking: 
Deception: Clickjacking relies on deception to mislead users into taking actions they did not intend to take. 
Transparency: The malicious overlay is often made transparent or hidden, making it difficult for users to detect that they are interacting with two layers of content. 
Cross-origin: Clickjacking can occur across different origins (domains) since web pages can include iframes from different sources. 

Mitigation and Prevention: 
Preventing clickjacking attacks can be challenging, but there are several mitigation techniques and best practices: 
X-Frame-Options: Web administrators can use the HTTP response header "X-Frame-Options" to control how their web pages are displayed within iframes. Setting this header to "DENY" or "SAMEORIGIN" can help prevent clickjacking. 
Content Security Policy (CSP): Implementing a robust CSP can restrict the sources from which content can be loaded, making it more difficult for attackers to embed malicious iframes. 
Frame-busting JavaScript: Web developers can include JavaScript code on their pages that checks if their page is being displayed within an iframe and take appropriate actions to prevent it. 
User Education: Users should be cautious when interacting with unfamiliar websites and should be aware of the risks associated with clicking on content that seems suspicious or too good to be true. 

 

Old school defenses (weak) 
Old school, or weak, defenses refer to security measures that were once commonly used to protect computer systems and data but have become less effective over time due to advances in hacking techniques and technology. These defenses may have been effective in the past, but they are no longer sufficient on their own to protect against modern cyber threats. Here are some examples of old school defenses: Antivirus Software: Traditional antivirus software relies on signature-based detection to identify known malware. While it can still catch some common threats, it is less effective against sophisticated and zero-day attacks that don't have known signatures. 
Firewalls: Legacy firewalls primarily focus on packet filtering and port blocking. They are less effective at detecting and blocking application-level threats, such as advanced malware and targeted attacks. 
Weak Passwords: Using weak passwords, such as "password123" or "admin," is a common security mistake. Modern attackers use sophisticated techniques like password cracking and brute force attacks to compromise accounts with weak passwords. 
Single-factor Authentication (SFA): Relying solely on usernames and passwords for authentication is a weak defense. Multi-factor authentication (MFA), which requires at least two forms of verification, is much more secure. 
Outdated Software: Failing to regularly update and patch software and operating systems leaves systems vulnerable to known security vulnerabilities that attackers can exploit. 
Security by Obscurity: Relying on the obscurity of systems or network configurations as a primary defense is a weak approach. Security should not depend on attackers not discovering system details; instead, it should be based on strong security principles and practices. 
No Intrusion Detection or Prevention: Neglecting to implement intrusion detection systems (IDS) or intrusion prevention systems (IPS) means that suspicious activities and attacks may go unnoticed until it's too late. 
Static Security Policies: Static security policies that don't adapt to changing threats and business needs are ineffective. Security policies should be dynamic and regularly updated to address emerging risks. 
No User Training: Neglecting to educate employees and users about cybersecurity risks and best practices leaves organizations vulnerable to social engineering attacks, such as phishing. 
Lack of Security Monitoring: Failing to actively monitor systems for signs of compromise or suspicious activity can result in delayed detection of security breaches. 
Open Wi-Fi Networks: Using open or unsecured Wi-Fi networks without encryption or authentication can expose devices and data to various security risks. 
 

X-Frame-Options 
X-Frame-Options is a security-related HTTP response header that web servers can send to web browsers to control whether a web page should be allowed to be displayed in an iframe. This header is primarily used to prevent clickjacking attacks and enhance web security by restricting how a page can be embedded in other websites or frames. 

There are three common values that can be set for the X-Frame-Options header: 
DENY: When the X-Frame-Options header is set to DENY, the web page is not allowed to be displayed in any iframe, regardless of the origin. 
SAMEORIGIN: When the X-Frame-Options header is set to SAMEORIGIN, the web page can only be displayed in an iframe on the same origin (i.e., the same domain, protocol, and port) as the page itself. 
ALLOW-FROM: This value allows you to specify a specific origin (e.g., a domain) that is allowed to embed the web page in an iframe. All other origins are denied. 

How X-Frame-Options Works: 
When a web browser receives a response from a web server with the X-Frame-Options header set, it checks the value of the header to determine whether the web page should be displayed in an iframe. If the value matches the browser's security policy, the page can be embedded. Otherwise, the browser will prevent the page from being loaded in an iframe. 

Benefits and Use Cases: 
Clickjacking Prevention: X-Frame-Options is a valuable defense against clickjacking attacks, where attackers attempt to trick users into performing actions, they did not intend to by overlaying a web page with malicious content. 
Enhanced Web Security: By controlling where a web page can be embedded, web administrators can reduce the risk of unauthorized use of their content and help protect against certain types of attacks. 
Cross-Origin Security: It helps enforce the same-origin policy, which is a fundamental security concept on the web. This policy restricts how web pages from different origins can interact with each other. 

Samesite cookie attribute 
The SameSite cookie attribute is an attribute that can be set when creating HTTP cookies in web applications. It is used to control how cookies are sent with cross-origin requests and helps mitigate certain types of security vulnerabilities related to cross-site request forgery (CSRF) and cross-site scripting (XSS). The SameSite attribute has three values: 

SameSite=None: When you set the SameSite attribute to None, it means that the cookie can be sent with both same-site and cross-site requests. This is often used for cookies that are used for authentication and need to be accessible to third-party websites or APIs. 

Use Cases: 
Session Cookies: For session management cookies, it's common to set SameSite=None to allow them to be sent with cross-origin requests, ensuring a consistent user experience across sites. 
Security Cookies: For security-sensitive cookies, such as CSRF tokens or authentication cookies, it's often recommended to use SameSite=Strict to prevent them from being exposed to cross-site requests. 
Functional Cookies: For cookies used for non-security purposes, like user preferences or analytics, you may choose SameSite=Lax to strike a balance between functionality and security. 
Security Benefits: 
CSRF Mitigation: The SameSite attribute helps mitigate CSRF attacks by preventing cookies from being sent with unauthorized cross-site requests. 
XSS Mitigation: It can also mitigate the impact of certain XSS attacks by limiting the exposure of cookies to cross-site requests initiated by malicious scripts.  

ArrayBuffer and Binary Array 

ArrayBuffer 
An ArrayBuffer is a built-in JavaScript object that represents a generic, fixed-size binary data buffer. It is a low-level data structure used for handling raw binary data, often in the context of working with binary files, network protocols, or other data formats where precise control over memory and binary data is required. ArrayBuffer objects do not have built-in methods for data manipulation like arrays; instead, they provide a raw storage buffer for binary data. 

Here are some key characteristics and usage patterns of ArrayBuffer: 
Fixed Size: ArrayBuffer has a fixed size that is specified when creating the buffer. Once the size is set, it cannot be changed. This fixed size is allocated in memory, making it efficient for low-level data operations. 
Byte-Based: An ArrayBuffer is organized as a sequence of bytes, each with a numerical value between 0 and 255. 
Data Views: To read and manipulate data within an ArrayBuffer, you typically use specialized views like DataView, TypedArray, or Uint8Array. These views provide methods and properties for reading and writing data in a type-safe manner (e.g., 16-bit integers, 32-bit floats). 
Memory Management: ArrayBuffer objects do not have built-in garbage collection, so you need to manage their lifecycle manually. This means you are responsible for releasing the memory when you are done using the buffer. 

Usage Examples: 
Reading and writing binary files. 
Parsing binary data formats, such as image formats (e.g., PNG, JPEG), audio formats (e.g., WAV, MP3), or binary protocols (e.g., WebSocket frames, network packets). 
Manipulating binary data for cryptography or data compression. 
 
TypedArray 
A TypedArray is a typed view into an ArrayBuffer in JavaScript, providing a way to access and manipulate binary data in a more structured and type-safe manner. TypedArrays allow you to work with arrays of binary data where each element has a fixed data type, such as 8-bit integers, 16-bit integers, 32-bit floats, etc. They are especially useful when dealing with binary data in scenarios like file I/O, networking, and data processing. 

Here are some key characteristics and types of TypedArrays in JavaScript: 
TypedArray Types: There are several TypedArray types available in JavaScript, each representing a specific data type: 
Int8Array: 8-bit two's complement signed integer. 
Uint8Array: 8-bit unsigned integer. 
Uint8ClampedArray: 8-bit unsigned integer with clamping, ensuring values stay within the range [0, 255]. 
Int16Array: 16-bit two's complement signed integer. 
Uint16Array: 16-bit unsigned integer. 
Int32Array: 32-bit two's complement signed integer. 
Uint32Array: 32-bit unsigned integer. 
Float32Array: 32-bit IEEE floating-point number. 
Float64Array: 64-bit IEEE floating-point number. 


TypedArray methods 
TypedArrays in JavaScript come with a variety of methods for manipulating and working with binary data efficiently. These methods allow you to perform operations such as reading and writing data, searching for values, and transforming elements within the TypedArray. Here are some commonly used methods available for TypedArrays: 

Subarray Methods: 
slice (begin, end): Returns a new TypedArray that includes a shallow copy of a portion of the original array from begin (inclusive) to end (exclusive). 
subarray (begin, end): Returns a new TypedArray that references the same ArrayBuffer as the original array but with a different view from begin to end. 

Access and Iteration Methods: 
length: Returns the number of elements in the TypedArray. 
Index-based access: You can access individual elements using square brackets (e.g., arr[2]) just like regular arrays. 
Iteration: You can use standard iteration methods like forEach, map, filter, and reduce. 

Data Conversion Methods: 
toString(): Returns a string representation of the TypedArray, typically as a comma-separated list of values. 
join(separator): Converts the TypedArray elements to strings and joins them using the specified separator. 
toLocaleString(): Returns a string representation of the TypedArray elements using locale-specific formatting. 

Data Manipulation Methods: 
set (array, offset): Copies elements from a regular array or another TypedArray into the current TypedArray, starting at the specified offset. 
fill (value, start, end): Sets all elements in the TypedArray to the specified value within the specified range (start to end). 
reverse (): Reverses the order of elements in the TypedArray. 
Searching and Testing Methods: 
find(callback): Returns the first element in the TypedArray that satisfies the provided testing function. 
findIndex(callback): Returns the index of the first element in the TypedArray that satisfies the provided testing function. 
some(callback): Tests whether at least one element in the TypedArray satisfies the provided condition. 
every(callback): Tests whether all elements in the TypedArray satisfies the provided condition. 
includes(value): Checks if the TypedArray contains a specific value and returns a Boolean. 

Sorting Methods: 
sort(compareFunction): Sorts the elements of the TypedArray in place according to the provided compare function. By default, it sorts based on UTF-16 code units. 

TypedArray Conversion Methods: 
from(iterable): Creates a new TypedArray from an iterable object, such as an array or another TypedArray. 
of (...items): Creates a new TypedArray with the specified values. 

Numeric Methods: 
Numeric operations: TypedArrays have methods for mathematical operations, such as reduce, reduceRight, map, and more, which are useful for numerical data processing. 

Buffer Copy Methods: 
copyWithin(target, start, end): Copies a portion of the TypedArray to another location within the same TypedArray, allowing overlapping copies. 

Element Comparison Methods: 
every(callback): Tests whether all elements in the TypedArray satisfies the provided condition. 
some(callback): Tests whether at least one element in the TypedArray satisfies the provided condition. 


DataView 
A DataView is a built-in JavaScript object that provides a way to view and manipulate binary data stored in ArrayBuffer objects with a specified byte order. It is commonly used for low-level data operations, such as reading and writing binary data in network protocols, file formats, and other data structures where precise control over memory and data types is required 
