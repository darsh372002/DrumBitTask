
# 🥁 Drum Kit Web App

This is an interactive **Drum Kit** web app using **HTML, CSS, and JavaScript**. Press keyboard keys or click on drum buttons to play drum sounds.

## 📁 Project Structure

```
DrumBeatTAsk/
├── index.html          # Webpage structure
├── styles.css          # Styling for layout and buttons
├── index.js            # JavaScript logic for sound and animation
├── images/
│   └── images.jpg      # Background or theme image
└── sounds/
    ├── crash.mp3
    ├── kick-bass.mp3
    ├── snare.mp3
    ├── tom-1.mp3
    ├── tom-2.mp3
    ├── tom-3.mp3
    └── tom-4.mp3
```

---

## 📄 File Descriptions

### `index.html`
- Contains the structure of the drum kit with `<button>` elements for each drum sound.
- Each button is labeled with a character (`w`, `a`, `s`, `d`, `j`, `k`, `l`) which corresponds to a sound.
- Connected to `styles.css` and `index.js`.

### `styles.css`
- Styles the drum buttons and page layout.
- Key features:
  - Adds shadow and border radius to buttons.
  - Visually responsive and centered layout.
  - Animations applied using the `pressed` class for a click effect.

### `index.js`
- The core logic for the drum kit interactivity.
- Key functionalities:

```javascript
// Event listener for all drum buttons
for (var i = 0; i < drumButtons.length; i++) {
    drumButtons[i].addEventListener("click", function () {
        var buttonInnerHTML = this.innerHTML;
        playSound(buttonInnerHTML);
        buttonAnimation(buttonInnerHTML);
    });
}

// Event listener for keyboard keypress
document.addEventListener("keydown", function (event) {
    playSound(event.key);
    buttonAnimation(event.key);
});

// Function to play drum sound based on key
function playSound(key) {
    switch (key) {
        case "w": var tom1 = new Audio("sounds/tom-1.mp3"); tom1.play(); break;
        case "a": var tom2 = new Audio("sounds/tom-2.mp3"); tom2.play(); break;
        case "s": var tom3 = new Audio("sounds/tom-3.mp3"); tom3.play(); break;
        case "d": var tom4 = new Audio("sounds/tom-4.mp3"); tom4.play(); break;
        case "j": var snare = new Audio("sounds/snare.mp3"); snare.play(); break;
        case "k": var crash = new Audio("sounds/crash.mp3"); crash.play(); break;
        case "l": var kick = new Audio("sounds/kick-bass.mp3"); kick.play(); break;
        default: console.log(key);
    }
}

// Animation function adds and removes CSS class
function buttonAnimation(currentKey) {
    var activeButton = document.querySelector("." + currentKey);
    if (activeButton) {
        activeButton.classList.add("pressed");
        setTimeout(function () {
            activeButton.classList.remove("pressed");
        }, 100);
    }
}
```

---

## ✅ Features

- Realistic drum sounds mapped to keyboard keys.
- Button animation when clicked or key pressed.
- Easy to extend and customize.
