# 01. AI & LLM Fundamentals
## 1.1 Artificial Intelligence (AI)

Artificial Intelligence (AI) is a field of computer science focused on building systems capable of performing tasks that typically require human intelligence.

These tasks include:
- Understanding human language.
- Recognizing images and objects.
- Learning from information.
- Making predictions and decisions.
- Solving problems.
- Generating new content.

**Examples:**
- Voice assistants.
- Facial recognition.
- Recommendation systems.
- Self-driving vehicles.
- ChatGPT.

AI is the broad field under which Machine Learning, Deep Learning and Generative AI are commonly studied.

---

## 1.2 Machine Learning (ML)

Machine Learning is a subset of AI in which systems learn patterns from data and use those patterns to make predictions or decisions without requiring every rule to be explicitly programmed.

### Traditional Programming vs Machine Learning

**Traditional Programming:**

A developer writes rules that determine how the system behaves.

Input + Rules → Output

Example: A program marks an email as spam when it contains predefined suspicious words.

**Machine Learning:**

An algorithm learns patterns from training data and produces a trained model.

Training Data + Learning Algorithm → Trained Model

The trained model can then process new inputs and generate predictions.

### How Machine Learning Works

1. Collect relevant data.
2. Prepare and clean the data.
3. Select a suitable ML algorithm.
4. Train the model using the data.
5. Evaluate its performance.
6. Use the trained model to make predictions.

### Types of Machine Learning

**1. Supervised Learning**

The model learns from labelled examples.

Examples:
- Spam email classification.
- House price prediction.
- Fraud detection.

**2. Unsupervised Learning**

The model discovers patterns or groups in data without predefined labels.

Examples:
- Customer segmentation.
- Grouping similar documents.
- Anomaly detection.

**3. Reinforcement Learning**

An agent learns through interactions with an environment, receiving rewards or penalties for its actions.

Examples:
- Game-playing systems.
- Robotics.
- Some AI model training techniques.

---

## 1.3 Deep Learning (DL)

Deep Learning is a subset of Machine Learning that uses artificial neural networks with multiple layers to learn complex patterns from data.

### What is a Neural Network?

A neural network is a computational model loosely inspired by the structure of biological neural networks.

It consists of interconnected computational units called neurons.

Its main components include:

- Input Layer: Receives input data.
- Hidden Layers: Process information and learn patterns.
- Output Layer: Produces the final result.
- Weights and Biases: Parameters adjusted during training.
- Activation Functions: Introduce non-linearity into the network.

### Conceptual Architecture

Input Layer → Hidden Layers → Output Layer

### Why Deep Learning?

Traditional ML often depends on manually designed features.

Deep Learning can automatically learn useful representations from large amounts of data.

### Applications

- Image recognition.
- Speech recognition.
- Natural Language Processing (NLP).
- Computer vision.
- Large Language Models (LLMs).
- Image and video generation.

Modern LLMs are predominantly built using Deep Learning.

---

## 1.4 Generative AI (GenAI)

Generative AI refers to AI systems capable of generating new content based on patterns learned from training data.

Unlike systems designed primarily to classify or predict, generative models can produce new outputs.

### Types of Generated Content

| Type | Examples |
|---|---|
| Text | ChatGPT, Claude |
| Images | DALL-E, Stable Diffusion |
| Audio | Speech and music generation |
| Video | AI-generated videos |
| Code | Code generation and completion |

### How Generative AI Works (High Level)

1. A model is trained on large amounts of data.
2. It learns patterns and representations from that data.
3. A user provides an input or prompt.
4. The model generates an output based on the learned patterns and the input.

### Common Applications

- AI chatbots.
- Document summarization.
- Content generation.
- Code assistants.
- Question answering.
- Information extraction.
- Conversational applications.

---

## 1.5 Relationship Between AI, ML, DL and GenAI

These terms are related but do not mean the same thing.

Conceptual hierarchy:

- Artificial Intelligence: The broader field.
  - Machine Learning: Systems learning patterns from data.
    - Deep Learning: Machine Learning using multi-layer neural networks.
      - Modern LLMs: Deep learning models for language tasks.

Generative AI is a broader category of AI systems that generate content. Modern generative AI predominantly uses Deep Learning, although not every generative AI technique must be deep learning.

---

## 1.6 Traditional AI vs Generative AI

| Traditional Predictive AI | Generative AI |
|---|---|
| Classifies spam emails | Writes emails |
| Predicts customer churn | Generates customer reports |
| Detects fraudulent transactions | Explains suspicious activity |
| Recommends products | Creates conversational shopping assistants |
| Detects manufacturing defects | Generates defect analysis reports |

Both approaches can be combined in the same application.

---

## 1.7 Relevance to AI Engineering

As an AI-enabled Software Engineer, understanding these differences helps determine which technology is appropriate for a particular problem.

Examples:

| Requirement | Relevant Technology |
|---|---|
| Detect fraudulent transactions | Machine Learning |
| Recognize objects in images | Deep Learning |
| Generate a report from user input | Generative AI |
| Answer questions about company documents | LLM + RAG |
| Execute application operations using natural language | LLM + Tool Calling |
| Perform multi-step tasks autonomously | AI Agents |

Our primary focus is on Generative AI, LLMs and the engineering techniques used to integrate them into software applications.

---

## Key Takeaways

1. AI is the broader field of building intelligent systems.
2. Machine Learning enables systems to learn patterns from data.
3. Deep Learning uses multi-layer neural networks.
4. Generative AI creates new content.
5. Modern LLMs predominantly use Deep Learning.
6. AI engineering focuses on applying these capabilities to real-world software products.

---

## Interview Questions

**Q1. What is the difference between AI and Machine Learning?**

AI is the broader field of building intelligent systems. Machine Learning is a subset of AI where systems learn patterns from data.

**Q2. What is Deep Learning?**

Deep Learning is a subset of Machine Learning that uses multi-layer neural networks to learn complex patterns.

**Q3. What is Generative AI?**

Generative AI refers to systems that generate new content such as text, images, audio, video or code based on learned patterns.

**Q4. Are all AI systems Generative AI?**

No. AI also includes predictive, classification, recommendation and rule-based systems.

**Q5. Are LLMs based on Machine Learning or Deep Learning?**

Modern LLMs are based predominantly on Deep Learning, which is a subset of Machine Learning.

---

# 2. Large Language Models (LLMs)

## 2.1 What is an LLM?

A Large Language Model (LLM) is a type of Deep Learning model trained on large amounts of text and other data to understand and generate human-like language.

LLMs can perform tasks such as:

- Answering questions.
- Generating text.
- Summarizing documents.
- Translating languages.
- Generating code.
- Extracting information.
- Following instructions.
- Reasoning through certain problems.

**Examples:**
- OpenAI GPT models.
- Anthropic Claude models.
- Google Gemini models.
- Meta Llama models.
- Qwen models.

LLMs are a major category of Generative AI.

---

## 2.2 Why are LLMs called Large Language Models?

Each word has a specific meaning:

**Large:** These models are trained using substantial datasets and generally contain large numbers of learnable parameters.

**Language:** They are designed primarily to process and generate language, although modern models can also work with images, audio and other modalities.

**Model:** A trained computational system that learns patterns from data and uses those learned patterns to generate outputs.

---

## 2.3 What is a Language Model?

A Language Model learns statistical patterns in language and estimates the probability of possible next tokens based on preceding context.

For example:

Input: "The sun rises in the..."

Possible predictions:
- East
- West
- North

The model assigns probabilities to possible next tokens based on its learned patterns and the available context.

A language model can be represented conceptually as:

P(next token | previous tokens)

This means predicting the next token based on the tokens already provided.

Modern LLMs use much more sophisticated neural network architectures to perform this task.

---

## 2.4 How Does an LLM Generate Text?

Modern autoregressive LLMs generally generate text one token at a time.

Consider the prompt:

"Artificial Intelligence is"

