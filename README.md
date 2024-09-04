

# Research Paper: **Specific AI Technologies For Improving Customer Service In Restaurants**

---

## API Section: **Zajil API**

The Zajil API is a set of tools that helps restaurants improve customer service by managing orders and interactions through voice and text. It also includes features for restaurant managers to track and manage orders and menu items.

### What is an API?

An API (Application Programming Interface) is like a bridge that lets different software programs talk to each other. In this case, the Zajil API helps the restaurant's system interact with customers, process orders, and provide information.

---

### Key Functions of the Zajil API

Here’s a simple breakdown of what the Zajil API can do:

1. **Welcome Message**  
   **What It Does**: Sends a welcome message to the customer.
   - **Example**: When a customer connects, they receive a greeting message saying, “Welcome to Zajil!”

2. **Handle Orders via Voice**  
   **What It Does**: Listens to the customer’s voice request, processes it, and responds with a voice message.
   - **Example**: If a customer says, "I want to order a pizza," the system responds with a voice message asking for more details, like "What kind of pizza would you like?"

3. **Handle Orders via Text**  
   **What It Does**: Reads the customer’s typed message and responds with a text message.
   - **Example**: If a customer types, "I want to order a pizza," the system replies with a text message asking, "What type of pizza would you like?"

4. **Show Order History**  
   **What It Does**: Displays the history of past orders for the customer.
   - **Example**: If a customer asks, “What did I order last time?” the system shows a list of their previous orders.

5. **Complete the Order**  
   **What It Does**: Finalizes the order and confirms with the customer.
   - **Example**: After processing the order, the system says, “Your order is complete. It will be delivered soon.”

6. **Play Back Voice Response**  
   **What It Does**: Allows the customer to listen to the voice message again.
   - **Example**: If a customer wants to hear a previous voice message again, they can request to replay it.

7. **Show All Orders**  
   **What It Does**: Lists all orders placed by the customer.
   - **Example**: If a customer asks, "What have I ordered in the past?" the system lists all their orders.

8. **Show All Products**  
   **What It Does**: Displays all available food and drink items on the restaurant’s menu.
   - **Example**: If a customer asks, "What do you have on the menu?" the system shows a list of available items.
---

## Database Schema

Here’s a table format for the Zajil API’s database schema:

### Chat Table

| **Field**      | **Type**    | **Description**                              |
|----------------|-------------|----------------------------------------------|
| `id`           | Integer     | Unique identifier for the chat record        |
| `chat_id`      | String      | Identifier for the chat session              |
| `role`         | String      | Role of the entity (user/system)             |
| `content`      | Text        | Content of the chat message                  |
| `is_voice`     | Boolean     | Indicates if the message is a voice message  |
| `voice`        | String      | URL or identifier for the voice message      |
| `user_phone`   | String      | Phone number of the user                    |
| `language`     | String      | Language of the message                     |
| `create_at`    | Timestamp   | Timestamp when the message was created       |

### Order Table


| **Field**      | **Type**    | **Description**                              |
|----------------|-------------|----------------------------------------------|
| `id`           | Integer     | Unique identifier for the order              |
| `chat_id`      | String      | Identifier for the related chat session      |
| `order`        | Text        | Details of the order                         |
| `status`       | String      | Status of the order (e.g., pending, completed) |
| `location`     | String      | Delivery location                            |
| `price`        | Decimal     | Total price of the order                     |
| `user_phone`   | String      | Phone number of the user                    |
| `create_at`    | Timestamp   | Timestamp when the order was created         |

### Product Table

| **Field**      | **Type**    | **Description**                              |
|----------------|-------------|----------------------------------------------|
| `id`           | Integer     | Unique identifier for the product            |
| `name`         | String      | Name of the product                          |
| `price`        | Decimal     | Price of the product                         |
| `ingredients`  | Text        | Ingredients included in the product          |
| `category`     | String      | Category of the product                      |
| `stock`        | Integer     | Available stock quantity                     |
| `create_at`    | Timestamp   | Timestamp when the product was added         |

### Token Table

| **Field**      | **Type**    | **Description**                              |
|----------------|-------------|----------------------------------------------|
| `id`           | Integer     | Unique identifier for the token record       |
| `token`        | Integer     | Number of tokens used                       |
| `create_at`    | Timestamp   | Timestamp when the token record was created |


---

## Dashboard Section

The Dashboard provides a control panel for restaurant managers to monitor and manage various aspects of their operations. 

