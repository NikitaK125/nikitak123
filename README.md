# nikitak123
const apiKey = 'YOUR_API_KEY'; // Replace with your Google Translate API key

const translateButton = document.getElementById('translateButton');
const inputText = document.getElementById('inputText');
const outputText = document.getElementById('outputText');
const sourceLanguageSelect = document.getElementById('sourceLanguage');
const targetLanguageSelect = document.getElementById('targetLanguage');

translateButton.addEventListener('click', () => {
  const textToTranslate = inputText.value;
  const sourceLanguage = sourceLanguageSelect.value;
  const targetLanguage = targetLanguageSelect.value;

  const params = {
    key: apiKey,
    q: textToTranslate,
    source: sourceLanguage,
    target: targetLanguage
  };

  fetch(`https://translate.googleapis.com/translate_a/single?${new URLSearchParams(params).toString()}`)
    .then(response => response.json())
    .then(data => {
      const translatedText = data[0][0][0];
      outputText.textContent = translatedText;
    })
    .catch(error => {
      console.error('Error:', error);
      outputText.textContent = 'An error occurred during translation.';
    });
});const apiKey = 'YOUR_API_KEY'; // Replace with your Google Translate API key

const translateButton = document.getElementById('translateButton');
const inputText = document.getElementById('inputText');
const outputText = document.getElementById('outputText');
const sourceLanguageSelect = document.getElementById('sourceLanguage');
const targetLanguageSelect = document.getElementById('targetLanguage');

translateButton.addEventListener('click', () => {
  const textToTranslate = inputText.value;
  const sourceLanguage = sourceLanguageSelect.value;
  const targetLanguage = targetLanguageSelect.value;

  const params = {
    key: apiKey,
    q: textToTranslate,
    source: sourceLanguage,
    target: targetLanguage
  };

  fetch(`https://translate.googleapis.com/translate_a/single?${new URLSearchParams(params).toString()}`)
    .then(response => response.json())
    .then(data => {
      const translatedText = data[0][0][0];
      outputText.textContent = translatedText;
    })
    .catch(error => {
      console.error('Error:', error);
      outputText.textContent = 'An error occurred during translation.';
    });
});
