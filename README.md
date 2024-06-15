# Function Calling in AI Applications

**Function calling** allows you to integrate Large Language Models (LLMs) with external tools for effective usage and interaction with APIs.

LLMs like GPT-4 and GPT-3.5 can detect when a function needs to be called and generate JSON arguments for those functions. These functions act as tools in your AI application, and multiple functions can be defined in a single request.

## Basic Sequence of Steps for Function Calling

1. **Initial Call:** Call the model with the user query and a set of functions defined in the functions parameter.
   
2. **Function Detection:** The model can choose to call one or more functions. The content will be a stringified JSON object in your custom schema (note: the model may hallucinate parameters).

3. **Parsing and Execution:** Parse the string into JSON in your code, and call your function with the provided arguments if they exist.
   
4. **Response Handling:** Call the model again, appending the function response as a new message. Let the model summarize the results back to the user.

## Example: Sending Email with Gemini and Open Source Models
