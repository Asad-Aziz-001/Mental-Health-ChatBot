# **🎯 Build a Domain-Specific Q&A Chatbot Using Python**

# **Live App Link 🔗:**
https://mental-health-chatbot-umbkqjvhza7g9bbtbzjyc3.streamlit.app/

# **1. Load the FAQ Dataset**

The chatbot starts by reading a CSV file that contains frequently asked questions and their answers.

It cleans up the column names to ensure consistency.

If the expected columns (pattern for questions, response for answers) are not present, it stops and shows an error.

# **2. Natural Language Processing Setup**

It downloads necessary NLTK resources for tokenizing text, removing stopwords, and lemmatizing words.

The stopwords list is loaded to remove common words like “the”, “is”, “and” which do not carry meaning.

A lemmatizer is prepared to reduce words to their base form (e.g., “running” → “run”).

# **3. Preprocessing the Questions**

Each question from the dataset is converted to lowercase.

It is tokenized into words.

Non-alphanumeric words and stopwords are removed.

Remaining words are lemmatized and joined back into a cleaned sentence.

# **4. Vectorization**

The cleaned questions are converted into numerical form using TF-IDF Vectorization.

This allows the chatbot to compare user queries with stored questions based on keyword importance.

# **5. Matching Logic**

When the user asks something:

The question is preprocessed the same way as the dataset questions.

Cosine similarity is calculated between the user’s query and all stored questions.

If the similarity score is above a threshold (0.3 in your code), the most relevant stored answer is returned.

If no match is strong enough, the chatbot tries to fetch a brief answer from Wikipedia.

If Wikipedia also fails, it responds with a fallback message saying it couldn’t find the answer.

# **6. Streamlit Web Interface**

The chatbot is deployed as an interactive Streamlit web app.

A sidebar explains the chatbot’s purpose and shows example questions from the dataset.

The main chat window displays the conversation history with a chat-like UI using streamlit-chat.

The user can type a question in the chat input at the bottom, and the chatbot responds instantly.

