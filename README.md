# RecursiveLearningAI
Really quick-and-dirty example of AI recursive learning. Proof of concept using only one request (Hardcoded example on finding a sentence that isnt in the bible, which o1 struggles with. Would love if more generalizable workflows are made. You can see that a lot of features im working on are dormant in the file itself. 

Insert your OpenAI key to run and try it. 

I believe that with enough memory and prompt engineering, 70b models WILL beat 4o out of the gate:

Example #1:

1. Input prompt, have llm break down goal to the most basic components 
2. test those components, individually, each with a context wiped new pull 
3. have an llm summarize the results; if all pass then pass full response to user. if fail, then synthesize learnings 
4. another llm takes these learnings and then constructs a new prompt with new context, amending the original user prompt 
5. this happens recursively again and again until the test are all passed
6. Have an LLM then synthesize the best possible answer given original goal
7. Return to user


Example #2; introspective/entropix-esque
1. User query
2.  LLM responds
3.Overseer LLM #1  Check branches of that response to assess alternate answers possibilities
4. Overseer LLM #2 triggers completion  for those "alternative universe" tokens 
5. context compressed and sent to an  LLM evaluates all COT output from unique branches 
6. LLM responds given best answer
7. you can even loop this if you want to, eg if there are branches in best answer from the entropy/varentropy profile
8. Return that answer to user, via an LLM that is focused on response formatting/user objective