A simplified generation process:

1. The model receives the input.
2. The input is converted into tokens.
3. The model processes the tokens.
4. It calculates probabilities for possible next tokens.
5. A token is selected according to the decoding strategy.
6. The selected token is added to the context.
7. The process repeats until generation stops.

Example:

Prompt: "Artificial Intelligence is"

Possible generated sequence:

"Artificial" → "Intelligence" → "is" → "changing" → "technology".

The model does not necessarily generate complete sentences in one operation. It repeatedly predicts and generates tokens.

**Important:** This is a simplified explanation of autoregressive text generation. Not every generative model uses this exact process.

---

## 2.5 What are Parameters in an LLM?

Parameters are numerical values learned during model training.

They determine how the neural network processes information and produces predictions.

Think of parameters as the learned internal values that define the model's behavior.

For example:

- GPT models have learned parameters.
- Claude models have learned parameters.
- Llama models have learned parameters.

More parameters do not automatically mean a better model.

Performance also depends on:
- Training data quality.
- Model architecture.
- Training methods.
- Data diversity.
- Post-training and alignment.
- Inference configuration.

Parameters are different from model settings such as temperature and top-p, which influence generation behavior.

---

## 2.6 What is an LLM Training Dataset?

LLMs learn from large collections of training data.

Depending on the model, this data can include:

- Books.
- Articles.
- Websites.
- Documentation.
- Source code.
- Other licensed or curated datasets.

The training process helps the model learn language structure, relationships, patterns and information.

**Important:** Training data and the model's learned parameters are not the same thing. The trained model does not simply work like a searchable copy of its training documents.

---

## 2.7 What Can LLMs Do?

### Language Understanding
- Understand user questions.
- Identify intent.
- Extract relevant information.
- Classify text.

### Content Generation
- Write emails.
- Generate reports.
- Summarize documents.
- Generate code.

### Reasoning and Problem Solving
- Solve certain mathematical problems.
- Compare alternatives.
- Follow multi-step instructions.
- Analyze information.

### Information Processing
- Extract structured information.
- Convert unstructured text into JSON.
- Identify entities.
- Categorize documents.

### Multimodal Tasks
- Understand images.
- Process audio.
- Transcribe speech.
- Work with video in supported models.

---

## 2.8 LLM vs Traditional Machine Learning Models

| Traditional ML Model | Large Language Model |
|---|---|
| Often designed for a specific task | Can perform many language tasks |
| Usually requires task-specific training or configuration | Can follow different instructions through prompts |
| Commonly produces classifications or predictions | Can generate flexible text responses |
| Often uses structured input features | Can process tokenized language and other modalities |
| Usually narrower in scope | More general-purpose |

An important distinction: LLMs are themselves Machine Learning models. They are not separate from ML.

Traditional ML models can also be general-purpose, and LLMs can be adapted for specific tasks.

---

## 2.9 LLM vs Chatbot

These terms are not interchangeable.

**LLM:** The underlying AI model that processes input and generates output.

**Chatbot:** An application or interface that allows users to interact conversationally with a system.

A chatbot may use:
- An LLM.
- Conversation history.
- System instructions.
- External APIs.
- Databases.
- Tool calling.
- Business logic.

For example, ChatGPT is an AI-powered product, while GPT models are the underlying models used by OpenAI products.

A chatbot does not necessarily require an LLM. Traditional chatbots can also use predefined rules.

---

## 2.10 How Developers Use LLMs

Developers generally integrate existing LLMs rather than train their own models.

A simplified architecture:

User → Application → LLM API → Model → Response → Application → User

The application is responsible for:
- Preparing prompts.
- Managing conversation history.
- Sending API requests.
- Handling responses.
- Validating outputs.
- Executing application logic.
- Managing errors and security.

We will explore this architecture in Module 02: Working with AI APIs.

---

## 2.11 Limitations of LLMs

LLMs are powerful but have important limitations.

**1. Hallucinations**

They can generate incorrect information while sounding confident.

**2. Knowledge Limitations**

Their learned knowledge may not include recent or private information.

**3. Context Limitations**

They have finite context windows.

**4. Non-deterministic Outputs**

The same prompt can produce different responses depending on generation settings and model behavior.

**5. Limited Reliability**

They may misunderstand instructions or fail at complex tasks.

**6. Security Risks**

They can be manipulated through prompt injection or unsafe tool instructions.

**7. Cost and Latency**

API calls consume resources and can introduce response delays.

We will study these limitations in detail in later lessons.

---

## Key Takeaways

1. An LLM is a Deep Learning model trained to process and generate language.
2. Language models predict possible next tokens based on previous context.
3. Modern autoregressive LLMs generate text token by token.
4. Parameters are learned numerical values inside the model.
5. LLMs can perform many tasks through instructions and prompts.
6. An LLM is not the same thing as a chatbot.
7. Developers typically integrate existing LLMs through APIs rather than training their own models.
8. LLMs have limitations including hallucinations, context limits, security risks and latency.

---

## Interview Questions

**Q1. What is an LLM?**

An LLM is a Deep Learning model trained on large amounts of data to understand and generate language.

**Q2. How does an LLM generate text?**

Modern autoregressive LLMs predict the probability of the next token based on preceding context and repeatedly generate tokens until completion.

**Q3. What are parameters in an LLM?**

Parameters are learned numerical values inside the neural network that influence how it processes inputs and generates outputs.

**Q4. Is ChatGPT an LLM?**

ChatGPT is an AI-powered application. GPT models are the underlying language models used by OpenAI.

**Q5. Is an LLM the same as traditional Machine Learning?**

An LLM is itself a Machine Learning model, specifically a Deep Learning model designed for language-related tasks.

**Q6. Do developers need to train their own LLMs?**

No. Most developers use existing models through APIs or deploy existing open-source models.

---
# 3. Transformer Architecture

## 3.1 What Is a Transformer?

A Transformer is a neural network architecture designed to process sequences of data, such as text.

It was introduced in the 2017 research paper *Attention Is All You Need*.

Before Transformers, many language models relied on architectures such as RNNs (Recurrent Neural Networks) and LSTMs (Long Short-Term Memory networks).

These architectures processed text sequentially, making it harder to parallelize training and capture relationships between distant words.

Transformers introduced **self-attention**, allowing a model to understand relationships between different tokens in a sequence.

Today, Transformers power most modern LLMs.

## 3.2 Why Do We Need Attention?

Consider this sentence:

> The animal didn't cross the road because it was tired.

To understand the sentence, the model needs to understand what "it" refers to.

Now consider:

> The animal didn't cross the road because it was busy.

The context changes the likely meaning.

A language model must understand relationships between words, not just process each word independently.

Attention helps the model determine which other tokens are important when interpreting a particular token.

**In simple terms:** Attention allows a model to focus on relevant parts of the input while processing a token.

## 3.3 High-Level Transformer Architecture

A Transformer processes input through multiple stages.

```text
Input Text
    |
    v
Tokenization
    |
    v
Token Embeddings
    |
    v
Positional Information
    |
    v
Transformer Layers
    |
    |-- Self-Attention
    |
    |-- Feed-Forward Network
    |
    v
Output Layer
    |
    v
Next Token Probabilities
    |
    v
Generated Text
```

Let's understand each component.

## 3.4 Tokenization and Embeddings

Before a Transformer processes text, the input is converted into tokens.

For example:

```text
Input: "AI is transforming software"

Tokens:
["AI", " is", " transforming", " software"]
```

Each token is converted into a numerical representation called an **embedding**.

An embedding is a vector of numbers representing a token in a mathematical space.

For example, a simplified representation might look like:

```text
"AI"          -> [0.21, 0.45, 0.12, ...]
"software"    -> [0.32, 0.18, 0.67, ...]
"transforming"-> [0.51, 0.29, 0.41, ...]
```

These are illustrative values, not actual model embeddings.

Embeddings allow the model to work with numerical representations rather than raw text.

