# glass-bending

I wrote this code through Visual Studio and used Vue framework.

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

# How it works:

This is a glass bending calculator. In order to bend glass properly, you should know five variables:

1) Radius
2) Span
3) Girth
4) Angle
5) Rise

It is possible to find all five variables by knowing any of five combinations of two variables: Span and Rise, Span and Radius, Radius and Rise, Radius and Girth, Radius and Angle.

This program calculates all five variables by using any of these five combinations. In addition to that, it also calculates area and weight of the glass itself, and gives a warning if the angle is bigger than 90 degrees, because in that case, the glass will break under its' own weight.

Order ID will be used in the future. I am currently working on creating a printing template for this javascript program.

# Update : 16.06.2022

Generally, there are not that much changes in this update. The only change that was made is making it work with Vue framework and there is a lot of work which still has to be done. The Vue version of this project is in "glass-bending.zip" archive. To start the project, I have opened the project in Visual Studio Code, opened the terminal there and wrote this command: "npm run serve".

# Known Issues:

1) openTables() method is not optimized. It is highly unefficient and so far is accessible only by pressing "Press Me!" button.
2) Very small amount of components. I have to break up the code in smaller pieces and put it in separate components so that the program becomes more efficient

# Plans for upcoming updates:
1) Restyling of certain components, especially input and result tables.
2) Creating a template for printing the outputs of the calculations (that is what the Order ID field was originally created for).
3) Creating another calculator and adding it to the website. The way I see it is that on the home page the user will be able to choose between two calculators: the one that I have already created and the one that I will create. I'm still thinking whether I should make all of it on the same page or should I create different pages for each calculator.

# Update : 17.06.2022

I was working on resolving two issues from my previous version of a program and a minor update.  

# Updates:
1) Moving HTML (header, dropdown list, etc.) from App.vue to InputTables.vue. I did it so that when I will add a new calculator I can import it in the same component as glass bending calculator. 

# Resolved issues:
1) Very small amount of components: I have put each calculation option in its own component and I am conditionally rendering the components based on the chosen option.
2) Optimizing openTables() method: After beaking up the code on smaller components, there was no more necessity in using the openTables() method. It was used to show and hide the calculation tables. Now, since all the components are getting rendered conditionally, there is no need to hide or show anything. Because of that, I have just deleted this method.

# Known Issues:
1) Components related to calculation are not efficient. Each of them (except for the Default component) have similar parts.

# Plans for upcoming updates:
1) Making separate component for pieces of code shared within calculation components
2) Everything that has not been done from the previous plan