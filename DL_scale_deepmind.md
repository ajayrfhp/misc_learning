# Building deep learning systems at scale

[Video link](https://www.youtube.com/watch?v=JWRaPjb7ml8)

- What is intelligence ?
  - Ability to learn to perform well over a wide range of environments
  - Learn from raw inputs, and solve a wide range of problems

- Deep RL intuition
  - Connect current state to goal state
  - State space is too large, use function approximators
  - Take actions, observe reward and propagate information back through time
  - Generate lots of examples by self exploration
  - Use ideas from Dynamic programming

- Scaling RL
  - Run many parallel actors in the environment
  - Actor critic policy
    - Actor produces policy estimates
    - Critic produces Q estimates. 
    - Critic >> Actor in terms of parameters
    - Actors run policy and store results in replay table
    - learners look at results from replay table and update parameters of actor networks
    - Actors do inference and learners do supervised learning. 