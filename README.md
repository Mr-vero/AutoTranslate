**Description:**

The `AutoTranslate` is a versatile JavaScript module designed for seamless and high-quality auto-translation of entire websites. It seamlessly integrates with SeamlessM4T, a unified translation model facilitating effortless communication across diverse linguistic communities. The module intelligently utilizes the IndexedDB API for efficient caching, ensuring fast and reliable translation services without the need for complex setup or external localization files.

**Features:**

- **Unified Translation Model:** SeamlessM4T provides a unified model that covers various translation tasks, fostering effortless text translation.

- **Auto-Translation:** The module enables automatic translation of entire websites, making it an ideal solution for projects requiring dynamic and on-the-fly translation without the need for extensive configuration.

- **Caching for Performance:** Translated data is intelligently stored in an IndexedDB database, significantly improving the speed of subsequent translations and minimizing reliance on external translation services.

- **Dynamic Translation Tasks:** The `translateText` function leverages SeamlessM4T to perform dynamic text translation.

**Usage:**

1. Import the module and initialize the translation cache using the `initialize` method.
2. Utilize the `translateText` function to seamlessly translate text content, taking advantage of SeamlessM4T's unified translation capabilities.
3. Achieve automatic translation of elements on the website by specifying a target language.

**Example Usage:**

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
  await translateAndUpdateElements(targetLanguage);
});
```

**Supported Languages:**

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

**To Do Next:**

1. **Optimize Translation Caching:** Explore potential optimizations for the translation caching mechanism to further enhance performance.

2. **Documentation Updates:** Ensure that the README file is kept up-to-date with the latest information on how to use the module and any new features that are added.

3. **Bug Fixes:** Address any reported bugs or issues to maintain a stable and reliable auto-translation experience.

Contributions and suggestions are welcome to help enhance the functionality and usability of the auto-translation module. If you have ideas or improvements to contribute, please follow the contribution guidelines mentioned in the README file.

**Contribution:**

Contributions to the project are welcome! If you'd like to contribute, follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and ensure that the code is well-documented.
4. Test your changes thoroughly.
5. Submit a pull request, providing a clear description of your changes.

**Note:** The speech function has been removed as per the user's request to streamline the translation process. If you have any questions or concerns, feel free to reach out through the repository's issue tracker.
