# **The seven chakras Testing**

## **Testing methods**

Several methods have been used for continuous improvement during the project as well as test post finishing the project. The first part of this document covers the issues faced and solved during the project. The second part is about the testing post project.  

## **Manual testing**

The following manual methods were used for testing:  

1. Testing by changing the code in GitPod and viewing the output on port 8000. I continously checked this on the responsiveness and made media queries where needed. I made changes in the "inspect" part just to see what impact my changes would have and to find any issues. For example a part of my screen was showing blank and the main part was not getting covered by it. By using the inspect option I came to know what was causing this issue. Also, below the footer there were some additional quotes which did allow the footer to align to the bottom. I managed to get both of these issues resolved.
2. Deployed the website via GitHub and checked how the website would look here. From here I discovered that not all images were showing which were visible on the testing website. The reason for this was that I used absolute values instead of relative values.
3. Checked the website several browsers e.g. Internet Explorer, Chrome and Microsoft Edge. This did not cause any issues. No issues were found here.
4. Shared the URL with my family so they could have a look at their devices and see if everything is readable and showing up correctly. No issues were found here.
5. Mentor session with David on 9 April, 14 April and 17 April. I kept a log with all my questions and all improvement points mentioned in the meetings. The points that came out of the meeting are as following:  

| Date         |Feedback type|Description  |
| -------------|-------------|-------------|
|09/04-2024   | Improvement | Use color codes instead of color names as the names are not supported in all browsers.|
| 09/04-2024   | Improvement | Instead of br create a class with the padding styling and use this throughout the code in HTML.|
| 09/04-2024   | Improvement | While committing don’t use the past time, instead write the code down as an instruction.|
| 09/04-2024   | Error       | Error on empty hamburger label. Add a class sr in a span in the label. Add styling to the css file for this class. Code shared by mentor.|
| 14/04-2024   | Error       | Error for label without content. Reason for this was not mentioning the ID in the input fields. By adding the ID’s in the input fields with the same text as the for tag in the label I was able to solve this issue.|
| 14/04-2024   | Improvement | Change the image to webp format and make two sizes of each image for smaller and larger devices  |
| 14/04-2024   | Error       | Images visible in the testing environment, but not on the deployed website. Solved this by making the path relative instead of absolute by adding. |
| 14/04-2024   | Error       | Table taking too much space on smaller screens. Solved this by adding a media query for smaller screens and reversing the table vertically. |
| 14/04-2024   | Improvement | Uphon submitting the form I was using a post method. Mentor suggested me a different approach and sending the user to a different page on the same website. Implemented the changes. |
| 17/04-2024   | Improvement |Change comments on some places from the section name to explaining what exactly is happening.|  
| 17/04-2024   | Testing | In this session we went through the validators and three minor syntax issues were found in the css file. Such as: I forgot adding px after a number and I forgot closing the tags on two places.|   

Some other issues, next to the bugs mentioned above, that I faced during the project:  

* On the seven chakras page I have a table for elements for each chakra. This table was in horizontal view. On a smaller screen the table would go out of the view. I tried adding padding and making the columns smaller, but nothing really solved this issue. Then I came to the idea to make table go to a vertical view if the size is smaller from the point it breaks. I solved this by adding an additional media query.  
* In the contact form the button was only visible for a part. After some debugging it appeared that the button size is set to a fixed number using the input properties. My aim was to make the input fields slightly bigger. Forgetting that the button is a part of the input property. I tackled this by making an additional class and noting down a query below the input query which made the button bigger.  
* In the contact form the line break class did not give sufficient space for the label and the input on larger devices. The reason for this was that the font size increases with the device size To solve this I added an additional class for form padding and I added a media query with more padding then the existing class. I used this query in the media queries section which resolved the issue.  
    * Edit 1: It appeared that I was using the class in the label instead of input. This was the reason that the line break was not taking. I reversed the whole change above and put the class name back in the input field.
* On the balancing page I used a flex wrap to view two techniques next to each other. The issue was that it did not put the text sections next to each other. The reason for this issue was that the paragraph contains long sentences and the width was taken as 100%. I resolved this issue by making the width 50%. Because of this reason the flex started doing its work and two techniques could be seen next to each other.
* Unfixed not a bug, but an improvement point: I have two buttons one on the contact page and one on the contact feedback page. I could use the same styling by adding a class for both of them. I have added the contact feedback button bit of a last minute as an improvement of having some time left. As I did not want to break the code just before the deadline I have kept the styling seperate.
* Other bugs were found using the test validators. In depth review can be read below.

## **Testing with validators**

