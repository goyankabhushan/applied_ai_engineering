# 01. AI & LLM Fundamentals

This module introduces the core concepts behind modern AI systems and Large Language Models (LLMs).

**Objective:** Understand how LLMs work, their capabilities and limitations, and the terminology needed to build AI-powered applications.

## Contents

1. [Artificial Intelligence, Machine Learning and Deep Learning](#1-artificial-intelligence-machine-learning-and-deep-learning)
2. [Large Language Models](#2-large-language-models)
3. [Transformer Architecture](#3-transformer-architecture)
4. [Tokens, Tokenization and Context Windows](#4-tokens-tokenization-and-context-windows)
5. [Training and Inference](#5-training-and-inference)
6. [Hallucinations and LLM Limitations](#6-hallucinations-and-llm-limitations)
7. [Foundation Models and Model Configuration](#7-foundation-models-and-model-configuration)
8. [Multimodal AI](#8-multimodal-ai)
9. [Open-Weight vs Closed-Source Models](#9-open-weight-vs-closed-source-models)

---

# 1. Artificial Intelligence, Machine Learning and Deep Learning

## 1.1 Artificial Intelligence (AI)

Artificial Intelligence is a field of computer science focused on building systems capable of performing tasks that typically require human intelligence.

Examples include:

- Understanding language.
- Recognizing images.
- Making predictions.
- Solving problems.
- Generating content.
- Making decisions.

AI is the broader field that includes Machine Learning, Deep Learning and Generative AI.

## 1.2 Machine Learning (ML)

Machine Learning is a subset of AI in which systems learn patterns from data to make predictions or decisions without requiring every rule to be explicitly programmed.

**Traditional programming:**

```text
Input + Rules → Output
```

**Machine Learning:**

```text
Training Data + Learning Algorithm → Trained Model
```

Common types:

| Type | How it works | Example |
|---|---|---|
| Supervised Learning | Learns from labelled examples | Spam detection |
| Unsupervised Learning | Finds patterns without predefined labels | Customer segmentation |
| Reinforcement Learning | Learns through actions and rewards | Game-playing agents |

## 1.3 Deep Learning (DL)

Deep Learning is a subset of Machine Learning that uses neural networks with multiple layers to learn complex patterns.

A neural network typically contains:

- Input layer: Receives data.
- Hidden layers: Process information.
- Output layer: Produces predictions.
- Weights and biases: Learned numerical parameters.
- Activation functions: Introduce non-linearity.

Deep Learning is used in image recognition, speech processing, computer vision and modern LLMs.

## 1.4 Generative AI (GenAI)

Generative AI refers to AI systems that generate new content based on patterns learned from training data.

| Modality | Examples |
|---|---|
| Text | ChatGPT, Claude |
| Images | Image generation models |
| Audio | Speech and music generation |
| Video | AI-generated video |
| Code | Code generation and completion |

Common applications include chatbots, document summarization, content generation, information extraction and code assistants.

## 1.5 Relationship Between AI, ML, DL and GenAI

```text
Artificial Intelligence
        |
        +-- Machine Learning
                |
                +-- Deep Learning
                        |
                        +-- Many modern LLMs

Generative AI is a category of AI systems
that generate new content.
```

Modern generative AI predominantly uses Deep Learning, although not every generative AI technique must use it.

## 1.6 Traditional Predictive AI vs Generative AI

| Predictive AI | Generative AI |
|---|---|
| Classifies spam emails | Writes emails |
| Predicts customer churn | Generates customer reports |
| Detects fraud | Explains suspicious activity |
| Recommends products | Creates conversational assistants |

Both approaches can be combined in one application.

## 1.7 Relevance to AI Engineering

| Requirement | Relevant Technology |
|---|---|
| Detect fraudulent transactions | Machine Learning |
| Recognize objects in images | Deep Learning |
| Generate reports | Generative AI |
| Answer questions about company documents | LLM + RAG |
| Execute operations using natural language | LLM + Tool Calling |
| Perform multi-step tasks | AI Agents |

Our focus is on Generative AI, LLMs and the engineering techniques used to integrate them into software applications.

---

# 2. Large Language Models

## 2.1 What Is an LLM?

A Large Language Model (LLM) is a Deep Learning model trained on large amounts of data to process and generate language.

LLMs can perform tasks such as:

- Answering questions.
- Generating text and code.
- Summarizing documents.
- Translating languages.
- Extracting information.
- Following instructions.
- Performing certain reasoning tasks.

Examples include GPT, Claude, Gemini, Llama and Qwen model families.

LLMs are a major category of Generative AI.

## 2.2 What Is a Language Model?

A language model learns patterns in language and estimates the probability of possible next tokens based on preceding context.

For example:

```text
The sun rises in the ...
```

Possible next tokens might include:

- East
- West
- Morning

Conceptually:

\[
P(\text{next token} \mid \text{previous tokens})
\]

Modern autoregressive LLMs use this next-token prediction process to generate text.

## 2.3 How Does an LLM Generate Text?

Most commonly used text-generating LLMs generate output autoregressively, one token at a time.

```text
Prompt
  |
  v
Tokenization
  |
  v
Model Processing
  |
  v
Predict Next Token
  |
  v
Append Token to Context
  |
  v
Repeat Until Generation Stops
```

For example:

```text
Input: "Artificial Intelligence"

Generated:
"Artificial Intelligence is changing technology."
```

The model repeatedly predicts and generates tokens until it reaches a stopping condition.

## 2.4 What Are Model Parameters?

Parameters are numerical values learned during model training.

They influence how the neural network processes information and generates predictions.

Model size is often described by its parameter count.

However, more parameters do not automatically mean a better model.

Performance also depends on:

- Training data quality.
- Model architecture.
- Training methods.
- Post-training and alignment.
- Inference configuration.

Model parameters are different from API settings such as temperature and top-p.

## 2.5 What Is an LLM Trained On?

Depending on the model, training data may include:

- Books and articles.
- Websites.
- Documentation.
- Source code.
- Licensed and curated datasets.

Training helps the model learn language structure, patterns, relationships and information.

The trained model is not simply a searchable copy of its training documents.

## 2.6 What Can LLMs Do?

| Capability | Example |
|---|---|
| Language understanding | Identify user intent |
| Content generation | Write emails and reports |
| Summarization | Summarize long documents |
| Information extraction | Extract invoice details |
| Classification | Categorize customer messages |
| Code generation | Generate code snippets |
| Multimodal understanding | Analyze images in supported models |

LLMs can perform multiple tasks through instructions rather than requiring a separate model for every task.

## 2.7 LLM vs Traditional ML vs Chatbot

**LLM vs Traditional ML**

An LLM is itself a Machine Learning model, specifically a Deep Learning model.

Traditional ML models are often designed for narrower prediction or classification tasks, while LLMs support a wider range of language tasks.

**LLM vs Chatbot**

- LLM: The underlying model that processes input and generates output.
- Chatbot: An application that allows users to interact conversationally.

A chatbot may use an LLM, conversation history, databases, APIs, business logic and tool calling.

A chatbot can also operate using traditional predefined rules.

## 2.8 How Developers Use LLMs

Most application developers use existing LLMs rather than training their own models.

```text
User
 |
 v
Application
 |
 v
LLM API
 |
 v
Model Inference
 |
 v
Response
 |
 v
Application
 |
 v
User
```

The application handles:

- Preparing prompts.
- Managing conversation history.
- Sending API requests.
- Processing responses.
- Validating outputs.
- Executing application logic.

We will implement this workflow in Module 2.

---

# 3. Transformer Architecture

## 3.1 What Is a Transformer?

A Transformer is a neural network architecture designed to process sequences of data, such as text.

It was introduced in the 2017 research paper *Attention Is All You Need*.

Transformers use an attention mechanism to capture relationships between different tokens.

They power most modern LLMs.

## 3.2 Why Do We Need Attention?

Consider:

```text
The animal didn't cross the road because it was tired.
```

To understand the sentence, a model needs to identify what "it" refers to.

Attention helps the model determine which other tokens are relevant when processing a particular token.

In simple terms, attention allows a model to focus on relevant parts of the input.

## 3.3 High-Level Transformer Architecture

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
    +-- Self-Attention
    |
    +-- Feed-Forward Network
    |
    v
Output Layer
    |
    v
Next Token Probabilities
```

## 3.4 Token Embeddings

Before a Transformer processes text, the input is converted into tokens.

Each token is converted into a numerical vector called an embedding.

For example:

```text
"AI"       → [0.21, 0.45, 0.12, ...]
"software" → [0.32, 0.18, 0.67, ...]
```

These values are illustrative.

Embeddings allow the model to process numerical representations instead of raw text.

## 3.5 Positional Information

Transformers need information about token order.

Consider:

```text
The dog chased the cat.
The cat chased the dog.
```

The words are similar, but their meanings are different.

Positional information helps the model understand where tokens appear in a sequence.

Common techniques include:

- Sinusoidal positional encoding.
- Learned positional embeddings.
- Rotary Position Embeddings (RoPE).

## 3.6 Self-Attention

Self-attention allows each token to consider other relevant tokens in the input.

It uses three important representations:

| Component | Purpose |
|---|---|
| Query (Q) | Represents what information a token is looking for |
| Key (K) | Represents information used to determine relevance |
| Value (V) | Contains information that can be combined |

The model compares queries with keys to calculate attention scores.

These scores determine how much information is taken from each token's value.

**Important:** Query, Key and Value are learned mathematical projections of token representations, not separate pieces of text.

## 3.7 Multi-Head Attention

Multi-head attention performs multiple attention operations in parallel.

Different heads can learn different relationships or patterns in the input.

```text
       Input Representations
                 |
       +---------+---------+
       |         |         |
       v         v         v
     Head 1    Head 2    Head 3
       |         |         |
       +---------+---------+
                 |
                 v
           Combined Output
```

This helps the model capture multiple types of relationships simultaneously.

## 3.8 Feed-Forward Network

After attention, the Transformer applies a Feed-Forward Network (FFN) to further process token representations.

A simplified Transformer layer contains:

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

Real Transformer layers also use:

- Residual connections: Help information flow through deep networks.
- Layer normalization: Help stabilize network activations during training.

## 3.9 Stacking Transformer Layers

Transformers contain multiple layers.

Each layer processes representations from the previous layer.

As information passes through the network, the model builds increasingly sophisticated contextual representations.

## 3.10 Encoder vs Decoder Architecture

Transformers can follow three common architectural patterns.

| Architecture | Purpose | Example |
|---|---|---|
| Encoder-only | Understand and represent input | BERT |
| Decoder-only | Generate output autoregressively | GPT-style models |
| Encoder-Decoder | Transform input into output | T5 |

For generative LLM applications, decoder-only architectures are particularly important.

## 3.11 Causal Self-Attention

Decoder-only language models generally use causal self-attention.

It prevents a token from accessing future tokens during generation.

For example:

```text
The developer is building an AI
```

When predicting the next token, the model can use the preceding tokens but cannot use tokens that have not yet been generated.

This supports autoregressive generation.

## 3.12 How a Prompt Flows Through a Transformer

When an LLM receives a prompt:

1. The prompt is tokenized.
2. Tokens are converted into embeddings.
3. Positional information is incorporated.
4. Transformer layers process the representations.
5. The output layer produces scores called logits.
6. The scores are converted into probabilities.
7. A decoding strategy selects the next token.
8. The process repeats until generation stops.

**What an Applied AI Engineer needs to know:** Understand attention, embeddings, positional information, Transformer layers, and autoregressive generation. You do not need to implement a Transformer from scratch.

---

# 4. Tokens, Tokenization and Context Windows

## 4.1 What Is a Token?

A token is a basic unit of text processed by an LLM.

A token can represent:

- A complete word.
- Part of a word.
- Punctuation.
- A space combined with a word.
- Numbers or special characters.

Example:

```text
Input:
"Artificial Intelligence is powerful."

Possible tokens:
["Artificial", " Intelligence", " is", " powerful", "."]
```

A token is not necessarily the same as a word.

## 4.2 What Is Tokenization?

Tokenization converts text into tokens and corresponding numerical token IDs.

```text
Input Text
    |
    v
Tokenizer
    |
    v
Tokens
    |
    v
Token IDs
    |
    v
LLM
```

Example:

```text
Text: "Hello world"

Tokens: ["Hello", " world"]

Token IDs: [15339, 1917]
```

The IDs are illustrative. Actual values depend on the tokenizer.

Common tokenization approaches include:

- Byte Pair Encoding (BPE).
- WordPiece.
- Unigram Language Model.

Subword tokenization allows uncommon words to be represented using smaller units.

## 4.3 Why Do Tokens Matter?

Token counts affect:

**API Cost:** Many providers charge based on input and output token usage.

**Context Window:** Every token consumes part of the available context.

**Response Length:** Output token limits control how much text can be generated.

**Languages:** Different languages can require different token counts for similar amounts of text.

## 4.4 What Is a Context Window?

A context window is the maximum amount of token information a model can handle during a request and generation process.

It may include:

- System instructions.
- Developer instructions.
- User messages.
- Conversation history.
- Retrieved documents.
- Tool results.
- Generated output.

Example:

```text
Context Window: 100,000 tokens

Instructions:          2,000
Conversation History: 15,000
Retrieved Documents:  30,000
User Prompt:           1,000
Reserved Output:       2,000
Remaining Capacity:  50,000
```

This is an illustrative example.

The context window is measured in tokens, not words.

## 4.5 Context Window vs Memory

These are different concepts.

**Context Window:** Information supplied to the model for a particular request.

**Memory:** Information stored separately and potentially retrieved for future interactions.

Example:

A personal assistant stores a user's food preference in a database.

When the user asks for a meal plan, the application retrieves that preference and includes it in the prompt.

The model uses that information because it is included in the current context, not because it automatically remembers every past conversation.

## 4.6 What Happens When the Context Window Is Full?

Applications can manage context using:

| Technique | Purpose |
|---|---|
| Truncation | Remove older or less relevant content |
| Summarization | Replace long history with a shorter summary |
| Retrieval | Fetch only relevant information |
| Conversation Management | Retain important information separately |

## 4.7 Context Window vs Maximum Output Tokens

| Concept | Meaning |
|---|---|
| Context Window | Overall token capacity available to the request and generation |
| Maximum Output Tokens | Maximum tokens the model can generate in a response |

The exact limits and accounting behavior depend on the model and provider.

## 4.8 What Is a Token Budget?

A token budget is the amount of context or output space allocated to different parts of an AI request.

Example:

| Component | Token Budget |
|---|---:|
| Instructions | 1,000 |
| Conversation History | 5,000 |
| Retrieved Documents | 8,000 |
| User Prompt | 1,000 |
| Output Reservation | 2,000 |

Token budgeting helps control cost, context usage and response length.

**Applied AI relevance:** Token management becomes especially important in RAG applications and AI agents, where prompts may contain conversation history, retrieved documents and tool results.

---

# 5. Training and Inference

## 5.1 What Is Model Training?

Training is the process through which a model learns patterns from data by adjusting its internal parameters.

A simplified training process:

```text
Training Data
     |
     v
Model Prediction
     |
     v
Calculate Error (Loss)
     |
     v
Update Parameters
     |
     v
Repeat
```

For many LLMs, a major pre-training objective is predicting the next token.

## 5.2 Stages of LLM Training

### 1. Pre-training

The model learns general patterns from a large dataset.

It develops broad language capabilities and knowledge representations.

### 2. Supervised Fine-Tuning (SFT)

The model is further trained using curated examples of desired behavior.

Example:

```text
Input:
Explain what an API is.

Expected Output:
An API is an interface that allows software systems to communicate.
```

This helps the model follow instructions.

### 3. Alignment and Preference Optimization

The model is further optimized to produce responses that better match desired behavior and human preferences.

Common techniques include:

- RLHF: Reinforcement Learning from Human Feedback.
- DPO: Direct Preference Optimization.

These are examples of alignment methods; not every model uses the same pipeline.

## 5.3 What Is Inference?

Inference is the process of using an already-trained model to generate predictions or responses.

When your application calls an LLM API, the model performs inference.

```text
Application
    |
    v
Send Prompt to AI API
    |
    v
Trained Model
    |
    v
Inference
    |
    v
Generated Response
```

Normal inference does not update the model's learned parameters.

## 5.4 Training vs Inference

| Training | Inference |
|---|---|
| Learns from data | Generates predictions |
| Updates model parameters | Normally keeps parameters fixed |
| Requires training data | Requires prompts or input data |
| Computationally expensive | Cost depends on model and usage |
| Used during model development | Used whenever an application calls the model |

## 5.5 What Is Fine-Tuning?

Fine-tuning is additional training performed on an existing model using a specialized dataset.

It can help with:

- Domain-specific behavior.
- Consistent response formats.
- Specialized tasks.
- Particular writing styles.

Fine-tuning is not automatically the best way to provide frequently changing information to an LLM.

For external or frequently updated knowledge, RAG is often more appropriate.

## 5.6 Training, Fine-Tuning, RAG and Memory

| Concept | Purpose |
|---|---|
| Pre-training | Develop general model capabilities |
| Fine-tuning | Adapt model behavior through additional training |
| RAG | Provide relevant external information during inference |
| Memory | Store and retrieve information across interactions |
| Inference | Use the model to generate a response |

These mechanisms solve different problems.

**Applied AI relevance:** As an application developer, you will mostly work with inference, prompting, retrieval, tools and sometimes fine-tuning—not train foundation models from scratch.

---

# 6. Hallucinations and LLM Limitations

## 6.1 What Is an LLM Hallucination?

An LLM hallucination occurs when a model generates incorrect, fabricated or unsupported information while presenting it as if it were true.

Example:

A model invents a research paper title or provides an incorrect API function.

The response may sound convincing even when it is wrong.

## 6.2 Why Do LLMs Hallucinate?

Common reasons include:

- Missing information in the prompt.
- Ambiguous instructions.
- Outdated learned knowledge.
- Incomplete or conflicting context.
- Statistical text generation without inherent fact verification.

An LLM is not automatically a database or fact-checking engine.

## 6.3 Other LLM Limitations

| Limitation | Explanation |
|---|---|
| Knowledge limitations | May not know recent or private information |
| Context limitations | Has a finite context window |
| Reasoning errors | Can fail at complex logical or mathematical tasks |
| Non-determinism | Responses may vary |
| Bias | May reproduce biases in training data |
| Lack of real-world access | Cannot automatically inspect external systems |
| Security risks | Can be manipulated through prompt injection |
| Cost and latency | Requests consume resources and take time |

## 6.4 How Can Developers Reduce Hallucinations?

### 1. Prompt Engineering

Provide clear instructions and define how the model should handle missing information.

```text
Answer only using the provided information.

If the information is unavailable,
clearly state that you don't know.
```

### 2. Retrieval-Augmented Generation (RAG)

Retrieve relevant information from trusted sources and provide it to the model.

```text
User Question
     |
     v
Retrieve Relevant Documents
     |
     v
Provide Context to LLM
     |
     v
Generate Answer
```

RAG improves factual grounding but does not guarantee correctness.

### 3. Tool Calling

Allow the model to use external tools when reliable data or operations are required.

Examples:

- Calculator for calculations.
- Database queries for customer information.
- Weather API for current weather.
- Search API for current information.

### 4. Structured Outputs

Require the model to return information in a defined schema, such as JSON.

This improves format reliability but does not guarantee factual accuracy.

### 5. Validation

Validate generated outputs using deterministic application logic.

Examples:

- Verify product IDs against a database.
- Validate email addresses.
- Check permissions before executing an operation.
- Recalculate important numerical results.

### 6. Human Review

Use human approval for high-impact or sensitive operations.

## 6.5 Prompting vs RAG vs Fine-Tuning vs Tool Calling

| Technique | Purpose |
|---|---|
| Prompting | Guide model behavior |
| RAG | Provide external knowledge |
| Fine-Tuning | Adapt model behavior |
| Tool Calling | Interact with external systems |
| Validation | Check outputs against rules |

**Applied AI relevance:** Never assume an LLM-generated response is correct just because it is well written. Design the application to validate important outputs and actions.

---

# 7. Foundation Models and Model Configuration

## 7.1 What Is a Foundation Model?

A foundation model is a broadly trained model that can be used or adapted for multiple downstream tasks.

Examples of tasks:

- Text generation.
- Summarization.
- Translation.
- Classification.
- Question answering.
- Code generation.
- Image understanding.

Examples of model families include GPT, Claude, Gemini, Llama and Qwen.

## 7.2 Foundation Model vs Task-Specific Model

| Foundation Model | Task-Specific Model |
|---|---|
| Broad capabilities | Designed for a particular task |
| Can support multiple applications | Usually narrower in scope |
| Can be adapted for different tasks | Often requires task-specific development |

## 7.3 Model Parameters vs API Parameters

These terms are different.

**Model Parameters**

Learned numerical values inside a neural network. They are adjusted during training.

**API Parameters**

Configuration values supplied by developers during inference.

Common API settings include:

- Temperature.
- Top-p.
- Maximum output tokens.
- Stop sequences.
- Response format.

Available settings vary by provider and model.

## 7.4 Temperature

Temperature influences randomness during token selection.

Generally:

- Lower temperature: More predictable responses.
- Higher temperature: More varied responses.

Typical use cases:

| Temperature | Suitable Tasks |
|---|---|
| Low | Extraction and classification |
| Medium | General assistance |
| Higher | Creative generation |

Temperature behavior and supported ranges vary by model.

## 7.5 Top-p Sampling

Top-p is also called nucleus sampling.

It restricts token selection to the smallest group of candidate tokens whose cumulative probability reaches a specified threshold.

For example, top-p of 0.9 considers a candidate group containing approximately 90% of the cumulative probability mass.

Temperature and top-p influence generation differently. In practice, adjust one at a time when evaluating their effects.

## 7.6 Maximum Output Tokens

Controls the maximum number of tokens the model can generate in a response.

A low limit may produce incomplete answers.

A higher limit allows longer responses but can increase latency and cost.

## 7.7 Stop Sequences

Stop sequences are predefined strings or tokens that can tell a model to stop generating when encountered.

Support depends on the model and API.

## 7.8 How Should You Choose a Model?

Do not select a model only because it is the largest or most popular.

Evaluate:

| Factor | What to Consider |
|---|---|
| Accuracy | Does it solve the task correctly? |
| Latency | How quickly does it respond? |
| Cost | What are input and output costs? |
| Context Window | Can it handle the required information? |
| Reliability | Does it behave consistently? |
| Capabilities | Does it support tools, images or audio as needed? |
| Privacy | Does its data handling meet requirements? |

A smaller model may be sufficient for classification or extraction, while a more capable model may be needed for complex reasoning.

---

# 8. Multimodal AI

## 8.1 What Is Multimodal AI?

Multimodal AI refers to AI systems that process or generate information across multiple types of data.

Common modalities include:

- Text.
- Images.
- Audio.
- Video.

A multimodal assistant, for example, can accept an image and a question about it, then generate a text response.

## 8.2 Unimodal vs Multimodal

| Unimodal | Multimodal |
|---|---|
| Primarily processes one modality | Processes multiple modalities |
| Example: Text-only model | Example: Text and image model |

## 8.3 Image Understanding

Vision-capable models can process images and answer questions about their contents.

Applications include:

- Document understanding.
- Image classification.
- Visual question answering.
- Product recognition.
- Screenshot analysis.

Some models process images through patches or other internal visual representations.

## 8.4 Audio Understanding

Important audio capabilities include:

**Speech-to-Text (STT):** Converts spoken audio into text.

**Text-to-Speech (TTS):** Converts text into spoken audio.

**Audio Understanding:** Processes audio to identify speech, sounds and conversational context.

Applications include voice assistants, meeting transcription and customer support automation.

## 8.5 Video Understanding

Video-capable systems process visual information across time.

Applications include:

- Video summarization.
- Activity recognition.
- Video question answering.
- Video analysis.

Some systems sample video frames and process them along with audio or text.

## 8.6 Multimodal Generation

Some models can generate outputs across different modalities.

| Input | Possible Output |
|---|---|
| Text | Image |
| Text | Audio |
| Text | Video |
| Audio | Text |
| Text and image | Combined response |

Capabilities depend on the model and provider.

## 8.7 Example: Multimodal AI in an Application

Consider an invoice processing application.

```text
Scanned Invoice
      |
      v
Vision-Capable Model
      |
      v
Extract Invoice Information
      |
      v
Structured JSON
      |
      v
Application Validation
      |
      v
Save to Database
```

Example output:

```json
{
  "invoice_number": "INV-1024",
  "vendor": "ABC Technologies",
  "total_amount": 25000,
  "currency": "INR"
}
```

The values are illustrative. The application must validate extracted information before using it.

## 8.8 OCR vs Multimodal AI

OCR (Optical Character Recognition) extracts text from images and scanned documents.

Multimodal AI can go further by interpreting visual context and answering questions about the content.

| OCR | Multimodal AI |
|---|---|
| Extracts text | Interprets broader visual content |
| Focuses on text recognition | Can process text and non-text visual information |
| Produces extracted text | Can answer questions and generate structured outputs |

OCR remains useful when text extraction is the main requirement.

**Applied AI relevance:** Understand which model capabilities your application needs. Not every task requires a multimodal model.

---

# 9. Open-Weight vs Closed-Source Models

## 9.1 What Are Open-Weight Models?

Open-weight models make trained model weights available for download, subject to their licenses.

Examples include model families such as:

- Llama.
- Qwen.
- Mistral.
- Gemma.

However, downloadable weights do not necessarily mean that training data, training code and all development details are publicly available.

The terms "open-source" and "open-weight" should not be treated as interchangeable.

Always inspect the license of the specific model version.

## 9.2 What Are Closed-Source Models?

Closed-source models generally do not publicly release their complete model weights.

Developers commonly access them through hosted APIs or managed platforms.

Examples include:

- OpenAI GPT models.
- Anthropic Claude models.
- Google Gemini models.

Access options depend on the provider.

## 9.3 Open-Weight vs Closed-Source

| Factor | Open-Weight | Closed-Source |
|---|---|---|
| Model weights | Often downloadable | Generally not public |
| Hosting | Can often self-host | Usually provider-hosted |
| Customization | More deployment control | Depends on provider |
| Infrastructure | May require your own | Managed by provider |
| Maintenance | Your responsibility when self-hosting | Primarily provider-managed |
| Cost | Infrastructure and operations | API usage or subscription |
| Privacy | More deployment control is possible | Depends on provider policies |

Neither option is universally better.

## 9.4 What Is Self-Hosting?

Self-hosting means deploying and running a model on infrastructure you control.

Examples of hosting environments:

- Local computer.
- GPU server.
- Private cloud.
- Organization's data center.

Common tools include:

- Ollama.
- vLLM.
- Hugging Face Transformers.
- Hugging Face Text Generation Inference.

Self-hosting gives more control but introduces responsibilities such as:

- GPU provisioning.
- Memory management.
- Scaling.
- Monitoring.
- Security.
- Model updates.
- Availability.

## 9.5 Hosted AI Model APIs

A hosted model API allows an application to communicate with a model without managing its underlying model infrastructure.

```text
Application
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
Application
```

This is one of the most common approaches for integrating AI into software products.

## 9.6 How Should You Choose?

**Choose a hosted model API when:**

- You want to integrate AI quickly.
- You do not want to manage GPU infrastructure.
- The provider's model capabilities meet your needs.
- Pricing and data policies are acceptable.

**Consider an open-weight model when:**

- You need more control over deployment.
- You have specific data residency requirements.
- You want to customize or self-host a model.
- You have suitable infrastructure and operational resources.

## 9.7 Hybrid AI Architecture

An application can use different models for different tasks.

```text
             AI Application
                   |
         +---------+---------+
         |                   |
         v                   v
    Simple Tasks        Complex Tasks
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

- A smaller model for classification.
- A hosted model for complex reasoning.
- A vision-capable model for image understanding.

Model selection should be based on evaluation, reliability, latency, cost and privacy requirements.

## 9.8 Production Considerations

Before selecting a model, evaluate:

- **Licensing:** Are commercial use and redistribution permitted?
- **Privacy:** How does the provider handle submitted data?
- **Security:** How will sensitive information be protected?
- **Cost:** What are the API or infrastructure expenses?
- **Performance:** Does the model meet latency and throughput requirements?
- **Reliability:** Does it perform consistently on your tasks?
- **Portability:** Can the application switch models without major changes?

---

# Module 1: Key Takeaways

1. AI is the broader field; ML and Deep Learning are subsets of AI.
2. Generative AI creates content, and modern LLMs predominantly use Deep Learning.
3. LLMs generate text by predicting tokens based on context.
4. Transformers use self-attention to understand relationships between tokens.
5. Embeddings represent tokens numerically, while positional information represents their order.
6. Tokenization converts text into token IDs.
7. Context windows limit the information available during a model request.
8. Training adjusts model parameters; inference uses an already-trained model.
9. Fine-tuning, RAG and memory solve different problems.
10. Hallucinations mean generated information can be incorrect despite sounding convincing.
11. Prompting, retrieval, tool calling and validation help build more reliable applications.
12. Foundation models support multiple tasks and can be configured for different use cases.
13. Multimodal AI processes information such as text, images, audio and video.
14. Open-weight and closed-source models offer different deployment and operational trade-offs.

# Module 1: Interview Revision

**1. What is the difference between AI, ML and Deep Learning?**

AI is the broader field of intelligent systems. ML is a subset of AI that learns patterns from data. Deep Learning is a subset of ML that uses multi-layer neural networks.

**2. What is an LLM?**

A Deep Learning model trained on large amounts of data to process and generate language.

**3. How does an LLM generate text?**

Most autoregressive LLMs repeatedly predict and generate the next token based on preceding context.

**4. What is a Transformer?**

A neural network architecture that uses attention mechanisms to process sequences and capture relationships between tokens.

**5. What is self-attention?**

A mechanism that lets each token evaluate the relevance of other tokens and combine their information.

**6. What are Query, Key and Value?**

Learned representations used by attention to determine relevance and combine information.

**7. What is tokenization?**

Converting text into tokens and their corresponding numerical IDs.

**8. What is a context window?**

The maximum token capacity available to a model for processing a request and generating output.

**9. What is the difference between training and inference?**

Training adjusts model parameters using data. Inference uses the trained model to generate predictions.

**10. What is fine-tuning?**

Further training an existing model on specialized data to adapt its behavior.

**11. What is an LLM hallucination?**

An incorrect or unsupported response generated by a model and presented as if it were true.

**12. How can developers reduce hallucinations?**

Use relevant context, RAG, tool calling, validation and human review where appropriate.

**13. What is the difference between model parameters and API parameters?**

Model parameters are learned values inside the neural network. API parameters configure generation behavior during inference.

**14. What is multimodal AI?**

AI that can process or generate information across modalities such as text, images, audio and video.

**15. What is the difference between open-weight and closed-source models?**

Open-weight models make weights available under their licenses. Closed-source models generally expose access through provider-managed services.

---

# Module 1: References

## AI and Machine Learning

- [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course)
- [Deep Learning Book](https://www.deeplearningbook.org/)

## Transformers and LLMs

- [Attention Is All You Need — Original Research Paper](https://arxiv.org/abs/1706.03762)
- [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)
- [Hugging Face NLP Course](https://huggingface.co/learn/nlp-course/)

## Tokenization

- [OpenAI Tokenizer](https://platform.openai.com/tokenizer)
- [Hugging Face Tokenizers](https://huggingface.co/docs/tokenizers/index)

## Training and Fine-Tuning

- [Hugging Face Transformers Documentation](https://huggingface.co/docs/transformers/index)
- [InstructGPT Research Paper](https://arxiv.org/abs/2203.02155)
- [Direct Preference Optimization Paper](https://arxiv.org/abs/2305.18290)

## Multimodal AI and Models

- [Hugging Face Multimodal Documentation](https://huggingface.co/docs/transformers/tasks/image_text_to_text)
- [Meta Llama](https://www.llama.com/)
- [Qwen](https://qwen.ai/)
- [Mistral AI](https://mistral.ai/)
- [Google Gemma](https://ai.google.dev/gemma)

**Learning guidance:** You do not need to read every research paper in detail. Prioritize understanding the concepts, their practical applications and the trade-offs involved.