## 3.5 Positional Information

Transformers process tokens using attention, but they also need information about token order.

Consider:

```text
The dog chased the cat.
The cat chased the dog.
```

Both sentences contain the same words, but their meanings are different.

Positional information helps the model understand where each token appears in the sequence.

It is combined with token representations before they enter the Transformer layers.

Modern Transformer models may use different positional encoding techniques, including:

- Sinusoidal positional encoding
- Learned positional embeddings
- Rotary Position Embeddings (RoPE)

You don't need to implement these techniques yet. Understand their purpose: **preserving information about token positions.**

## 3.6 Self-Attention

Self-attention is one of the most important concepts in Transformer architecture.

It allows each token to consider other relevant tokens in the input sequence.

For example:

```text
The developer built an application because they needed it.
```

When processing "they", the model can use attention to identify relevant contextual information, such as "developer".

Self-attention uses three important representations:

| Component | Meaning |
|---|---|
| Query (Q) | What information is this token looking for? |
| Key (K) | What information does another token represent? |
| Value (V) | What information can another token contribute? |

Think of it like searching through information:

- Query: What am I looking for?
- Key: What does each available item contain?
- Value: What information should I retrieve?

The model compares queries with keys to calculate attention scores.

These scores determine how much information to take from each token's value.

The result is a context-aware representation of each token.

**Important:** Query, Key, and Value are learned mathematical projections of token representations. They are not separate pieces of text or database fields.

## 3.7 Multi-Head Attention

A sentence can contain several types of relationships.

For example:

> The engineer deployed the application after testing it.

The model may need to understand:

- Who performed the action?
- What was deployed?
- What does "it" refer to?
- Which event happened first?

Multi-head attention allows the model to use multiple attention mechanisms in parallel.

Each attention head can learn to capture different patterns or relationships.

```text
             Input Representations
                      |
          +-----------+-----------+
          |           |           |
          v           v           v
       Head 1      Head 2      Head 3
          |           |           |
          +-----------+-----------+
                      |
                      v
                 Combined Output
```

The outputs of these heads are combined and transformed before continuing through the network.

You don't need to memorize the internal equations. Understand that multiple attention heads help the model capture different relationships simultaneously.

## 3.8 Feed-Forward Network

After attention, the Transformer applies a Feed-Forward Network (FFN).

Its job is to further process the information represented by each token.

A simplified Transformer layer looks like:

```text
Input
  |
  v
Self-Attention
  |
  v
Feed-Forward Network
  |
  v
Output
```

A real Transformer layer also includes residual connections and normalization.

### Residual Connections

Residual connections allow information from earlier stages to bypass a transformation and be combined with its output.

They help deep neural networks train more effectively.

### Layer Normalization

Layer normalization helps stabilize the values flowing through the network, supporting more reliable training.

You mainly need to understand their purpose, not their mathematical implementation.

## 3.9 Stacking Transformer Layers

A Transformer usually contains multiple layers.

Each layer processes the representations produced by the previous layer.

```text
Input Embeddings
       |
       v
Transformer Layer 1
       |
       v
Transformer Layer 2
       |
       v
Transformer Layer 3
       |
       v
      ...
       |
       v
Transformer Layer N
       |
       v
Output Representation
```

As information passes through these layers, the model builds increasingly sophisticated representations of the input.

The number of layers, attention heads, and hidden dimensions depends on the model architecture.

## 3.10 Encoder vs Decoder Architecture

Transformers can be designed using three common architectural patterns.

### Encoder-only

The encoder processes input text and produces contextual representations.

Commonly used for:

- Text classification
- Semantic understanding
- Embedding generation

Example: BERT.

### Decoder-only

The decoder generates text one token at a time using previously available tokens.

Commonly used for:

- Chatbots
- Text generation
- Code generation
- General-purpose LLM applications

Examples: GPT-style models.

### Encoder-Decoder

The encoder processes the input, while the decoder generates output using the encoded information.

Commonly used for:

- Translation
- Summarization
- Text-to-text tasks

Example: T5.

| Architecture | Primary purpose | Example |
|---|---|---|
| Encoder-only | Understand input | BERT |
| Decoder-only | Generate output | GPT-style models |
| Encoder-Decoder | Transform input into output | T5 |

For applied AI engineering, the most important architecture to understand is **decoder-only**, because it is widely used for generative LLM applications.

## 3.11 Causal Self-Attention

Decoder-only language models generally use causal self-attention.

It prevents a token from accessing future tokens when predicting the next token.

Consider:

```text
The developer is building an AI
```

When predicting the next token after "AI", the model can use the tokens before it.

During generation, it cannot use tokens that haven't been generated yet.

This ensures that text is generated autoregressively, one token at a time.

```text
The
The developer
The developer is
The developer is building
The developer is building an
The developer is building an AI
```

This is why decoder-only LLMs can generate coherent sequences without seeing the complete answer in advance.

## 3.12 How a Prompt Flows Through a Transformer

Let's connect everything.

Suppose a user asks:

```text
Explain what an API is.
```

The process looks like this:

1. **Tokenization:** The text is split into tokens.
2. **Embedding:** Each token is converted into a numerical vector.
3. **Positional information:** The model receives information about token order.
4. **Transformer layers:** Attention and feed-forward networks process the representations.
5. **Output layer:** The final representation is converted into scores (logits) for possible next tokens.
6. **Probability distribution:** The scores are converted into probabilities.
7. **Token selection:** A decoding strategy selects the next token.
8. **Repeat:** The selected token is added to the context, and the process repeats until generation stops.

The generated tokens are then decoded into readable text.

This connects directly to the autoregressive generation process discussed in Lesson 2.

## 3.13 What Should an Applied AI Engineer Know?

You do not need to build a Transformer from scratch to integrate AI into applications.

You should understand:

- What a Transformer is and why it is used.
- What self-attention does.
- The purpose of Query, Key, and Value.
- Why multi-head attention exists.
- Why embeddings and positional information are required.
- The difference between encoder-only, decoder-only, and encoder-decoder models.
- Why decoder-only models use causal attention.
- How a prompt eventually produces next-token probabilities.

These concepts help you understand model capabilities, limitations, context handling, and the behavior of LLM APIs.

## Key Takeaways

1. Transformers are the architecture behind most modern LLMs.
2. Self-attention helps models understand relationships between tokens.
3. Query, Key, and Value are fundamental components of attention.
4. Multi-head attention captures different relationships in parallel.
5. Embeddings convert tokens into numerical representations.
6. Positional information helps models understand token order.
7. Decoder-only Transformers are widely used for text generation.
8. Causal attention prevents models from looking at future tokens during autoregressive generation.
9. Transformer layers repeatedly process token representations to build contextual information.

## Interview Questions

**1. What is a Transformer?**

A neural network architecture that uses attention mechanisms to process sequences and capture relationships between tokens.

**2. Why were Transformers introduced?**

They address limitations of sequential architectures such as RNNs, enable better parallelization during training, and use attention to capture relationships across sequences.

**3. What is self-attention?**

A mechanism that allows each token to evaluate the relevance of other tokens and incorporate their information into its representation.

**4. What are Query, Key, and Value?**

Learned representations used by attention to determine which information is relevant and how it should be combined.

**5. What is multi-head attention?**

A mechanism that runs multiple attention operations in parallel to capture different relationships.

**6. Why do Transformers need positional information?**

Because attention alone does not inherently encode the order of tokens.

**7. What is the difference between encoder-only and decoder-only models?**

Encoder-only models primarily build contextual representations of input, while decoder-only models generate output autoregressively.

**8. What is causal attention?**

A form of attention that prevents a token from accessing future tokens during autoregressively generation.

**9. What happens inside a Transformer when an LLM receives a prompt?**

The prompt is tokenized, embedded, enriched with positional information, processed through Transformer layers, and converted into next-token probabilities.

# 4. Tokens, Tokenization & Context Windows

## 4.1 What Is a Token?

