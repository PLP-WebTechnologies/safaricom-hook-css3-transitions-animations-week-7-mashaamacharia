### **Assignment: Building an Interactive and Dynamic Web Page**  

#### **Objective**  
Create a visually engaging and interactive webpage that utilizes **CSS3 transitions and animations**, **advanced JavaScript functions** (including scope, parameters, and return values), and combines **CSS animations with JavaScript** to create dynamic user interactions.  

---

### **Part 1: CSS3 Transitions and Animations**  
1. **Task**:  
   - Use **CSS transitions** to create smooth effects on hover or focus (e.g., buttons that change color or grow).  
   - Use **CSS animations** with `@keyframes` to create dynamic effects like fading, sliding, or rotating.  

2. **Requirements**:  
   - At least **two elements** must include hover or focus transitions.  
   - At least **two animations** must be created using `@keyframes` (e.g., an animated banner or an animated loading spinner).  

---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS3 Transitions and Animations</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <button class="transition-button">Hover Over Me</button>
    <div class="animated-banner">Welcome to Our Website!</div>
    <div class="loading-spinner"></div>
</body>
</html>


/* Transition Example */
.transition-button {
    background-color: #4CAF50;
    color: white;
    padding: 15px 32px;
    text-align: center;
    font-size: 16px;
    border: none;
    cursor: pointer;
    transition: background-color 0.3s ease, transform 0.3s ease;
}

.transition-button:hover {
    background-color: #45a049;
    transform: scale(1.1);
}

/* Animation Example */
.animated-banner {
    width: 100%;
    padding: 20px;
    background-color: #2196F3;
    color: white;
    text-align: center;
    animation: slideIn 3s ease-in-out infinite alternate;
}

@keyframes slideIn {
    from {
        transform: translateX(-100%);
    }
    to {
        transform: translateX(0);
    }
}

/* Loading Spinner */
.loading-spinner {
    border: 16px solid #f3f3f3;
    border-top: 16px solid #3498db;
    border-radius: 50%;
    width: 120px;
    height: 120px;
    animation: spin 2s linear infinite;
    margin: 20px auto;
}

@keyframes spin {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(360deg);
    }
}



### **Part 2: JavaScript Functions**  
1. **Task**:  
   - Write JavaScript functions to handle interactivity on the webpage.  
   - Utilize **parameters**, **return values**, and demonstrate an understanding of **scope**.  

2. **Requirements**:  
   - Write at least **three functions**:  
     - A function with parameters and return values (e.g., calculate a value like the area of a rectangle based on user input).  
     - A function that demonstrates the concept of scope (local vs. global variables).  
     - A function to toggle a CSS class that applies an animation (e.g., toggling a "hidden" class for a modal).  

---
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Functions</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Calculate Rectangle Area</h1>
    <label for="length">Length:</label>
    <input type="number" id="length">
    <label for="width">Width:</label>
    <input type="number" id="width">
    <button onclick="displayArea()">Calculate Area</button>
    <p id="area-result"></p>

    <h1>Toggle Modal</h1>
    <button onclick="toggleModal()">Open Modal</button>
    <div id="modal" class="modal hidden">
        <div class="modal-content">
            <span class="close" onclick="toggleModal()">&times;</span>
            <p>This is a modal window.</p>
        </div>
    </div>

    <script src="scripts.js"></script>
</body>
</html>

/* Modal Styles */
.modal {
    display: none;
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
    background-color: white;
    margin: 15% auto;
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
}

.hidden {
    display: none;
}

// Function to calculate the area of a rectangle
function calculateArea(length, width) {
    return length * width;
}

// Function to display the area
function displayArea() {
    const lengthInput = document.getElementById('length');
    const widthInput = document.getElementById('width');
    const result = document.getElementById('area-result');

    const length = parseFloat(lengthInput.value);
    const width = parseFloat(widthInput.value);

    if (isNaN(length) || isNaN(width)) {
        result.textContent = 'Please enter valid numbers for length and width.';
    } else {
        const area = calculateArea(length, width);
        result.textContent = `The area of the rectangle is ${area}.`;
    }
}

// Function to demonstrate scope
function scopeExample() {
    var globalVar = 'I am a global variable';

    function innerFunction() {
        var localVar = 'I am a local variable';
        console.log(globalVar); // Accessible
        console.log(localVar);  // Accessible
    }

    innerFunction();
    console.log(globalVar); // Accessible
    // console.log(localVar);  // Unaccessible, will cause an error
}

// Function to toggle modal visibility
function toggleModal() {
    const modal = document.getElementById('modal');
    modal.classList.toggle('hidden');
}


### **Part 3: Combining CSS Animations with JavaScript**  
1. **Task**:  
   - Use JavaScript to trigger or control CSS animations dynamically.  

2. **Requirements**:  
   - Create an interactive element (e.g., a button, card, or slider) that triggers an animation when clicked.  
   - Dynamically add or remove CSS classes to control the animation.  
   - Ensure that the animation resets properly when triggered multiple times.  

---
