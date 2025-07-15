# LangGraph Quick Answers

## Q1: How does the model determine which tool to use?
The model analyzes the query content and selects tools based on context. 

## Q2: Is there a cycle limit? How to impose one?
for breakout room 1 no default limit exists. 

## Q3: How are answers matched to questions?
By position - Question[0] matches Answer[0], Question[1] matches Answer[1], etc. Lists must stay synchronized.

## Q4: Ways to improve the metric?

- Partial credit scoring
- Semantic similarity with embeddings
- Context awareness

## Q5: What does tool_call_or_helpful do?
Checks if response is good enough. If not helpful → retry. If helpful → end. Uses GPT-4-mini to self-evaluate responses. Prevents infinite loops with 10-message limit.

## Activity 2: Agent steps diagram
See tool_trace_flow.png for visual flow of agent decisions and tool calls.

## Activity 5: Cell explanations
- **Cell 65**: Creates graph, adds agent and action nodes
- **Cell 67**: Sets agent as entry point
- **Cell 72**: Adds conditional routing with helpfulness check
- **Cell 74**: Routes from action back to agent
- **Cell 76**: Compiles graph for execution
- **Cell 78**: Tests with multi-part question