A token is the basic unit of text that an LLM processes.

A token can represent:
- A complete word
- Part of a word
- A punctuation mark
- A space combined with a word
- A number or special character

For example:

```text
Input:
"Artificial Intelligence is powerful."

Possible tokens:
["Artificial", " Intelligence", " is", " powerful", "."]
```

The exact tokenization depends on the model and its tokenizer.

**Important:** A token is not necessarily the same as a word.

For example, a long or uncommon word may be split into multiple tokens.

## 4.2 What Is Tokenization?

Tokenization is the process of converting text into tokens that a model can process.

A simplified pipeline:

```text
Input Text
    |
    v
Tokenizer
    |
    v
Token IDs
    |
    v
LLM
```

The tokenizer converts text into token IDs, which are numerical identifiers from the model's vocabulary.

Example:

```text
Text:
"Hello world"

Tokens:
["Hello", " world"]

Token IDs:
[15339, 1917]
```

These IDs are illustrative. Actual IDs depend on the tokenizer.

The model processes numerical representations of these tokens, not the original text directly.

## 4.3 How Do Tokenizers Work?

Most modern LLM tokenizers use subword tokenization techniques.

Instead of requiring every possible word to exist in the vocabulary, they can split uncommon words into smaller units.

Common approaches include:

**Byte Pair Encoding (BPE)**

- Starts with smaller units.
- Repeatedly merges frequently occurring adjacent units.
- Builds a vocabulary of commonly occurring token sequences.
- Used by several popular LLM tokenizers.

**WordPiece**

- Builds subword units based on how well they help represent the training data.
- Used by BERT-family models.

**Unigram Language Model**

- Starts with a larger vocabulary and selects a useful subset of subword units.
- Used in SentencePiece-based tokenization approaches.

You don't need to implement tokenizers. Understand that tokenization converts text into manageable units from a model-specific vocabulary.

## 4.4 Why Does Tokenization Matter?

Tokenization directly affects how AI applications behave and how much they cost.

### API Cost

Many AI APIs charge based on the number of input and output tokens.

For example:

```text
Input tokens:  1,000
Output tokens:   500
Total tokens:  1,500
```

More tokens generally mean higher API usage costs.

### Context Window Usage

Every token consumes part of the model's available context window.

Large prompts, conversation histories, and retrieved documents can consume many tokens.

### Response Length

Output token limits determine how much text a model can generate in a single response.

### Multilingual Text

Different languages can require different numbers of tokens for similar amounts of text.

This can affect both cost and context usage.

## 4.5 What Is a Context Window?

A context window is the maximum amount of token information a model can consider during a single processing operation.

It can include:

- System instructions
- Developer instructions
- User messages
- Conversation history
- Retrieved documents
- Tool results
- Other information supplied to the model

Example:

```text
Model Context Window: 100,000 tokens

System Instructions:     2,000
Conversation History:   15,000
Retrieved Documents:    30,000
Current User Prompt:     1,000
Available Space:        52,000
```

This is an illustrative example.

The context window is a token limit, not a word limit.

## 4.6 Context Window vs Memory

These concepts are different.

**Context Window**

The information available to the model during a particular request.

**Memory**

Information stored separately and potentially retrieved for future interactions.

For example, imagine a personal AI assistant.

A user previously said:

> I prefer vegetarian food.

That preference might be stored in a database.

When the user later asks for a meal plan, the application can retrieve that preference and include it in the prompt.

The model can then use it within its current context window.

The model does not automatically remember every past conversation just because it has a large context window.

## 4.7 What Happens When the Context Window Is Full?

If the input exceeds the model's supported context limit, the request may fail or require the application to reduce the input.

Common strategies include:

**1. Truncation**

Remove older or less important content.

**2. Summarization**

Replace a long conversation history with a shorter summary.

**3. Retrieval**

Fetch only the relevant information from a larger knowledge base.

**4. Conversation Management**

Maintain important information separately and include only what is needed for the current request.

These strategies become especially important when building AI assistants and RAG applications.

## 4.8 Context Window vs Maximum Output Tokens

These are related but different limits.

| Concept | Meaning |
|---|---|
| Context window | Maximum token capacity available for the request and generation |
| Maximum output tokens | Maximum tokens the model can generate in its response |

For example:

```text
Context Window:       100,000 tokens
Input Tokens:          20,000 tokens
Output Token Limit:     4,000 tokens
```

The model may have room in its context window for more input, but it cannot generate more than the configured output limit.

Actual API behavior and limits depend on the model.

## 4.9 What Is a Token Budget?

A token budget is the amount of context or output space allocated to different parts of an AI request.

For example, an application might allocate:

| Component | Token Budget |
|---|---:|
| System instructions | 1,000 |
| Conversation history | 5,000 |
| Retrieved documents | 8,000 |
| Current user prompt | 1,000 |
| Reserved output space | 2,000 |

This helps developers control cost, context usage, and response length.

Token budgeting becomes particularly useful in RAG systems and AI agents, where multiple sources of information may be sent to a model.

## 4.10 Practical Example: Why Token Management Matters

Imagine building a customer support AI.

A customer has a conversation containing 200 previous messages.

Sending the entire conversation with every request may:

- Increase API costs.
- Consume context unnecessarily.
- Make relevant information harder to prioritize.
- Leave less space for retrieved knowledge and the response.

A better approach:

1. Keep recent messages.
2. Summarize older conversations.
3. Retrieve relevant customer information.
4. Include only the necessary context.
5. Reserve sufficient space for the response.

This is an important part of practical AI engineering.

## Key Takeaways

1. Tokens are the units of text processed by LLMs.
2. Tokenization converts text into token IDs.
3. Tokens are not equivalent to words.
4. Token counts affect API costs and context usage.
5. A context window limits the information available during a model request.
6. Context windows are not the same as persistent memory.
7. Developers manage context through summarization, retrieval, truncation, and conversation management.
8. Token budgets help control cost and response length.

## Interview Questions

**1. What is a token in an LLM?**

A basic unit of text processed by a language model. It can represent a word, part of a word, punctuation, or another text unit.

**2. What is tokenization?**

The process of converting input text into tokens and corresponding numerical token IDs.

**3. Why are tokens important when using AI APIs?**

They affect API pricing, context window usage, and the amount of text a model can process or generate.

**4. What is a context window?**

The maximum amount of token information a model can handle within a particular request and generation process.

**5. Is a context window the same as memory?**

No. A context window holds information supplied to the model for a request. Memory is information stored separately and potentially retrieved for future requests.

**6. How can developers manage large conversation histories?**

Through summarization, truncation, retrieval, and selective conversation history management.

**7. What is the difference between context window and maximum output tokens?**

The context window limits the overall context capacity, while maximum output tokens limits the generated response length.

**8. Why is token budgeting important?**

It helps developers allocate context efficiently, control API costs, and reserve enough space for model responses.

# 5. Training vs Inference

## 5.1 What Is Model Training?

Training is the process through which a machine learning model learns patterns from data.

For an LLM, training involves processing large amounts of text and adjusting its internal parameters to improve its ability to predict tokens.

A simplified example:

```text
Training Data
     |
     v
Tokenization
     |
     v
LLM
     |
     v
Prediction
     |
     v
Compare with Expected Token
     |
     v
Calculate Error (Loss)
     |
     v
Update Model Parameters
     |
     v
Repeat
```

The model gradually adjusts its parameters to improve its predictions.

## 5.2 How Does an LLM Learn?

Consider the sentence:

```text
The capital of France is _____
```

During training, the model learns to predict the next token based on the preceding context.

It might initially predict an incorrect token.

The training process calculates how far its prediction is from the expected token and adjusts the model's parameters.

This process happens repeatedly across enormous amounts of training data.

The model gradually learns statistical patterns, language structure, relationships, and other information represented in its training data.

## 5.3 What Are Parameters?

Parameters are numerical values inside a neural network that are adjusted during training.

