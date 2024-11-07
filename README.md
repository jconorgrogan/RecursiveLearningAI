# RecursiveLearningAI
Really quick-and-dirty example of AI recursive earning; The TLDR is that you have an LLM create test cases for a user query, then pass another LLM's answer to a user query through those use cases, then have a judge LLM review those responses for logic errors, then have another LLM call collect those learnings and create a new prompt which amends the original user prompt with the learnings of the LLMs iterations

1. Insert your OpenAI key to the "Proofofconcept.html" run and try it.

**Future exploration ideas ****

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
