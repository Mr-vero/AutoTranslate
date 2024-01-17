# AutoTranslate - Seamless Website Translation

Welcome to AutoTranslate, a versatile JavaScript module designed for seamless and high-quality auto-translation of entire websites. This module seamlessly integrates with SeamlessM4T, a unified translation model that facilitates effortless communication across diverse linguistic communities. Say goodbye to the complexities of setup and external localization files – AutoTranslate makes website translation a breeze.

## Features

- **Unified Translation Model:** SeamlessM4T provides a unified model that covers various translation tasks, fostering effortless text translation.

- **Auto-Translation:** Enable automatic translation of entire websites, making it an ideal solution for projects requiring dynamic and on-the-fly translation without extensive configuration.

- **Caching for Performance:** Translated data is intelligently stored in an IndexedDB database, significantly improving the speed of subsequent translations and minimizing reliance on external translation services.

- **Dynamic Translation Tasks:** The `translateText` function leverages SeamlessM4T to perform dynamic text translation.

## Get Started

### CDN Usage

Include the following script tag in your HTML file to use the AutoTranslate module directly from the CDN:

```html
<!-- Replace 'v.1.0.0' with the desired version -->
<script src="https://cdn.jsdelivr.net/gh/Mr-vero/AutoTranslate@v.1.0.0/dist/autoTranslate.js"></script>
```

Now, proceed with the module initialization and usage as described in the README.

### NPM Usage

Install the `js-auto-translate` package using npm:

```bash
npm i js-auto-translate
```

Then, import the `translateText` or `autoTranslate` function from the module in your JavaScript file:

```javascript
// Import the translation function
import { translateText, autoTranslate } from "js-auto-translate";

// Rest of your code...
```

Now, use the `translateText` function and other features of the AutoTranslate module as described in the README.

Adjust the version in the CDN link or npm package version according to your project's requirements.

Feel free to reach out if you have any questions or encounter issues during the integration process.

## Usage

1. Import the module and initialize the translation cache using the `initialize` method.
2. Utilize the `translateText` function to seamlessly translate text content, taking advantage of SeamlessM4T's unified translation capabilities.
3. Achieve automatic translation of elements on the website by specifying a target language.

## Example Usage

Customize class using `translateText`
```javascript
// Import the translation function
import { translateText } from "./autoTranslate.js";

// Function to translate and update text content of elements with a specific class
async function translateAndUpdateElements(targetLanguage) {
  // Find all elements with the "autotranslate" class
  const elementsToTranslate = document.querySelectorAll(".autotranslate");

  // Translate and update text content of each element
  for (const element of elementsToTranslate) {
    const originalText = element.innerText.trim();

    // Skip empty elements
    if (!originalText) {
      continue;
    }

    try {
      // Translate the text using SeamlessM4T
      const translatedText = await translateText(
        originalText,
        targetLanguage,
      );

      // Update the text content of the element with the translated text
      element.innerText = translatedText;
    } catch (error) {
      console.error("Translation error:", error);
    }
  }
}

// Automatically translate when the DOM content is loaded
document.addEventListener("DOMContentLoaded", async () => {
  const targetLanguage = "Mandarin Chinese"; // Replace with the target language code
  await translateAndUpdateElements("English",targetLanguage);
});
```

Easy installation with `autoTranslate`
```javascript
import { autoTranslate } from "https://cdn.jsdelivr.net/gh/Mr-vero/AutoTranslate@v.1.0.1/dist/autoTranslate.js";

// Automatically translate when the DOM content is loaded
document.addEventListener("DOMContentLoaded", async () => {
  const targetLanguage = "Thai"; // Replace with the target language code
  await autoTranslate("English",targetLanguage);
});
```

## Supported Languages

The auto-translation module currently supports a variety of languages, including but not limited to:


The auto-translation module currently supports the following languages:

- Bengali
- Catalan
- Czech
- Danish
- Dutch
- English
- Estonian
- Finnish
- French
- German
- Hindi
- Indonesian
- Italian
- Japanese
- Korean
- Maltese
- Mandarin Chinese (Selected)
- Modern Standard Arabic
- Northern Uzbek
- Polish
- Portuguese
- Romanian
- Russian
- Slovak
- Spanish
- Swahili
- Swedish
- Tagalog
- Telugu
- Thai
- Turkish
- Ukrainian
- Urdu
- Vietnamese
- Welsh
- Western Persian

## To Do Next

1. **Optimize Translation Caching:** Explore potential optimizations for the translation caching mechanism to further enhance performance.

2. **Documentation Updates:** Ensure that the README file is kept up-to-date with the latest information on how to use the module and any new features that are added.

3. **Bug Fixes:** Address any reported bugs or issues to maintain a stable and reliable auto-translation experience.

## Contribution

Contributions to the project are welcome! If you'd like to contribute, follow the guidelines in the README. I appreciate your help in enhancing the functionality and usability of the auto-translation module. If you have ideas or improvements to contribute, please follow the contribution guidelines mentioned in the README file.

**Note:** The speech function has been removed as per the user's request to streamline the translation process. If you have any questions or concerns, feel free to reach out through the repository's issue tracker.