They determine how information is transformed as it passes through the model.

For example:

- A small model might contain billions of parameters.
- A larger model might contain hundreds of billions of parameters.

More parameters do not automatically mean a better model. Architecture, training data, training methods, and inference configuration also matter.

## 5.4 Stages of LLM Training

Modern LLM development generally involves multiple stages.

### 1. Pre-training

The model learns general patterns from a large dataset.

A common objective is next-token prediction.

The model develops broad language and knowledge capabilities.

### 2. Supervised Fine-Tuning (SFT)

The pre-trained model is trained further using curated examples of desired behavior.

Example:

```text
Input:
Explain what an API is.

Expected Output:
An API is an interface that allows software systems to communicate.
```

This helps the model follow instructions and produce more useful responses.

### 3. Alignment and Preference Optimization

The model is further optimized to produce responses that better match human preferences and behavioral requirements.

Methods include:

- RLHF (Reinforcement Learning from Human Feedback)
- DPO (Direct Preference Optimization)

RLHF commonly uses human preference feedback and a reinforcement learning process.

DPO learns from preference comparisons using a different optimization approach.

These are examples of alignment techniques; not every model uses the same pipeline.

## 5.5 What Is Inference?

Inference is the process of using an already-trained model to generate predictions or responses.

When you send a prompt to an LLM API, the model performs inference.

Example:

```text
User Prompt
     |
     v
Trained LLM
     |
     v
Generate Next Token
     |
     v
Generate More Tokens
     |
     v
Final Response
```

Unlike training, ordinary inference does not update the model's learned parameters.

## 5.6 Training vs Inference

| Training | Inference |
|---|---|
| Model learns from data | Model generates predictions |
| Updates model parameters | Normally keeps parameters fixed |
| Requires training datasets | Requires input prompts or data |
| Computationally expensive | Cost depends on model and usage |
| Performed during model development or fine-tuning | Performed whenever an application uses the model |

## 5.7 What Happens When You Call an AI API?

Suppose an application calls an LLM API:

```text
Application
    |
    v
Send Prompt to AI API
    |
    v
Model Performs Inference
    |
    v
Generate Response
    |
    v
Return Response to Application
```

The model provider has already trained the model.

Your application is using the trained model for inference.

This is the typical workflow for an Applied AI Engineer.

## 5.8 Can a Model Learn from My Prompts?

Not automatically.

Sending a prompt to a model does not normally update its underlying parameters.

There are three different concepts to understand:

**Inference:** The model processes your prompt and generates a response.

**Memory or external storage:** An application stores information and retrieves it for future requests.

**Fine-tuning:** The model's parameters are further trained using additional data.

These are different mechanisms and should not be confused.

## 5.9 What Is Fine-Tuning?

Fine-tuning is the process of taking an already-trained model and training it further on a specific dataset.

Example:

Imagine building an AI assistant for a financial services company.

You might fine-tune a model using carefully prepared examples of financial customer support conversations.

Fine-tuning can help with:

- Domain-specific behavior
- Consistent response formats
- Specialized tasks
- Particular writing styles
- Repeated task patterns

However, fine-tuning is not automatically the best way to provide an LLM with updated company information.

For frequently changing information, RAG is often more appropriate.

We will cover RAG in a later module.

## 5.10 What Is Transfer Learning?

Transfer learning means taking knowledge learned by a model during one training task and applying it to another task.

Fine-tuning is one common way of using transfer learning.

For example:

A model trained on general language data can be further trained to perform a specialized task.

## 5.11 What Should an Applied AI Engineer Know?

You should understand:

- What training and inference mean.
- How pre-training works at a high level.
- Why supervised fine-tuning is used.
- What alignment means.
- What model parameters are.
- Why API usage is inference rather than training.
- When fine-tuning might be useful.
- Why external knowledge retrieval and fine-tuning solve different problems.

## Key Takeaways

1. Training teaches a model by adjusting its parameters.
2. Inference uses an already-trained model to generate predictions.
3. Pre-training develops general capabilities.
4. Fine-tuning adapts an existing model to specific tasks or behaviors.
5. RLHF and DPO are examples of alignment techniques.
6. Calling an LLM API normally performs inference, not training.
7. Memory, RAG, and fine-tuning are different approaches.

## Interview Questions

**1. What is the difference between training and inference?**

Training adjusts model parameters using data. Inference uses the trained model to generate predictions without normally updating those parameters.

**2. What is pre-training?**

The initial training stage where a model learns general patterns from a large dataset.

**3. What is fine-tuning?**

Further training an existing model on specialized data to improve its behavior for particular tasks.

**4. What is RLHF?**

Reinforcement Learning from Human Feedback is an alignment technique that uses human preference feedback to help optimize model behavior.

**5. Does an LLM learn every time we send a prompt?**

No. Normal inference does not update the model's parameters.

**6. When should you consider RAG instead of fine-tuning?**

When an application needs to access external or frequently changing information without retraining the model.

# 6. Hallucinations & LLM Limitations

## 6.1 What Is an LLM Hallucination?

An LLM hallucination occurs when a model generates information that is incorrect, fabricated, or unsupported but presents it as if it were true.

Example:

User:

```text
Who invented the programming language Python?
```

Correct answer:

```text
Python was created by Guido van Rossum.
```

A hallucinating model might confidently provide an incorrect person's name.

The problem is that the response can sound convincing even when it is wrong.

## 6.2 Why Do LLMs Hallucinate?

LLMs generate responses based on patterns learned during training and the context provided during inference.

They do not inherently verify every generated statement against a trusted source.

Common reasons include:

### 1. Missing Information

The model may not have enough information to answer a question.

Instead of acknowledging uncertainty, it may generate a plausible-sounding answer.

### 2. Ambiguous Prompts

Unclear or incomplete instructions can lead to incorrect assumptions.

### 3. Outdated Knowledge

A model's training knowledge may not include recent developments.

### 4. Weak or Conflicting Context

If the prompt contains incomplete, irrelevant, or contradictory information, the model may produce unreliable responses.

### 5. Statistical Generation

An LLM predicts likely next tokens. It is not inherently a database or a fact-checking engine.

This is one reason why fluent language does not guarantee factual correctness.

## 6.3 Common Types of Hallucinations

| Type | Example |
|---|---|
| Factual hallucination | Giving an incorrect historical date |
| Fabricated references | Inventing a research paper or URL |
| Incorrect calculations | Producing an incorrect numerical result |
| Unsupported claims | Claiming a document contains information it does not contain |
| Coding hallucinations | Inventing a library function or API |
| Contextual hallucination | Misinterpreting information provided by the user |

## 6.4 Other Limitations of LLMs

Hallucination is not the only limitation.

### Knowledge Cutoff

A model's internal knowledge may not include recent events or updated information.

Applications can address this using web search, APIs, or retrieval systems.

### Limited Context

Models have a finite context window.

They cannot process unlimited conversation history or documents in a single request.

### Reasoning Errors

Models can make mistakes in:

- Complex logical problems
- Multi-step calculations
- Technical analysis
- Long instructions
- Edge cases in programming

### Lack of Real-World Awareness

An LLM does not automatically know the current state of external systems.

For example, it cannot inherently know:

- Your current bank balance
- Today's stock price
- The current status of an order
- Whether a particular server is online

The application must provide access to such information.

### Non-deterministic Responses

The same prompt can produce different responses depending on model configuration, sampling, and other factors.

### Bias

Models may reproduce biases present in their training data or introduced by other parts of the system.

### Security Risks

LLM applications can be vulnerable to:

- Prompt injection
- Data leakage
- Unsafe tool execution
- Insecure handling of user inputs
- Excessive permissions

These become especially important when building AI agents.

## 6.5 How Can Developers Reduce Hallucinations?

Hallucinations cannot be completely eliminated, but application design can reduce their frequency and impact.

### 1. Better Prompting

Give the model clear instructions.

Example:

