# Ex05 Image Carousel

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM
imagecarousel .js
// src/ImageCarousel.js
import React, { useState } from 'react';
import './ImageCarousel.css'; // CSS for styling


const images = [ "https://via.placehoIder.com/600x300?text=Image+1",
"https://via.placeholder.com/600x300?text=Image+2",
 
"https://via.placehoIder.corn/600x300?text=Image+3", "https://via.placehoIder.corn/600x300?text=Irnage+4"
];


const ImageCarousel = () => {
const [currentlndex, setCurrentindex] = useState(0);


const nextlmage = () => {
setCurrentindex((previndex) => (prevlndex + 1) % images.length);
};


const prevlmage = () => {
setCurrentindex((prevlndex) => (prevlndex - 1 +images.length)% images.length);
};


return (
<div className="carousel-container">
<button className="prev" onClick={prevImage}>{</button>
<img src={images[currentlndex]} alt={'Slide ${currentlndex + 1}'} className="carousel-image"
/>
<button className="next" onClick={nextirnage}>}</button>
</div>
);
};


export default ImageCarousel;


irnagecarousel.css
/* src/ImageCarousel.css */
.carousel-container { display: flex;
align-items: center;
 
justify-content: center; position: relative;
max-width: 600px; margin: 0 auto; overflow: hidden; border: 2px solid #ddd; border-radius: lOpx;
}


.carousel-image { width: 100%; height: auto;
transition: transform 0.5s ease;
}


button {
position: absolute; top: 50%;
transform: translateY(-50%); background-color: rgba(0, 0, 0, 0.5); color: white;
border: none; padding: l 5px; cursor: pointer; font-size: 20px;
border-radius: 50%;
transition: background-color 0.3s ease;
}


button:hover {
background-color: rgba(0, 0, 0, 0.8);
}
 
.prev {
left: lOpx;
}


.next {
right: 1Opx;
}


app.JS
// src/App.js
import React from 'react'; import './App.css';
import ImageCarousel from './ImageCarousel';


function App() { return (
<div className="App">
<hl>Image Carousel in React</hl>
<ImageCarousel />
</div>
);
}


export default App;


## OUTPUT
![image](https://github.com/user-attachments/assets/913a6027-192d-4f75-a9bc-2962b7183c50)


## RESULT
The program for creating Image Carousel using React is executed successfully.
