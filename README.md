# Feedbot
???? Project Report: Recipe Chatbot using GPT-2
1. Project Overview

Project includes the creation of a domain-specific chatbot within the recipes and cooking domain. The chatbot enables users to create, find, and modify recipes based on their preference and ingredients. It is powered by a Hugging Face fine-tuned GPT-2 Transformer model, enabling it to generate free-text, conversational responses and recipe suggestions.

2. Dataset

The dataset used is the "Recipes Dataset: 64K Dishes" on Kaggle with over 64,000 recipes containing dense data such as:

Recipe names

Descriptions

Lists of ingredients

Step-by-step instructions

Categories and subcategories
The dataset was preprocessed and cleaned to remove duplicate data, fix encoding problems, and put it in uniformity across text fields. The cleaned text was combined into a unified "recipe story" format for GPT-2 fine-tuning.

3. Model Selection

The Hugging Face pre-trained GPT-2 model was selected because of its ability to generate coherent and contextually relevant natural language responses. GPT-2 is a causal language model, ideal for generative text-based tasks like recipe generation and chatbot dialogue.

4. Data Preprocessing and Tokenization

Tasks involved:

Text normalization and encoding fixes

Removal of empty or incomplete recipe entries

Combination of multiple columns into one training text feature

Division of data into training (90%) and test (10%) sets

Tokenization of text using GPT-2's tokenizer, adding a pad token (eos_token) for model compatibility

5. Model Fine-Tuning

The GPT-2 model was fine-tuned using the Hugging Face Trainer API with the following configuration:

Learning rate: 5e-5

Batch size: 2

Epochs: 3

Optimizer: AdamW

Evaluation strategy: Per epoch

Loss: Cross-entropy loss on next-token prediction

Early stopping and model checkpointing were used to optimize performance and prevent overfitting.

6. Evaluation

The chatbot's performance was both quantitatively and qualitatively tested:

Metrics: Perplexity and BLEU score were used to evaluate fluency and relevance of the output text.

Qualitative Testing: The chatbot was tested interactively using Gradio, evaluating its ability to respond naturally to inputs such as:

"Give me a vegan dessert recipe."

"How do I make pancakes with no eggs?"

"Suggest a quick chicken dinner."

7. Deployment

The chatbot was made available through a Gradio web interface, and users could input ingredients or meal types and receive real-time generated recipes and cooking directions.
Example exchange:

User: "Tell me a recipe with chicken and garlic."
Chatbot: "Here's one for you: Garlic Chicken Delight — sauté chicken breasts in olive oil, add minced garlic, lemon juice, and herbs."

8. Results and Insights

The fine-tuned GPT-2 model generated coherent and novel recipe texts from user input.

Evaluation showed low perplexity scores, implying good generalization.

Limitations were rare duplicate ingredients and truncated instructions — potential enhancements are large context windows or GPT-2-medium fine-tuning.

9. Conclusion

The project demonstrates the applicability of Transformer-based models in domain-conversational AI. The recipe chatbot exemplifies the capability of generative NLP models to assist users with creative and practical activities such as cooking, meal planning, and ingredient substitution.