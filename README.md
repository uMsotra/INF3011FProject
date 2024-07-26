Virtual Art Museum
Welcome to the Virtual Art Museum, developed by Team 12. This project reimagines sports, cultural, and heritage preservation through an interactive virtual tour. This guide will help you understand and run the project on your local machine, even if you're not familiar with coding.

Overview
The Virtual Art Museum is a web-based application that showcases various artworks along with their descriptions and accompanying audio narrations. Users can explore a virtual gallery and interact with the exhibits. We utilized Three.js, a JavaScript library, to create and display 3D graphics in a web browser.

Prerequisites
To run the Virtual Art Museum, you will need:

A web browser (Google Chrome, Firefox, Safari, etc.)
An internet connection (for downloading initial setup files)
Setting Up the Project
Step 1: Download the Project Files
Download the project files as a ZIP file from the provided link.
Extract the contents of the ZIP file to a folder on your computer.
Step 2: Open the Project in a Browser
Navigate to the folder where you extracted the project files.
Locate the file named index.html.
Double-click on index.html to open it in your default web browser.
Running the Virtual Art Museum
Once you open index.html in your browser, the virtual tour will start automatically. Follow these steps to navigate through the tour:

Loading Screen
Wait for the loading screen to disappear. This screen indicates that the content is being fetched.
Start the Tour
Click on the "Start the virtual tour" button to enter the museum.
Navigating the Tour
Exploring the Museum
Move Around: Use your mouse or touch gestures to navigate through the museum.
View Artworks: Click on an artwork to zoom in and learn more about it. Each artwork has an accompanying description and audio narration.
Controls: Use the + and - buttons to zoom in and out of the artwork.
Information Panel: The panel on the right provides additional information about the selected artwork.
About Section: At the bottom of the screen, you can see information about the development team.
Interacting with Artworks
Left Wall: Contains artworks with descriptions and audio narrations.
Front Wall: Showcases significant cultural and historical moments.
Right Wall: Highlights prominent figures and events in South African history.
Back Wall: Displays iconic landmarks and pivotal moments.
Editing the Artworks
You can customize the virtual museum by adding your own images and audio narrations. Follow these steps to update the paintings.js file:

Step 1: Prepare Your Files
Images: Place your image files in the images folder.
Audio: Place your audio files in the audio folder.
Step 2: Update the paintings.js File
Open the scripts/paintings.js file in a text editor.
Use the LeftWall, FrontWall, RightWall, and BackWall functions to place your artworks.
Ensure that the image and audio filenames correspond with the ones in your code.
Example Code:

javascript
Copy code
// Function to place artwork on the left wall
LeftWall(xCoordinate, yCoordinate, "images/YourImage.jpg", "audio/YourAudio.mp3", "Description of your artwork");

// Function to place artwork on the front wall
FrontWall(xCoordinate, yCoordinate, "images/YourImage.jpg", "audio/YourAudio.mp3", "Description of your artwork");

// Function to place artwork on the right wall
RightWall(xCoordinate, yCoordinate, "images/YourImage.jpg", "audio/YourAudio.mp3", "Description of your artwork");

// Function to place artwork on the back wall
BackWall(xCoordinate, yCoordinate, "images/YourImage.jpg", "audio/YourAudio.mp3", "Description of your artwork");
Replace xCoordinate and yCoordinate with the desired coordinates for placing your artwork. The filenames should match those placed in the images and audio folders.

Technical Details
Project Structure
The project is organized as follows:

index.html: The main HTML file that sets up the structure of the webpage.
styles/styles.css: The CSS file that styles the webpage.
scripts/script.js: The JavaScript file that initializes the Three.js scene and handles user interactions.
scripts/paintings.js: The JavaScript file that places artworks in the virtual museum and attaches their descriptions and audio.
libraries/three.js: The Three.js library that enables the rendering of 3D graphics.
libraries/pleaserotate.js: A library that handles screen orientation prompts.
Using Three.js
Three.js is a powerful JavaScript library that allows us to create and display animated 3D graphics in a web browser using WebGL. Here's how we used it in our project:

Loading Three.js: In the index.html file, we include the Three.js library:

html
Copy code
<script src="libraries/three.js"></script>
Creating the Scene: In scripts/script.js, we create a Three.js scene, which acts as a container for all 3D objects, lights, and cameras:

javascript
Copy code
const scene = new THREE.Scene();
Adding a Camera: The camera determines what part of the scene is visible to the user:

javascript
Copy code
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
Rendering the Scene: The renderer displays the scene from the perspective of the camera:

javascript
Copy code
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);
Placing Artworks: In scripts/paintings.js, we define functions to place artworks on the walls of the virtual museum:

javascript
Copy code
function LeftWall(x, y, imageUrl, audioUrl, description) {
    // code to create and place the artwork
}
Animation Loop: We use an animation loop to continuously render the scene, making it interactive and responsive:

javascript
Copy code
function animate() {
    requestAnimationFrame(animate);
    renderer.render(scene, camera);
}
animate();
Linking Three.js and Project Goals
By using Three.js, we were able to create a realistic and interactive virtual museum. This allows users to explore and engage with the exhibits in an immersive way, achieving our goal of preserving and showcasing sports, cultural, and heritage artifacts.

Acknowledgements
This project was developed by Team 12 as part of the INF3011 course. We would like to thank our sponsors (CSIR) and instructors (Lectures and Mentors) for their support and guidance.
