# 💬 Chatbot template



This code implements a simple chatbot application using Streamlit and OpenAI's GPT-3.5 model.

1. **Streamlit Setup**: 
   - The app begins by importing Streamlit (`import streamlit as st`) and OpenAI's API client (`from openai import OpenAI`).
   - The title "💬 Chatbot" is displayed, followed by a brief description that explains the purpose of the app. It mentions the requirement of an OpenAI API key and provides a link to obtain one.

2. **API Key Input**:
   - The app asks the user to input their OpenAI API key via `st.text_input`. The key is kept hidden by setting the input type to `"password"`.
   - If the user hasn't entered a key, a message prompts them to add one.

3. **OpenAI Client**:
   - If the API key is provided, an OpenAI client (`client = OpenAI(api_key=openai_api_key)`) is created using the provided key.

4. **Session State**:
   - A session state variable (`st.session_state.messages`) is used to store chat messages across reruns, ensuring the chat history persists.

5. **Displaying Chat History**:
   - The existing chat messages are displayed using `st.chat_message`, which iterates through the stored messages in the session state and renders them accordingly.

6. **Chat Input**:
   - The user is prompted to enter a message via `st.chat_input`.
   - Upon submitting a message, it is added to the session state under the "user" role and displayed in the chat.

7. **Generating Responses**:
   - The app sends the chat history (user and assistant messages) to the OpenAI API using `client.chat.completions.create()`.
   - The API response is streamed back in real-time, and it is displayed in the chat interface.

8. **Updating Chat**:
   - The assistant's response is appended to the session state, ensuring the conversation continues with the new messages displayed.

This app provides a simple way for users to interact with GPT-3.5 through a chatbot interface, making it easy to integrate OpenAI's model into conversational apps.
