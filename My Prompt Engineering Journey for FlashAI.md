# My Prompt Engineering Journey for FlashAI Using ChatGPT 3.5

## Introduction

This document outlines my journey through prompt engineering for FlashAI, leveraging ChatGPT 3.5. The primary objective was to input notes into the Large Language Model (LLM) and receive structured flashcards conducive to study and memorization.

## Methodology

### Source Material

The sample text used for generating flashcards, constant across all prompt iterations, detailed the etymology, description, habitat, and behavior of the eastern chipmunk, as sourced from [Wikipedia](https://en.wikipedia.org/wiki/Eastern_chipmunk).

### Prompt Version 1

**Prompt**: "Use \${text} to generate the front and back of \${selectedValue} flashcards. The front should be a question and the back should be the answer."

**Observations**:

- **Output**: Generated accurate flashcards but with varying structure and consistency.
- **Analysis**: The prompt needed refinement for more consistent output structuring.

### Prompt Version 2

**Prompt**: "Generate front and back content for a set of flashcards optimal for test preparation from the information: \${text}. Each flashcard should emphasize key concepts, with a question on the front and its corresponding answer on the back. Please provide the response in JSON format, where each flashcard is represented as an object with 'front' and 'back' as the components, like this: [{front: 'question', back: 'answer'}]. Ensure you produce exactly \${selectedValue} flashcard(s)."

**Observations**:

- **Output**: Led to a structured and predictable JSON format output, enhancing clarity and usability.
- **Analysis**: Specifying the output format as JSON significantly improved the structuring of the flashcards.

### Prompt Version 3

**Prompt**: "Transform the provided text into a structured set of flashcards, each designed to enhance test preparation efficiency. Construct each flashcard with a focus on essential ideas, framing a pertinent question on the front and its precise answer on the back. Format the output as a JSON array... Tailor the set to include exactly \${selectedValue} flashcards, optimizing for a comprehensive review of the material's most critical points."

**Observations**:

- **Output**: Produced high-quality flashcards with clear, engaging questions and concise, informative answers.
- **Analysis**: This version significantly improved the clarity, engagement, and educational value of the flashcards. Specifying the educational goal and desired structure guided the LLM to generate outputs that were immediately useful for studying.

## Key Improvements and Learnings

- **Clarity and Precision**: Specifying that flashcards focus on "essential ideas" improved relevance.
- **Contextual Relevance**: Framing the request around "test preparation efficiency" informed the nature of content needed.
- **Structured Output**: The JSON format example clarified expected output, ensuring consistent flashcard structure.
- **Engagement and Learning**: Suggestions to formulate thought-provoking questions and concise answers aligned with effective study practices.

## Future Directions

To protect my innovative prompt engineering work, I plan to explore strategies that prevent unauthorized use or tricking the AI into revealing proprietary methodologies.

## Conclusion

My prompt engineering journey with FlashAI and ChatGPT 3.5 highlighted the iterative process of refining prompts to achieve high-quality, educationally valuable outputs. This experience underscored the significant role of clear, detailed, and contextually informed prompts in leveraging AI capabilities for educational content creation.
