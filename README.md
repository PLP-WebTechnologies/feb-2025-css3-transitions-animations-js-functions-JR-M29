# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Transitions and Animations</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <button id="animate-button">Animate!</button>
    <img id="animated-image" src="image.jpg" alt="Animated Image">
    <div id="user-preferences">
        <label for="background-color">Background Color:</label>
        <input type="color" id="background-color" value="#ffffff">
        <button id="save-preferences">Save Preferences</button>
    </div>

    <script src="script.js"></script>
</body>
</html>
```

style.css
```
#animated-image {
    width: 200px;
    height: 200px;
    transition: transform 0.5s ease-in-out;
}

#animated-image.animate {
    animation: spin 2s linear;
}

@keyframes spin {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(360deg);
    }
}

#animate-button {
    transition: background-color 0.3s ease-in-out;
}

#animate-button:hover {
    background-color: #007bff;
    color: #fff;
}
```

script.js
```
// Store user preferences in localStorage
document.getElementById('save-preferences').addEventListener('click', () => {
    const backgroundColor = document.getElementById('background-color').value;
    localStorage.setItem('backgroundColor', backgroundColor);
    document.body.style.background = backgroundColor;
});

// Retrieve user preferences from localStorage
const storedBackgroundColor = localStorage.getItem('backgroundColor');
if (storedBackgroundColor) {
    document.body.style.background = storedBackgroundColor;
    document.getElementById('background-color').value = storedBackgroundColor;
}

// Trigger animation on button click
document.getElementById('animate-button').addEventListener('click', () => {
    document.getElementById('animated-image').classList.add('animate');
    setTimeout(() => {
        document.getElementById('animated-image').classList.remove('animate');
    }, 2000);
});

