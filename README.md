# text-sentiment
// Import the necessary libraries
const Sentiment = require('sentiment');

/**
 * Analyzes the sentiment of a given text.
 * 
 * @param {string} text - The text to analyze.
 * @returns {string} - The sentiment of the text.
 */
function analyzeSentiment(text) {
  try {
    // Check if the text is a string
    if (typeof text !== 'string') {
      throw new TypeError('Text must be a string');
    }
    
    // Create a new instance of the Sentiment analyzer
    const sentiment = new Sentiment();
    
    // Analyze the sentiment of the text
    const result = sentiment.analyze(text);
    
    // Return the sentiment
    return result.score > 0 ? 'Positive' : result.score < 0 ? 'Negative' : 'Neutral';
  } catch (error) {
    // Log the error
    console.error(`Error: ${error.message}`);
    return 'Error';
  }
}
