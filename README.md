Function calling is the ability to reliably connect LLMs to external tools to enable effective tool usage and interaction with external APIs

LLMs like GPT-4 and GPT-3.5 have been fine-tuned to detect when a function needs to be called and then output JSON containing arguments to call the function

The functions that are being called by function calling will act as tools in your AI application and you can define more than one in a single request.


The basic sequence of steps for function calling is as follows:
1. Call the model with the user query and a set of functions defined in the functions parameter.


2. The model can choose to call one or more functions; if so, the content will be a stringified JSON object adhering to your custom schema (note: the model may hallucinate parameters).


3. Parse the string into JSON in your code, and call your function with the provided arguments if they exist.


4. Call the model again by appending the function response as a new message, and let the model summarize the results back to the user.


In this example we sending email with Gemini and few open source models
