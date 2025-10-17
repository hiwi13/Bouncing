Project Title: Chapter2_Challenge_Applet
Class Name: BouncingBallApplet
Author: [Your Name]
Date: [Insert Date]

---------------------------------------------------------
1. Project Description
---------------------------------------------------------
This project is a simple Java Applet program that displays 
an animated red ball bouncing inside the applet window. 
The animation is created using a separate thread that 
continuously updates the ball’s position and redraws it 
on the screen.

---------------------------------------------------------
2. How the Program Works
---------------------------------------------------------
- The applet extends the Applet class and implements Runnable 
  to allow multithreading.
- In the init() method, the background color and applet size 
  are set.
- The start() method begins the animation by starting a new thread.
- The run() method uses a continuous loop to:
    1. Update the x and y coordinates of the ball.
    2. Reverse direction when the ball hits any edge.
    3. Call repaint() to redraw the ball at the new position.
    4. Pause for 30 milliseconds using Thread.sleep(30).
- The paint() method draws a red ball using the fillOval() method.

---------------------------------------------------------
3. How to Run the Program
---------------------------------------------------------
1. Compile the Java code:
   javac BouncingBallApplet.java

2. Create an HTML file named BouncingBallApplet.html with:
   -----------------------------------------------------
   <html>
     <head>
       <title>Bouncing Ball Applet</title>
     </head>
     <body>
       <h2>Bouncing Ball Applet</h2>
       <applet code="BouncingBallApplet.class" width="400" height="300">
         Your browser does not support Java Applets.
       </applet>
     </body>
   </html>
   -----------------------------------------------------

3. Run the applet using:
   appletviewer BouncingBallApplet.html

---------------------------------------------------------
4. Security (Applet Sandbox Restrictions)
---------------------------------------------------------
Java Applets run in a restricted "sandbox" environment 
for security reasons. They are NOT allowed to:
1. Read or write files on the user's computer.
2. Access network resources (like other servers) without permission.

---------------------------------------------------------
5. Modern Replacement Technologies
---------------------------------------------------------
Java Applets are now deprecated. Modern web technologies 
used instead are:
- HTML5 (for structure)
- CSS3 (for design and layout)
- JavaScript (for animation and interactivity)

Example (Bouncing Ball with JavaScript):
----------------------------------------
HTML:
<canvas id="ballCanvas" width="400" height="300"></canvas>

JavaScript:
let canvas = document.getElementById("ballCanvas");
let ctx = canvas.getContext("2d");
let x = 50, y = 50, dx = 4, dy = 4, r = 20;

function drawBall() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  ctx.beginPath();
  ctx.arc(x, y, r, 0, Math.PI*2);
  ctx.fillStyle = "red";
  ctx.fill();
  x += dx; y += dy;
  if (x + r > canvas.width || x - r < 0) dx = -dx;
  if (y + r > canvas.height || y - r < 0) dy = -dy;
}
setInterval(drawBall, 30);

---------------------------------------------------------
6. Legacy Importance
---------------------------------------------------------
Even though Java Applets are deprecated, learning about them is important because:
1. They demonstrate how early web-based Java programs worked.
2. They show how multithreading and graphics were handled in older systems.
3. Understanding them helps modern developers appreciate 
   the evolution of interactive web technologies.

---------------------------------------------------------
7. Output Description
---------------------------------------------------------
When the program runs, you will see:
- A blue (cyan) background window (400x300 pixels)
- A red ball bouncing smoothly within the window boundaries.