For this part the following validators were used:
1. Web Accesibility Evaluation Tools: [WAVE](https://wave.webaim.org/)  
2. W3C - Markup Validation Service - [W3C](https://validator.w3.org/)
3. Lighthouse - via Developers Tools  
4. Jigsaw W3 CSS validator: [Jigsaw](https://jigsaw.w3.org/css-validator/)

### **Wave**

This resulted in 5 errors which were fixed:  

* Error on empty hamburger label. Add a class sr in a span in the label. Add styling to the css file for this class. Code shared by mentor.  
* Four errors for label without content. Reason for this was not mentioning the ID in the input fields. By adding the ID’s in the input fields with the same text as the for tag in the label I was able to solve this issue.  

### **W3C HTML validator**

Two errors, two sub-errors and one warning was found using this validator:

1. Stylsheet tag
Place: On all pages.
Description: Issues with the stylsheet tag which caused three errors. I mentioned the tags stylesheet in. The stylesheet tags are used when you want the styling content in the HTML file. This would go above the body element. In this case I have a separate file for css. Removing the stylesheet tags made the three errors dissapear.

This caused in total three errors.

Error image:  

![W3C stylesheet error](docs/screenshots/w3c-stylesheet-tag-error.png)

2. Closing tag for icon
Place: On all pages.
Description: There was an additional closing tag in the Youtube icon. I deleted this tag and the error was solved.

Error image:  

![W3C Closing tag error](docs/screenshots/w3c-closing-tag-icon-error.png)

3. Section without header
Place: Balancing page.
Description: 
Warning of a section without header. After double checking this it was on the class “eight techniques” which covers the eight methods. As this element does not need any headings and was only meant to divide the content I changed the section tags to div tags. This solved the problem.

![W3C Closing tag error](docs/screenshots/w3c-section-lacks-heading-warning.png)  

### **W3C HTML validator**

Three minor syntax errors were found in the css file related to forgetting px behind a number, forgetting a closing tag.  

![Jigsaw css validator-no-errors](docs/screenshots/jigsaw-css-validator.PNG)  

### **Lighthouse**

An audit has been conducted on all pages for both mobile and desktop. And in normal browser and incognito mode. The audit was performed for four categories: performance, accesibility, best practices and SEO.

The results were as following:

#### **About page**  

Desktop results:
- The score for all four categories was 100%

Result: No changes were made

Audit image:  
![Lighthouse score for desktop about.html](docs/screenshots/lighthouse-about-desktop.png)  

Mobile results:
* On three parts the website scored 100%. On the performance part the percentage was 96%. The reason for this is:
    * Large content element – hero image. No changes made to this as it was a personal choice to make the website look vissually attractive.
    * Preload content. Out of scope for this project.

Result: No changes were made

Audit image:  
![Lighthouse score for mobile about.html](docs/screenshots/lighthouse-about-mobile.png)

#### **Seven chakras page**

Desktop results:

On three parts the website scored 100%. On the performance part the percentage is 94%. The reason for this is:

*	Large content element – hero image. No changes made to this as mentioned in the about section this was a personal decision.
*	Preload content. Out of scope for this project.
*	Convert images from png format to webp. Change accepted.
*	Use HTTP2. Out of scope for this project.

Action: Converted the image formats from png to webp and compressed the size to a smaller size.

Result: the performance boosted to a full 100%.

Audit image
Before changes:  
![Lighthouse score for Desktop seven-chakras.html](docs/screenshots/lighthouse-sevenchakras-desktop.png)

After changes:  
![Lighthouse score for Desktop seven-chakras.html](docs/screenshots/lighthouse-sevenchakras-desktop-after.PNG)

Mobile results:

On three parts the website scored 100%. On the performance part the percentage is 94%. The reason for this is:
*	Large content element – hero image. No changes made to this.
*	Preload content. Out of scope for this project.
*	Convert images from png format to webp and making the size smaller. Change accepted.
*	Use HTTP2. Out of scope for this project.

Action: Converted the image formats from png to webp and compressed the size to a smaller size.

Result: Converting the image to webp format and compressing them to a smaller size made a huge difference in the performance. It went up from 76 to 94.

Audit image
Before changes:  
![Lighthouse score for mobile seven-chakras.html](docs/screenshots/lighthouse-sevenchakras-mobile-before.png)

After changes:  
![Lighthouse score for mobile seven-chakras.html](docs/screenshots/lighthouse-sevenchakras-mobile-after.png)


#### **Balancing page**

Desktop results:

On three parts the website scored 100%. On the performance part the percentage is 99%. The reason for this is:
*	Pre connect to required origins. Out of scope for this project

Result: No changes were made

Audit image:  
![Lighthouse score for Desktop balance-chakras.html](docs/screenshots/lighthouse-balancing-desktop.png)

Mobile results:

On three parts the website scored 100%. On the performance part the percentage is 98%. The reason for this is:
*	Pre connect to required origins. Out of scope for this project.

Result: No changes were made

Audit image:  
![Lighthouse score for mobile balance-chakras.html](docs/screenshots/lighthouse-balancing-mobile.png)

#### **Contact page**

Desktop results:

On three parts the website scored 100%. On the performance part the percentage is 99%. The reason for this is:
*	Large content element – hero image. No changes made to this.

Result: No changes were made

Audit image:  
![Lighthouse score for Desktop contact.html](docs/screenshots/lighthouse-contact-desktop.png)

Mobile results:

On two parts the website scored 100%. 
On the performance part the percentage is 99%. The reason for this is:
*	Eliminate render-blocking resource. No changes were made

On the SEO part the percentage is 98%. The reason for this is:
*	Tap targets are not sized appropriately. – Change accepted

Error image:  
![Lighthouse error for SEO mobile contact.html](docs/screenshots/lighthouse-contact-mobile-seo-error.png)

Action: Resize the dropdown field

Result: This solved the issue and brought the percentage up to 100%

Audit image
Before changes:  

![Lighthouse score for Desktop contact.html](docs/screenshots/lighthouse-contact-mobile-before.png)

After changes:  

![Lighthouse score for Desktop contact.html](docs/screenshots/lighthouse-contact-mobile-after.png)

#### **Contact feedback page**

Desktop results:
* The score for all four categories was 100%

Result: No changes were made

Audit image:  
![Lighthouse score for desktop contact-feedback.html](docs/screenshots/lighthouse-contact-feedback-desktop.PNG)

Mobile results:
* On three parts the website scored 100%. On the performance part the percentage was 92%. The reason for this is:
    * Large content element – hero image. No changes were made.
    * Eliminate render blocking elements: This is done on purpose. 

Result: No changes were made

Audit image:  
![Lighthouse score for mobile contact-feedback.html](docs/screenshots lighthouse-contact-feedback-mobile.PNG)

***
[return to README.md](README.md)