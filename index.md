---
layout: home
title: FPGA VGA Driver Project
tags: fpga vga verilog
categories: demo
---

Hi, I am Choon Xiang and welcome to my FPGA VGA Driver Project blog. I will be drawing a simplified Straw Hat Pirates logo from the manga and anime One Piece. I will be documenting my progress so read along if you are interested!

## **Template VGA Design**
### **Project Set-Up**
Summarise the project set-up and design flow. Include a screenshot of your own set-up, for example see the image of my Project Summary window below. Guideline 1 short paragraph.

<img src="https://raw.githubusercontent.com/melgineer/fpga-vga-verilog/main/docs/assets/images/VGAPrjSum.png">
### **Template Code**
Outline the structure and design of the Verilog code templates you were given. What do they do? Include reference to how a VGA interface works. Guideline: 2/3 short paragraphs, consider including screenshot(s).
### **Simulation**
Explain the simulation process. Reference any important details, include a well-selected screenshot of the simulation. Guideline: 1/2 short paragraphs.
### **Synthesis**
Describe the synthesis and implementation processes. Consider including 1/2 useful screenshot(s). Guideline: 1/2 short paragraphs.
### **Demonstration**
Perhaps add a picture of your demo. Guideline: 1/2 sentences.

## **My VGA Design Edit**
Initially, I wanted to draw an original Straw Hat Pirates logo from the manga and anime One Piece.

<img src="https://raw.githubusercontent.com/ChoonXiangg/SOC-Project/refs/heads/main/docs/assets/images/Straw%20Hat%20Pirates%20Logo.webp">

Unfortunately, as we can see from the image, I think it is too complicated for this project. Thus, I will be simplifying it and hopefully it will be just as nice as the original one and maybe a little cuter.
### **Code Adaptation**

First, I declared the base parameters. They are screen height, screen width, x center, and y center. Since I am displaying graphics on a 640x480 display, the screen height will be 480 and the screen width will be 640. X center will be screen width / 2 and y center will be screen height / 2.

Then, I drew its skull by filling a white circle in the middle. First, I declared its radius. I figured 120 will be a good radius since then its diameter will be 240 which is half the screen height. Next, I used a conditional statement to declare the area of it. In fact, how you draw in Verilog is first, you declare the area you want to fill using a conditional statement. Then, you fill it using binarised RGB (Red, Green, and Blue) values of the colour.

Next, I drew its hat. I started by filling the top half of the circle dark yellow. 
After that, I drew the red bottom part of the hat by filling the middle to lower part of the hat red. Finally, I drew the brim of the hat by filling a dark yellow rectangle at the bottom part of the hat.

After that, I drew its eyes and its nose. It's just three black circles and since I knew how to draw a circle, it was quite simple.

if ((row - eyeYCenter) * (row - eyeYCenter) + (col - leftEyeXCenter) * (col - leftEyeXCenter) < eyeRadius * eyeRadius || (row - eyeYCenter) * (row - eyeYCenter) + (col - rightEyeXCenter) * (col - rightEyeXCenter) < eyeRadius * eyeRadius) begin

### **Simulation**
Show how you simulated your own design. Are there any things to note? Demonstrate your understanding. Add a screenshot. Guideline: 1-2 short paragraphs.
### **Synthesis**
Describe the synthesis & implementation outputs for your design, are there any differences to that of the original design? Guideline 1-2 short paragraphs.
### **Demonstration**
If you get your own design working on the Basys3 board, take a picture! Guideline: 1-2 sentences.

## **More Markdown Basics**
This is a paragraph. Add an empty line to start a new paragraph.

Font can be emphasised as *Italic* or **Bold**.

Code can be highlighted by using `backticks`.

Hyperlinks look like this: [GitHub Help](https://help.github.com/).

A bullet list can be rendered as follows:
- vectors
- algorithms
- iterators

Images can be added by uploading them to the repository in a /docs/assets/images folder, and then rendering using HTML via githubusercontent.com as shown in the example below.

<img src="https://raw.githubusercontent.com/melgineer/fpga-vga-verilog/main/docs/assets/images/VGAPrjSrcs.png">
