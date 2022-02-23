# Landing Page Project

## Table of Contents

* [Instructions](#instructions)

## Instructions

The starter project has some HTML and CSS styling to display a static version of the Landing Page project. You'll need to convert this project from a static project to an interactive one. This will require modifying the HTML and CSS files, but primarily the JavaScript file.

To get started, open `js/app.js` and start building out the app's functionality

For specific, detailed instructions, look at the project instructions in the Udacity Classroom.

---
**Version 1.1.0**
## Screenshots

### A screenshot of the issue that the reviewer addressed:
The reviewer said, "Hi, On mobile screen, the page is not rendered correctly. Please fix it."
![Screenshot1](https://github.com/Youssef-Hassane/Screenshot/blob/main/Screen%20Shot%201.png?raw=true)


### A screenshot after I fixed the issue:
![Screenshot2](https://github.com/Youssef-Hassane/Screenshot/blob/main/ScreenShot%202.png?raw=true)

#### After a few seconds the navigation bar will disappear:
![Screenshot4](https://github.com/Youssef-Hassane/Screenshot/blob/main/Screen%20Shot%204.png?raw=true)

![Screenshot3](https://github.com/Youssef-Hassane/Screenshot/blob/main/Screen%20Shot%203.png?raw=true)



## How I fixed the issue?
I just removed the <img> elements that were making the issue.

---
**Version 1.0.0**

Hi there,

So here I'm going to discuss the project.

At first I add every li and a element's manually as you can see below. However, after I went to the HTML file and added more section I noticed that I'm required to go back to the JS file and add more li and a element for the new section.

The below is my first approach, and as you can see it wasn't efficient And every time I add more section and the HTML file I have to come back here and add more li and a element's for the new section:

 
  
  
  //First I'm going to create the Navigation bar by using JavaScript:
  let navUl = document.querySelector("#navbar__list");
  
  
  //Creating li elements                                                             
  let listOne = document.createElement("li");                          
  let listTwo = document.createElement("li");                  
  let listThree = document.createElement("li");              
  let listFour = document.createElement("li");                
  let listFive = document.createElement("li");                 
  let listSix = document.createElement("li");                   
  
  
  //Set a id Attribute
  listOne.setAttribute("id", "navSection1");
  listTwo.setAttribute("id", "navSection2");
  listThree.setAttribute("id", "navSection3");
  listFour.setAttribute("id", "navSection4");
  listFive.setAttribute("id", "navSection5");
  listSix.setAttribute("id", "navSection6");
 
  //Set a class Attribute
  listOne.setAttribute("class", "navItem");
  listTwo.setAttribute("class", "navItem");
  listThree.setAttribute("class", "navItem");
  listFour.setAttribute("class", "navItem");
  listFive.setAttribute("class", "navItem");
  listSix.setAttribute("class", "navItem");
 
 
 
 
  
  //set a id Attribute to the footter
  let foot = document.querySelector(".page__footer");
  foot.setAttribute("id", "foot")
  
  
  
  //Adding the all the a elements to all the li elements by using .innerHTML                  
  listOne.innerHTML =     `<a class="scroll menu__link" data-link="section1" href="javascript:void(0)" >Section 1</a>`;                
  listTwo.innerHTML =     `<a class="scroll menu__link" data-link="section2" href="javascript:void(0)" >Section 2</a>`; 
  listThree.innerHTML =   `<a class="scroll menu__link" data-link="section3" href="javascript:void(0)" >Section 3</a>`; 
  listFour.innerHTML =    `<a class="scroll menu__link" data-link="section4" href="javascript:void(0)" >Section 4</a>`;
  listFive.innerHTML =    `<a class="scroll menu__link" data-link="section5" href="javascript:void(0)" >Section 5</a>`; 
  listSix.innerHTML =     `<a class="scroll menu__link" data-link="foot" href="javascript:void(0)" >Footer</a>`; 
  
  
  //The previous code summarize all that: 
  
  //Creating a elements                               //Set a href Attribute    
  let linkOne = document.createElement("a");          linkOne.setAttribute("href", "#section1");
  let linkTwo = document.createElement("a");          linkTwo.setAttribute("href", "#section2");
  let linkThree = document.createElement("a");        linkThree.setAttribute("href", "#section3");
  let linkFour = document.createElement("a");         linkFour.setAttribute("href", "#section4");
  let linkFive = document.createElement("a");         linkFive.setAttribute("href", "#section4");
  let linkSix = document.createElement("a");          linkSix.setAttribute("href", "#foot");
 
  //Adding the all the a elements to all the li elements
  listOne.appendChild(linkOne);
  listTwo.appendChild(linkTwo);
  listThree.appendChild(linkThree);
  listFour.appendChild(linkFour);
  listFive.appendChild(linkFive);
  listSix.appendChild(linkSix);
  
  
  
  //Adding all the li elements to the ul element 
  navUl.append(listOne, listTwo, listThree, listFour, listFive, listSix);
 

Therefore, I needed to create a function that automatically create a li and a element's to every section in the HTML file.

Here is the function that automatically create a li and a element's to every section in the HTML file:

//By using the .getElementById I selected the element that has id of navbar__list which is the ul element that in the nav element
let navigationBarUnorderedList  = document.getElementById("navbar__list");

//By using .querySelectorAll() function select all the section element's in the HTML file
let selectAllSections = document.querySelectorAll("section");


//Creating a function that called createNavigationBarListElement
//The purpose of this function is to see how many sections are in the HTML file and create a list element in the unordered list element
function createNavigationBarListElement() {

    //Using the forEach loop in order to loop in the selectAllSections Array
    selectAllSections.forEach( function(section) {

        //Creating li elements by using the createElement function and save it in the listElement variable
        let listElement = document.createElement ("li");

        //Modifying the li element by using the .innerHTML function
        //Create a a element that has class, data-link (special attribute ), and href attribute
        listElement.innerHTML = `<a class="scroll menu__link" data-link="${section.id}" href="#${section.id}" >${section.dataset.nav}</a>`;

        //Add the li element that was created in the ul element
        navigationBarUnorderedList.appendChild(listElement);
        }
    );
};

---

## You can see the rest of the project in the app.js file.


---

## Contributors

- Youssef Hassane

---

## References

- MDN. (n.d.). Array.prototype.foreach() - javascript: MDN. JavaScript | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach

- MDN. (n.d.). ClearTimeout() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/clearTimeout

- MDN. (n.d.). Document.createElement() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement 

- MDN. (n.d.). Document.getElementById() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById 

- MDN. (n.d.). Document.getElementById() - web apis: MDN. Web APIs | MDN. Retrieved February 22, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById 

- MDN. (n.d.). Document.querySelector() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector 

- MDN. (n.d.). Document.querySelectorAll() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll 

- MDN. (n.d.). Element.append() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Element/append 

- MDN. (n.d.). Element.getAttribute() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute 

- MDN. (n.d.). Element.getBoundingClientRect() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect 

- MDN. (n.d.). ELEMENT.INNERHTML - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML 

- MDN. (n.d.). Element.scrollIntoView() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView 

- MDN. (n.d.). Element.setAttribute() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute 

- MDN. (n.d.). Event.preventDefault() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault 

- MDN. (n.d.). EventTarget.addEventListener() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener 

- MDN. (n.d.). Node.appendChild() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild 

- MDN. (n.d.). SetTimeout() - web apis: MDN. Web APIs | MDN. Retrieved February 20, 2022, from https://developer.mozilla.org/en-US/docs/Web/API/setTimeout 