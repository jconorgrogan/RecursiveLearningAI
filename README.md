# RecursiveLearningAI
Really quick-and-dirty example of AI recursive learning (video in action:https://x.com/jconorgrogan/status/1853943122046144829) ; The TLDR is that we can make AI "Learn" via smart, recursive workflows that rejigger the context window.  Goes as followis:

1. Digest user query. Send towards two paths in parrellel:
2. Answer query
3. Have one LLM create test cases for a user query
4. Then,pass LLM's answer through the tests cases
5. Have a judge LLM review those responses for logic errors
6. Another LLM call collects those learnings
7. They then create a new prompt which amends the original user prompt with the learnings of the LLMs iterations, and sends that through to the model
8. This process repeats until all logic tests are passed, and the answer is returned to the user

This image is the result of two recursive iterations. The initial starting prompt was, "Construct a sentence where none of the words in that sentence are in the Bible", which o1preview constantly struggles with. As you can see, by the end the "user query" had changed a lot, with learnings 

<img width="1479" alt="image" src="https://github.com/user-attachments/assets/8c637b0d-6150-44a0-9c06-48a8352cfe51">

Insert your OpenAI key to the "Proofofconcept.html" run and try it.

 **Future exploration ideas**

**Example #1: [Not yet in production]**

1. Input prompt, have llm break down goal to the most basic components 
2. test those components, individually, each with a context wiped new pull 
3. have an llm summarize the results; if all pass then pass full response to user. if fail, then synthesize learnings 
4. another llm takes these learnings and then constructs a new prompt with new context, amending the original user prompt 
5. this happens recursively again and again until the test are all passed
6. Have an LLM then synthesize the best possible answer given original goal
7. Return to user

**Example #2; introspective/entropix-esque [Not yet in production]**
1. User query
2.  LLM responds
3. Overseer LLM #1 Check branches of that response to assess alternate answers possibilities
4. Overseer LLM #2 triggers completion  for those "alternative universe" tokens 
5. context compressed and sent to an  LLM evaluates all COT output from unique branches 
6. LLM responds given best answer
7. you can even loop this if you want to, eg if there are branches in best answer from the entropy/varentropy profile
8. Return that answer to user, via an LLM that is focused on response formatting/user objective

**Example #3 Introspective pruning- [See 9.11or9.9Solver html file for proof-of-concept which has an LLM replace any numbers like 9.11 (which fire calandar-related activations) with short math equations (9+0.11)]**
1. User querys
2. LLM responds
3. LLM reviews neuron activations, if any fire in domains that are counter to the user goal, seek to clamp those down
4. Alter context/prompt with tokens that still compress the user goal, but in a way that uses tokens that minimize neuron activation for activity that could negatively impact the output
