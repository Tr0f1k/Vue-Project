# First Js Project

I wrote this code through Visual Studio by using Vue framework. To start the project, I have opened the project in Visual Studio Code, opened the terminal there and wrote this command: "npm run serve".


# How To Work With it

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

Generally, there are not that much changes in this update. The only change that was made is making it work with Vue framework and there is a lot of work which still has to be done.

# Upcoming updates:
1) Optimizing openTables() method, since it is highly unefficient and so far is accessible only by pressing "Press Me!" button. I will emit the openTables() method to the App.vue component and trigger it as the id value changes.
2) Working with styles of certain components, especially input and result tables.
3) Create a template for printing the outputs of the calculations (that is what the Order ID field was originally created for).
4) Create another calculator and add it to the website. The way I see it is that on the home page the user will be able to choose between two calculators: the one that I have already created and the one that I will create. I'm still thinking whether I should make all of it on the same page or should I create different pages for each calculator.
5) Break up the code in smaller pieces and put it in separate components. In this version, I have only two components. I plan on using more components that I have currently used