```text
Answer only using the provided information.

If the information is unavailable,
clearly state that you don't know.
```

### 2. Retrieval-Augmented Generation (RAG)

Retrieve relevant information from trusted sources and provide it to the model.

Example:

```text
User Question
     |
     v
Search Relevant Documents
     |
     v
Retrieve Supporting Information
     |
     v
Send Context + Question to LLM
     |
     v
Generate Answer
```

RAG can improve factual grounding, but it does not guarantee correctness.

### 3. Tool Calling

Allow the model to use external tools for tasks that require reliable data.

Examples:

- Calculator for calculations
- Database queries for customer information
- Weather API for weather information
- Search API for current information

### 4. Structured Outputs

Use schemas to constrain the response format.

For example, require the model to return a JSON object with specific fields.

Structured output improves format reliability, but it does not guarantee that the values are factually correct.

### 5. Validation

Validate generated information before using it.

Examples:

- Check whether a generated email address exists in your database.
- Verify that a generated product ID is valid.
- Check whether a requested operation is permitted.
- Validate numerical calculations using deterministic code.

### 6. Human Review

For high-impact decisions, use human approval or review instead of allowing an LLM to make decisions independently.

## 6.6 RAG vs Fine-Tuning vs Prompting

These techniques solve different problems.

| Technique | Primary purpose |
|---|---|
| Prompt Engineering | Guide model behavior |
| RAG | Provide relevant external information |
| Fine-Tuning | Adapt model behavior through additional training |
| Tool Calling | Allow the model to interact with external systems |
| Validation | Check generated outputs against rules or trusted data |

Example:

Imagine building an AI assistant for an organization.

- Prompting defines how the assistant should behave.
- RAG provides access to company documents.
- Fine-tuning may help with specialized behavior.
- Tool calling allows it to interact with company systems.
- Validation checks whether actions and outputs are acceptable.

## 6.7 What Should an Applied AI Engineer Know?

You should be able to:

- Explain why LLMs hallucinate.
- Recognize situations where LLM output cannot be trusted.
- Use retrieval to provide factual context.
- Use external tools for reliable information.
- Validate outputs before executing operations.
- Apply permission checks and human approval where necessary.
- Understand that structured output does not guarantee factual correctness.

## Key Takeaways

1. Hallucinations are incorrect or unsupported generated claims.
2. Fluent responses are not necessarily factual.
3. LLMs have limitations involving knowledge, reasoning, context, and security.
4. Prompting can guide behavior but cannot guarantee correctness.
5. RAG provides external information to ground responses.
6. Tool calling enables access to real-world systems.
7. Validation and human review are important safeguards.

## Interview Questions

**1. What is an LLM hallucination?**

An incorrect or unsupported response generated by a language model and presented as if it were true.

**2. Why do LLMs hallucinate?**

They generate likely token sequences rather than inherently verifying every claim against trusted information.

**3. How can hallucinations be reduced?**

Through better prompts, RAG, tool calling, structured outputs, validation, and human review.

**4. Does RAG eliminate hallucinations?**

No. It provides relevant external context, but the model can still misunderstand or misuse that information.

**5. Does structured output guarantee correctness?**

No. It constrains the response format, not necessarily the factual accuracy of its contents.

**6. What is prompt injection?**

An attack where malicious instructions are introduced through input or retrieved content to manipulate an LLM's behavior.

**7. Why should AI-generated actions be validated?**

Because an LLM can generate incorrect or unsafe actions. Applications must enforce business rules, permissions, and validation independently.

# 7. Foundation Models, Parameters & Configuration

## 7.1 What Is a Foundation Model?

A foundation model is a large model trained on broad datasets that can be adapted or used for many different tasks.

Instead of building a separate model for every task, developers can use one foundation model for multiple applications.

Examples of tasks include:

- Text generation
- Summarization
- Translation
- Classification
- Question answering
- Code generation
- Image understanding

Examples of foundation model families include GPT, Claude, Gemini, Llama, and Qwen.

## 7.2 Foundation Model vs Traditional Task-Specific Model

| Foundation Model | Task-Specific Model |
|---|---|
| General-purpose capabilities | Designed for a particular task |
| Can support multiple applications | Usually has a narrower purpose |
| Can be adapted for different tasks | Often requires retraining for major changes |
| May be accessed through APIs or deployed directly | Often deployed for a specific workflow |

For example:

A general-purpose LLM can summarize documents, answer questions, and generate code.

A traditional spam classifier may only classify messages as spam or not spam.

## 7.3 What Is a Model Family?

A model family is a collection of related models developed by the same organization or research group.

Examples:

- GPT models from OpenAI
- Claude models from Anthropic
- Gemini models from Google
- Llama models from Meta
- Qwen models from Alibaba

Different models within the same family may have different:

- Sizes
- Capabilities
- Context windows
- Speed
- Pricing
- Multimodal support

Do not assume every model in a family supports the same features.

## 7.4 Model Parameters vs API Parameters

These are two different concepts.

### Model Parameters

Model parameters are learned numerical values inside a neural network.

They are adjusted during training and determine how the model processes information.

They are not normally modified by developers when making an API request.

### API Parameters

API parameters are configuration values developers provide when calling a model.

They control aspects of how the model generates responses.

Common examples include:

- Temperature
- Top-p
- Maximum output tokens
- Stop sequences
- Response format

The available settings depend on the provider and model.

## 7.5 Temperature

Temperature controls the randomness of token selection during generation.

Generally:

- Lower temperature produces more predictable outputs.
- Higher temperature allows more variation.

Example:

Prompt:

```text
Suggest a name for a task management application.
```

Low temperature might produce:

```text
TaskFlow
```

Higher temperature might produce:

```text
MindGarden
```

These are illustrative outputs, not guaranteed results.

Typical use cases:

| Temperature | Suitable Use Cases |
|---|---|
| Low | Extraction, classification, structured responses |
| Medium | General assistance and explanations |
| Higher | Creative writing and brainstorming |

Temperature behavior and supported ranges vary by model.

## 7.6 Top-p Sampling

Top-p is also known as nucleus sampling.

It controls token selection by considering the smallest group of candidate tokens whose cumulative probability reaches a specified threshold.

For example:

If top-p is 0.9, the model considers a candidate set containing approximately 90% of the cumulative probability mass before sampling.

A simplified illustration:

```text
Candidate Tokens:

Token A: 50%
Token B: 25%
Token C: 15%
Token D: 10%

Top-p = 0.90

Considered candidates:
A, B, C
```

This is an illustrative example.

Temperature and top-p both influence generation variability, but they work differently.

In practice, you usually adjust one at a time to understand its effect.

## 7.7 Maximum Output Tokens

This controls the maximum number of tokens the model can generate in a response.

For example:

```text
Maximum Output Tokens: 500
```

The model cannot generate more than the configured limit for that response.

A low limit may result in incomplete answers.

A higher limit can allow longer responses, but may increase latency and cost.

## 7.8 Stop Sequences

Stop sequences are predefined strings or tokens that tell a model to stop generating when encountered.

Example:

```text
Stop Sequence: <END>
```

If the model generates the specified stop sequence, generation stops.

This can be useful for controlling output boundaries in certain text-generation workflows.

Support varies across providers and APIs.

## 7.9 Choosing a Model for an Application

You should not select a model only because it is the largest or most popular.

Evaluate models based on:

| Factor | What to Consider |
|---|---|
| Accuracy | Does it solve the required task correctly? |
| Latency | How quickly does it respond? |
| Cost | What is the input and output pricing? |
| Context Window | Can it handle the required input? |
| Reliability | Does it behave consistently? |
| Multimodal Support | Does it support images, audio, or video as needed? |
| Tool Calling | Can it interact with application tools? |
| Privacy | Does its data handling meet application requirements? |

A smaller model may be sufficient for simple classification or extraction tasks, while a more capable model may be needed for complex reasoning.

## 7.10 Model Selection in Real Applications