### Key Features of the Dashboard

1. **Order Summary**  
   **What It Does**: Displays a summary of all current and past orders.
   - **Example**: A manager can view all orders placed today and their statuses.

2. **Manage Orders**  
   **What It Does**: Allows managers to review, update, and manage all orders.
   - **Example**: A manager can check the status of each order and make adjustments if needed.

3. **Product Management**  
   **What It Does**: Enables managers to add, update, or remove items from the menu.
   - **Example**: If the restaurant introduces a new dish, the manager can add it to the menu through the dashboard.

4. **Chat History**  
   **What It Does**: Shows the history of customer interactions, including chat messages and voice conversations.
   - **Example**: A manager can review past conversations between customers and the system to understand common queries and issues.

---
Certainly! Here’s a detailed overview of the AI models used in the Zajil system, including their functions, technologies, and significance, as well as a description of the lifecycle and functionalities. I've also included a table format for the database schema.

---

## Models Used

The AI models embedded in the Zajil system are crucial for processing requests, generating responses, and managing resources efficiently. Below is a detailed overview of these models:

| **Model**        | **Function**                                   | **Technology Used**                   | **Significance**                                             |
|------------------|------------------------------------------------|---------------------------------------|-------------------------------------------------------------|
| **Calculate Tokens** | Calculates token usage for text processing | GPT-like models                       | Optimizes resource usage and cost management                |
| **Generate Voice**   | Converts text to speech                     | TTS technologies like ElevenLabs API  | Enhances user interaction through voice interfaces          |
| **Ask AI**          | Processes user input and generates responses | GPT-based NLP                         | Central to delivering coherent and contextually accurate responses |
| **Process Chat**     | Manages chat flow, integrating various models | Integrated NLP and data logging       | Ensures real-time, responsive, and accurate conversation management |

### Model Descriptions

1. **Calculate Tokens**
   - **Function**: This model calculates the number of tokens used during text processing. Tokens are units of text that the system processes. By managing token usage, the system can optimize costs and ensure efficient resource allocation.
   - **Technology Used**: Based on GPT-like models, which are used to handle and process natural language text.

2. **Generate Voice**
   - **Function**: Converts written text into spoken words, allowing the system to interact with users through voice. This feature is crucial for systems that support voice-based interactions.
   - **Technology Used**: Text-to-Speech (TTS) technologies, such as ElevenLabs API, which provides high-quality voice synthesis.

3. **Ask AI**
   - **Function**: This model processes user inputs, such as questions or commands, and generates appropriate responses. It forms the core of the conversational capabilities of the system.
   - **Technology Used**: GPT-based Natural Language Processing (NLP) models, which are designed to understand and generate human-like text based on context.

4. **Process Chat**
   - **Function**: Manages the flow of chat interactions, ensuring that different models work together seamlessly to provide a coherent conversation experience. It integrates NLP and data logging to keep track of chat history and user interactions.
   - **Technology Used**: Integrated NLP systems combined with data logging techniques to manage real-time conversations and ensure accurate responses.

---

## Lifecycle and Functionalities

### Lifecycle

1. **User Interaction**
   - **Stage**: User initiates interaction via text or voice.
   - **Function**: The system receives input from the user, which is then processed by the AI models.

2. **Processing Input**
   - **Stage**: Input is processed by the "Ask AI" model.
   - **Function**: The model interprets the user's request and generates a response based on context and content.

3. **Token Management**
   - **Stage**: Token usage is calculated.
   - **Function**: The "Calculate Tokens" model tracks token usage for cost and resource management.

4. **Response Generation**
   - **Stage**: Response is generated and delivered.
   - **Function**: Depending on the interaction type, the response is either converted to speech by the "Generate Voice" model or displayed as text.

5. **Chat Management**
   - **Stage**: Chat flow is managed.
   - **Function**: The "Process Chat" model ensures smooth and accurate management of the conversation, logging interactions and maintaining context.

### Functionalities

- **Text and Voice Interaction**: Users can interact with the system via text or voice, and the system responds appropriately based on the input type.
- **Contextual Understanding**: The system understands and processes user requests in context, ensuring relevant and accurate responses.
- **Efficient Resource Management**: By calculating token usage, the system optimizes the use of computational resources and manages costs effectively.
- **Real-time Conversation Management**: The system maintains coherent and responsive conversations by managing chat flows and integrating various AI models.
---
