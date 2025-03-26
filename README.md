# Heart Animation Overlay

This project demonstrates an interactive web-based heart animation overlay. When the user clicks on the overlay text, the text disappears, and heart emojis start floating upwards, creating a visually appealing effect. The hearts are dynamically created and animated using JavaScript and CSS.

## Components

### HTML

The HTML structure consists of a container `div` that encapsulates an image and an overlay. The overlay includes clickable text that triggers the animation.

- **Container (`div#heart-animation`)**: Serves as the main wrapper with specific dimensions and overflow control, ensuring the animation remains confined to this area.
- **Image (`img`)**: Serves as a background, filling the entire container to provide a thematic backdrop for the overlay and animation.
- **Overlay Text (`div#overlay-text`)**: Positioned absolutely within the container to cover the image, featuring a semi-transparent background and centered text, which serves as the interactive element for starting the animation.

### CSS

The CSS is primarily inline within the `style` attributes and dynamically injected via JavaScript:
- **Container Styles**: Ensure the container is centered horizontally with `margin: auto`.
- **Overlay Styles**: Ensure the text is centered both vertically and horizontally using Flexbox.
- **Heart Styles**: Defined within the injected `<style>` tag in the JavaScript, dictating the animation properties.

### JavaScript

The JavaScript code is encapsulated in an immediately invoked function expression (IIFE) to avoid polluting the global namespace.

- **Event Listeners**: An event listener waits for the document to be fully loaded before executing. Another listener is attached to the overlay text for the click event.
- **Animation Logic**:
  - **Overlay Click**: Hides the overlay text and ensures the animation starts only once.
  - **Heart Creation**: A function `createHeart` is invoked repeatedly using `setInterval`. Each call creates a new `div` element styled to look like a heart, which is then animated to float upwards and fade out.
  - **CSS Injection**: Adds necessary styles for the heart animation to the document's `<head>`, defining keyframes for the floating effect.

## Keyframe Animation

The heart's motion is controlled by the `float` keyframe, which moves the heart from the bottom of the container upwards while gradually changing its opacity from fully opaque to completely transparent.

## Usage

To use this overlay in your project:
1. Include the HTML markup in your document.
2. Ensure the JavaScript code is loaded either in the `<head>` with a `defer` attribute or just before the closing `</body>` tag to prevent DOM loading issues.

This setup creates a simple yet effective interaction model, suitable for web pages that require a touch of animation to engage users.