Imagine building an AI-powered document management system.

Different tasks may require different models.

| Task | Possible Model Requirement |
|---|---|
| Document classification | Fast, inexpensive model |
| Metadata extraction | Model with reliable structured outputs |
| Document question answering | Model with good reasoning and context support |
| Image-based document understanding | Vision-capable model |
| Complex document analysis | More capable reasoning model |

This leads to an important design principle:

**Choose the model based on the task, not just the model's popularity.**

## Key Takeaways

1. Foundation models are broadly trained models that support multiple downstream tasks.
2. Model families contain related models with different capabilities.
3. Model parameters are learned values inside the neural network.
4. API parameters configure how a model generates responses.
5. Temperature and top-p influence generation variability.
6. Maximum output tokens limit response length.
7. Model selection should consider accuracy, cost, latency, context, capabilities, and privacy.

## Interview Questions

**1. What is a foundation model?**

A broadly trained model that can be adapted or used for many different downstream tasks.

**2. What is the difference between model parameters and API parameters?**

Model parameters are learned numerical values inside the neural network. API parameters configure the model's behavior during inference.

**3. What does temperature control?**

The randomness of token selection during generation.

**4. What is top-p sampling?**

A sampling method that considers the smallest set of candidate tokens whose cumulative probability reaches a specified threshold.

**5. What is the difference between temperature and top-p?**

Temperature changes the probability distribution used for sampling, while top-p restricts sampling to a nucleus of high-probability candidates.

**6. How would you choose an LLM for an application?**

Evaluate task accuracy, latency, cost, context window, reliability, capabilities, and privacy requirements.

**7. Should every application use the largest available model?**

No. A smaller, cheaper model may be sufficient for simpler tasks and can improve application efficiency.

# 8. Multimodal AI

## 8.1 What Is Multimodal AI?

Multimodal AI refers to AI systems that can process or generate information across multiple types of data.

Traditional language models primarily work with text.

Multimodal models can work with combinations of:

- Text
- Images
- Audio
- Video
- Other structured or sensor-based data

For example, a multimodal assistant may accept an image and a question about that image, then generate a text response.

## 8.2 Unimodal vs Multimodal Models

| Unimodal Model | Multimodal Model |
|---|---|
| Works primarily with one data modality | Works with multiple modalities |
| Example: text-only language model | Example: model that accepts text and images |
| Narrower input/output capabilities | Can support richer interactions |

## 8.3 Image Understanding

Vision-capable models can process images and answer questions about their contents.

Example:

```text
Input:
An image of a damaged laptop screen.

Question:
What damage can you identify?
```

The model may describe visible cracks, discoloration, or other visual details.

Applications include:

- Document understanding.
- Image classification.
- Visual question answering.
- Product recognition.
- Screenshot analysis.
- Medical image assistance, with appropriate safeguards.

Some models process images through patches or other internal visual representations before combining that information with language representations.

You don't need to understand the internal vision architecture yet.

## 8.4 Audio Understanding

Audio-capable AI systems can process spoken language and other audio signals.

Common tasks include:

### Speech-to-Text (STT)

Converts spoken audio into text.

Example:

```text
Audio:
"Schedule a meeting for tomorrow."

Output:
Schedule a meeting for tomorrow.
```

### Text-to-Speech (TTS)

Converts text into spoken audio.

Example:

```text
Input:
"Your meeting is scheduled."

Output:
A generated spoken response.
```

### Audio Understanding

Some models can process audio directly to identify information such as speech, sounds, and conversational context.

Applications include:

- Voice assistants.
- Meeting transcription.
- Call-center automation.
- Voice-based customer support.
- Audio summarization.

## 8.5 Video Understanding

Video-capable systems can process visual information across time.

A video contains a sequence of frames, often combined with audio.

Applications include:

- Video summarization.
- Activity recognition.
- Video question answering.
- Surveillance analysis with appropriate safeguards.
- Sports analysis.

Some systems sample frames from videos and process them along with audio or text.

## 8.6 Multimodal Generation

Multimodal AI is not limited to understanding inputs. Some models can also generate outputs in different modalities.

Examples:

| Input | Generated Output |
|---|---|
| Text prompt | Image |
| Text prompt | Audio |
| Text prompt | Video |
| Audio input | Text response |
| Text and image | Combined response |

The capabilities vary by model and provider.

## 8.7 How Multimodal Models Work: High-Level View

Different modalities need different processing methods.

A simplified architecture:

```text
             User Input
                 |
       +---------+---------+
       |         |         |
       v         v         v
      Text     Image     Audio
       |         |         |
       v         v         v
   Text Encoder  Vision   Audio
                Encoder  Encoder
       |         |         |
       +---------+---------+
                 |
                 v
          Shared Model
          Representations
                 |
                 v
          Model Processing
                 |
                 v
           Generated Output
```

This is a conceptual illustration. Real multimodal architectures vary significantly.

Some models use separate encoders, while others use unified architectures or specialized token representations.

## 8.8 Multimodal AI in Real Applications

Consider an intelligent document management system.

A user uploads a scanned invoice.

A multimodal AI workflow could:

1. Accept the uploaded document image.
2. Understand the visual content.
3. Extract invoice details.
4. Return structured information.
5. Validate extracted fields.
6. Save the information to the application database.

Example output:

```json
{
  "invoice_number": "INV-1024",
  "vendor": "ABC Technologies",
  "total_amount": 25000,
  "currency": "INR"
}
```

The values are illustrative.

The application should validate extracted data before storing or using it.

## 8.9 Multimodal AI vs Traditional OCR

OCR (Optical Character Recognition) extracts text from images and scanned documents.

Multimodal AI can go further by interpreting visual context and answering questions about the content.

| OCR | Multimodal AI |
|---|---|
| Extracts text from images | Understands and reasons about visual content |
| Focuses on text recognition | Can process text and non-text visual information |
| Often produces extracted text | Can answer questions and generate structured outputs |

OCR remains useful when reliable text extraction is the primary requirement.

Multimodal models can be useful when the task requires broader visual understanding.

## 8.10 What Should an Applied AI Engineer Know?

You should understand:

- What multimodal AI means.
- The difference between text, image, audio, and video capabilities.
- What vision-capable models can do.
- The difference between speech-to-text and text-to-speech.
- How multimodal inputs can be integrated into applications.
- When traditional OCR or specialized tools may be more appropriate.
- Why outputs still need validation.

## Key Takeaways

1. Multimodal AI processes multiple types of information.
2. Modern AI systems can understand text, images, audio, and video.
3. Speech-to-text converts audio into text.
4. Text-to-speech converts text into audio.
5. Vision-capable models can interpret image content.
6. Multimodal AI can support document processing, voice assistants, and video analysis.
7. The correct modality and model depend on the application requirement.

## Interview Questions

**1. What is multimodal AI?**

AI that can process or generate information across multiple modalities, such as text, images, audio, and video.

**2. What is the difference between unimodal and multimodal AI?**

Unimodal systems primarily work with one modality, while multimodal systems work with multiple modalities.

**3. What is the difference between STT and TTS?**

STT converts speech into text, while TTS converts text into spoken audio.

**4. What is the difference between OCR and multimodal AI?**

OCR primarily extracts text from images. Multimodal AI can also interpret broader visual context and answer questions about image content.

**5. Give an example of multimodal AI in a business application.**

An invoice processing system that accepts scanned documents, extracts information, validates it, and stores structured data.

**6. Does every LLM support image and audio inputs?**

No. Multimodal capabilities depend on the specific model and API.

# 9. Open-Source vs Closed-Source Models

## 9.1 What Are Open-Source Models?

Open-source AI models are models whose developers make their model artifacts and related resources available under a license that permits certain forms of access, use, modification, or redistribution.

However, the term "open-source model" is often used loosely.

Some models provide downloadable weights but do not release all training data, training code, or other development details.

Therefore, it is important to examine the actual license and what the provider makes available.

