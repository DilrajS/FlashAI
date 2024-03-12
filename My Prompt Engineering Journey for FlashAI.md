# My Prompt Engineering Journey for FlashAI using OpenAI's GPT

![FlashAI Prompt Engineering](images/FlashAI_Prompt.gif)

## Introduction

This document outlines my journey through prompt engineering for FlashAI, leveraging ChatGPT 3.5. The primary objective was to input notes into the Large Language Model (LLM) and receive structured flashcards conducive to study and memorization.

## Methodology

### Source Material

The sample text used for generating flashcards, constant across all prompt iterations, detailed the etymology, description, habitat, and behavior of the eastern chipmunk, as sourced from [Wikipedia](https://en.wikipedia.org/wiki/Eastern_chipmunk). Here is the text in detail:

>"The name "chipmunk" comes from the Ojibwe word ᐊᒋᑕᒨ ajidamoo (or possibly ajidamoonh, the same word in the Ottawa dialect of Ojibwe), which translates literally as "one who descends trees headlong." [9] First described by Mark Catesby in his 1743 The Natural History of Carolina, Florida, and the Bahama Islands, the chipmunk was eventually classified as Sciurus striatus by Linnaeus, meaning "striped squirrel" in Latin. [10][11] The scientific name was changed to Tamias striatus, meaning "striped steward," by Johann Illiger in 1811. [12]

>A small species, it reaches about 30 cm (12 in) in length including the tail, and a weight of 66–150 g (2.3–5.3 oz). [13] It has reddish-brown fur on its upper body and five dark brown stripes contrasting with light brown stripes along its back, ending in a dark tail. It has lighter fur on the lower part of its body. It has a tawny stripe that runs from its whiskers to below its ears, and light stripes over its eyes. It has two fewer teeth than other chipmunks and four toes each on the front legs, but five toes on the hind legs. [14] The chipmunk's appearance "remains consistent throughout life. There is no external difference in appearance between the sexes except the obvious anatomical characteristics of the genitalia during periods of fertility. Molt occurs once or twice annually, during May or June and sometimes again in October. Both albino and melanistic specimens have been observed, but without geographical regularity." [12]

>The eastern chipmunk lives in deciduous wooded areas and urban parks throughout the eastern United States and southern Canada. It prefers locations with rocky areas, brush or log piles, and shrubs to provide cover. [15]

>The eastern chipmunk can climb trees well, but constructs underground nests with extensive tunnel systems, often with several entrances. To hide the construction of its burrow, the eastern chipmunk is argued by some to carry soil to a different location in its cheek pouches. [16] However, recorded observations of chipmunks carrying soil in their cheek pouches are extremely limited. John Burroughs is noted as having written that "I used to think that the chipmunk carried away the soil in his cheek pouches, and have so-stated in one of my books [Riverby, 1894], but I am now certain that he does not—only his food stores are thus carried." [17] Chipmunks also line their burrows with leaves, rocks, sticks, and other material, making the burrows even harder to see. [16] "The vocal repertoire of the chipmunk consists of five more or less stereotyped sounds: the chip, the chuck, the trills, the whistle or squeal, and chatter." [18] The chipmunks' trilling has been measured to occur at the rate of 130 trills per minute. [14]"


### Prompt Version 1

**Prompt**: "Use \${text} to generate the front and back of \${selectedValue} flashcards. The front should be a question and the back should be the answer."

*Output*:
>Front of Flashcard: What is the origin of the name "chipmunk"?
>Back of Flashcard: The name "chipmunk" comes from the Ojibwe word ᐊᒋᑕᒨ ajidamoo, which translates as "one who descends trees headlong."

>Front of Flashcard: What is the scientific name of the chipmunk and its meaning?
>Back of Flashcard: The scientific name is Tamias striatus, meaning "striped steward."

>Front of Flashcard: What are some characteristics of the eastern chipmunk's appearance?
>Back of Flashcard: It has reddish-brown fur on its upper body, dark brown stripes contrasting with light brown stripes along its back, and a tawny stripe that runs from its whiskers to below its ears.

>Front of Flashcard: Where does the eastern chipmunk prefer to live?
>Back of Flashcard: It prefers deciduous wooded areas and urban parks throughout the eastern United States and southern Canada, particularly those with rocky areas, brush, or log piles for cover.

>Front of Flashcard: How does the eastern chipmunk construct its nests?
>Back of Flashcard: It constructs underground nests with extensive tunnel systems, often with several entrances, and lines them with leaves, rocks, sticks, and other materials.


**Observations**:

- **Output**: Generated accurate flashcards but with varying structure and consistency.
- **Analysis**: The prompt needed refinement for more consistent output structuring.

### Prompt Version 2

**Prompt**: "Generate front and back content for a set of flashcards optimal for test preparation from the information: \${text}. Each flashcard should emphasize key concepts, with a question on the front and its corresponding answer on the back. Please provide the response in JSON format, where each flashcard is represented as an object with 'front' and 'back' as the components, like this: [{front: 'question', back: 'answer'}]. Ensure you produce exactly \${selectedValue} flashcard(s)."

*Output*: 
>[
>
    {
        "front": "What is the etymology of the name 'chipmunk'?",
        "back": "The name 'chipmunk' comes from the Ojibwe word ᐊᒋᑕᒨ ajidamoo, which translates literally as 'one who descends trees headlong.'"
    },
>
    {
        "front": "Who first described the chipmunk?",
        "back": "Mark Catesby described the chipmunk in his 1743 work 'The Natural History of Carolina, Florida, and the Bahama Islands.'"
    },
>
    {
        "front": "What is the scientific classification of the chipmunk according to Linnaeus?",
        "back": "Linnaeus classified the chipmunk as Sciurus striatus, meaning 'striped squirrel' in Latin."
    },
>
    {
        "front": "What changes did Johann Illiger make to the scientific name of the chipmunk?",
        "back": "Johann Illiger changed the scientific name to Tamias striatus, meaning 'striped steward.'"
    },
>
    {
        "front": "Describe the appearance of the chipmunk.",
        "back": "The chipmunk has reddish-brown fur on its upper body with five dark brown stripes along its back, ending in a dark tail. It has a tawny stripe from its whiskers to below its ears and light stripes over its eyes."
    },
>
    {
        "front": "Where does the eastern chipmunk live?",
        "back": "The eastern chipmunk lives in deciduous wooded areas and urban parks throughout the eastern United States and southern Canada."
    },
>
    {
        "front": "What type of habitat does the eastern chipmunk prefer?",
        "back": "The eastern chipmunk prefers locations with rocky areas, brush or log piles, and shrubs to provide cover."
    }
>]


**Observations**:

- **Output**: Led to a structured and predictable JSON format output, enhancing clarity and usability.
- **Analysis**: Specifying the output format as JSON significantly improved the structuring of the flashcards.

### Prompt Version 3

**Prompt**: "Transform the provided text into a structured set of flashcards, each designed to enhance test preparation efficiency. Your task is to distill key concepts and information from the following material: ${text}. Construct each flashcard with a focus on essential ideas, framing a pertinent question on the front and its precise answer on the back.

Please format the output as a JSON array, where each element represents a single flashcard in the form of an object with 'front' and 'back' keys. The 'front' should contain the question, and the 'back' should provide the answer. Tailor the set to include exactly ${selectedValue} flashcards, optimizing for a comprehensive review of the material's most critical points.

Example of desired output format:
[
  {"front": "What is the principle of X?", "back": "The principle of X is ..."},
  {"front": "How does Y affect Z?", "back": "Y influences Z by ..."}
]
Ensure the questions are formulated to provoke thought and engagement, facilitating effective memorization and understanding of the subject matter. The answers should be concise yet informative, directly addressing the questions posed.
"

*Output*: 
>[
>
      {
        "front": "What is the etymology of the name 'chipmunk'?",
        "back": "The name 'chipmunk' comes from the Ojibwe word ᐊᒋᑕᒨ ajidamoo, meaning 'one who descends trees headlong.'"
      },
>
      {
        "front": "Who first described the chipmunk?",
        "back": "Mark Catesby first described the chipmunk in his 1743 work 'The Natural History of Carolina, Florida, and the Bahama Islands.'"
      },
>
      {
        "front": "What does the scientific name 'Sciurus striatus' mean?",
        "back": "The scientific name 'Sciurus striatus' means 'striped squirrel' in Latin."
      },
>
      {
        "front": "Describe the appearance of the eastern chipmunk.",
        "back": "The eastern chipmunk has reddish-brown fur on its upper body, five dark brown stripes along its back, and a tawny stripe from its whiskers to below its ears. It has lighter fur on its lower body."
      },
>
      {
        "front": "Where does the eastern chipmunk live?",
        "back": "The eastern chipmunk lives in deciduous wooded areas and urban parks throughout the eastern United States and southern Canada."
      },
>
      {
        "front": "What is the behavior of the eastern chipmunk regarding nesting?",
        "back": "The eastern chipmunk constructs underground nests with extensive tunnel systems, often with several entrances. It lines its burrows with leaves, rocks, sticks, and other material."
      },
>
      {
        "front": "What is the vocal repertoire of chipmunks?",
        "back": "The vocal repertoire of chipmunks consists of five sounds: chip, chuck, trills, whistle or squeal, and chatter. Their trilling can occur at a rate of 130 trills per minute."
      }
>]


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