Examples of model families with publicly available weights include:

- Llama
- Qwen
- Mistral
- Gemma

Availability and usage rights vary by model and license.

## 9.2 What Are Closed-Source Models?

Closed-source models are models where the provider does not publicly release the model's complete internal artifacts, such as its weights.

Developers typically access them through hosted APIs or managed platforms.

Examples include:

- OpenAI GPT models
- Anthropic Claude models
- Google Gemini models

The exact access and deployment options depend on the provider.

## 9.3 Open-Source vs Closed-Source

| Factor | Open-Weight Models | Closed-Source Models |
|---|---|---|
| Model weights | Often downloadable | Generally not publicly available |
| Hosting | Can often self-host | Usually provider-hosted |
| Customization | Greater control over deployment and modification | Depends on provider features |
| Infrastructure | May require your own infrastructure | Provider manages model infrastructure |
| Maintenance | Your responsibility when self-hosting | Primarily handled by provider |
| Pricing | Infrastructure and operational costs | API usage or subscription costs |
| Privacy | Can offer greater deployment control | Depends on provider's data policies |
| Model updates | You manage versions when self-hosting | Provider manages model releases |

Open-weight does not automatically mean unrestricted or fully open-source.

## 9.4 Examples of Open-Weight Models

### Llama

Developed by Meta.

A family of models available with downloadable weights under model-specific licenses.

### Qwen

Developed by Alibaba.

Provides a range of models, including language and multimodal models, with different capabilities and licensing terms.

### Mistral

Developed by Mistral AI.

Offers multiple model families and deployment options, including models with publicly available weights.

### Gemma

Developed by Google.

A family of models with publicly available weights and model-specific terms.

Always check the license for the exact model version you intend to use.

## 9.5 Examples of Closed-Source Models

### GPT

Developed by OpenAI.

Provides models through hosted APIs and supported product interfaces.

### Claude

Developed by Anthropic.

Provides language models through hosted APIs and supported platforms.

### Gemini

Developed by Google.

Provides models through Google's AI platforms and APIs.

These providers manage the underlying model infrastructure for their hosted API offerings.

## 9.6 What Is Self-Hosting?

Self-hosting means deploying and running a model on infrastructure that you control.

This could be:

- A local computer
- A dedicated GPU server
- A private cloud environment
- An organization's own data center

Common tools and platforms include:

- Ollama
- vLLM
- Hugging Face Transformers
- Hugging Face Text Generation Inference

Self-hosting gives developers more control over infrastructure and deployment, but it introduces operational responsibilities.

These include:

- GPU provisioning
- Memory management
- Scaling
- Model serving
- Monitoring
- Security
- Updates
- Availability

## 9.7 What Is an AI Model API?

An AI model API allows an application to communicate with a model through a programmatic interface.

Example:

```text
Your Application
       |
       v
   AI API Request
       |
       v
  Model Provider
       |
       v
  Model Inference
       |
       v
   API Response
       |
       v
Your Application
```

Instead of deploying and managing model infrastructure, the application sends requests to the provider.

This is one of the most common ways to integrate AI into software products.

## 9.8 How Should You Choose?

There is no universally better option.

Choose based on the application requirements.

### Choose a Hosted Closed-Source Model When:

- You want to integrate AI quickly.
- You don't want to manage GPU infrastructure.
- You need a provider-managed model.
- The available model capabilities meet your requirements.
- The provider's pricing and data policies are acceptable.

### Consider an Open-Weight Model When:

- You need greater control over deployment.
- You have specific data residency requirements.
- You want to experiment with model customization.
- You have suitable infrastructure.
- You want to evaluate self-hosting economics.

## 9.9 What About Hybrid AI Architecture?

An application does not have to use only one type of model.

It can use different models for different tasks.

Example:

```text
             AI Application
                   |
         +---------+---------+
         |                   |
         v                   v
   Simple Tasks         Complex Tasks
         |                   |
         v                   v
   Self-hosted Model    Hosted Model API
         |                   |
         +---------+---------+
                   |
                   v
             Application
```

For example:

- Use a smaller self-hosted model for simple classification.
- Use a hosted model for complex reasoning.
- Use a vision-capable model for image understanding.

The architecture should be based on evaluation, reliability, latency, cost, and privacy requirements.

## 9.10 Important Considerations for Production

Before selecting a model, evaluate:

**Licensing:** Are commercial use, redistribution, and modification permitted?

**Privacy:** What happens to the prompts and data sent to the provider?

**Security:** How is sensitive information protected?

**Cost:** What are the API or infrastructure costs?

**Performance:** Does the model meet latency and throughput requirements?

**Reliability:** Does it consistently perform well on your actual tasks?

**Portability:** Can the application switch models without major changes?

A useful engineering practice is to keep your application code independent of a single model provider where practical.

## Key Takeaways

1. Open-weight models provide downloadable model weights, subject to their licenses.
2. Closed-source models are generally accessed through provider-managed services.
3. Open-weight does not necessarily mean fully open-source.
4. Self-hosting gives more infrastructure control but adds operational complexity.
5. Hosted APIs simplify model integration and infrastructure management.
6. Model selection should consider cost, privacy, licensing, latency, and quality.
7. Applications can combine hosted and self-hosted models.

## Interview Questions

**1. What is the difference between open-source and closed-source LLMs?**

Open-source or open-weight models provide varying levels of access to model artifacts, while closed-source models generally expose capabilities through provider-managed services.

**2. What is self-hosting?**

Deploying and running a model on infrastructure controlled by the organization or developer.

**3. What are the advantages of self-hosting?**

Greater deployment control, potential data residency benefits, and flexibility over infrastructure and model configuration.

**4. What are the disadvantages of self-hosting?**

Infrastructure costs, GPU requirements, scaling complexity, maintenance, monitoring, and operational responsibilities.

**5. Why might a company choose a hosted AI API?**

It reduces infrastructure management and provides access to provider-managed models.

**6. Can an application use multiple AI models?**

Yes. Different models can handle different tasks based on cost, performance, and capability requirements.

**7. What should you check before using an open-weight model commercially?**

Its license, commercial usage permissions, redistribution conditions, and other applicable restrictions.

# Module 1: References

These resources cover the concepts discussed throughout AI & LLM Fundamentals.

## Official Documentation and Research

### AI and Machine Learning Fundamentals

- [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course)
- [Deep Learning Book](https://www.deeplearningbook.org/)

### Transformers and LLM Fundamentals

- [Attention Is All You Need — Original Transformer Paper](https://arxiv.org/abs/1706.03762)
- [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)
- [Hugging Face NLP Course](https://huggingface.co/learn/nlp-course/)
- [The GPT-2 Paper](https://openai.com/research/better-language-models)

### Tokenization and Context

- [OpenAI Tokenizer](https://platform.openai.com/tokenizer)
- [Hugging Face Tokenizers Documentation](https://huggingface.co/docs/tokenizers/index)

### Training and Fine-Tuning

- [Hugging Face Transformers Documentation](https://huggingface.co/docs/transformers/index)
- [InstructGPT Research Paper](https://arxiv.org/abs/2203.02155)
- [Direct Preference Optimization Paper](https://arxiv.org/abs/2305.18290)

### Multimodal AI

- [Hugging Face Multimodal Documentation](https://huggingface.co/docs/transformers/tasks/image_text_to_text)

### Open-Weight Models

- [Meta Llama](https://www.llama.com/)
- [Qwen](https://qwen.ai/)
- [Mistral AI](https://mistral.ai/)
- [Google Gemma](https://ai.google.dev/gemma)

## Learning Guidance

You do not need to read every research paper in detail.

Prioritize:

1. Understanding the concepts.
2. Knowing how they affect real AI applications.
3. Understanding common limitations and trade-offs.
4. Being able to explain the concepts during technical interviews.

Use the official documentation when you begin integrating specific models and APIs.

---

**Module 1 completed: AI & LLM Fundamentals.**