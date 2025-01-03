## How to provision an EC2 instance

#### This example will:
1. Create a new VPC
2. Create a new security group
3. Create a new internet gateway
4. Create a new subnet
5. Create a new route table for subnet and gateway
6. Provision a t2.small EC2 instance in that subnet

You can execute this example in two ways: "**Single-task**" and "**Multi-task**".

#### Traditional Playbook writing experience

In your Playbook writing experience, you usally tend to write it in a step-by-step approach. You write the single-tasks one after the other. 
<img title="Example list" src="/Images/AWS-single-task-traditional.png">

#### Speed up Playbook writing with Single-task and Multi-task content generation

- The Generative AI capabilities of watsonx Code Assistant will enable you complete your IT Automation in Playbook faster.
- Simply provide your intent in plain English language and watsonx Code Assistant will return the content suggestion for it.
<img title="AWS example" src="/Images/AWS-single-task.png">

- Now, take it to the next level by giving all the IT Automation instructions/tasks together. Type in all the individual tasks below the `tasks` parameter by separating it with an `&`. You should comment the line in order for watsonx Code Assistant to interpret the prompt.
<img title="AWS example" src="/Images/AWS-Multi-task.png">
<img title="AWS example" src="/Images/AWS-Multi-task-recommendation.png">

This comment line now acts as a prompt to the watsonx Code Assistant.

#### Time to experiment!

Now that you know how watsonx Code Assistant can interpret the prompts, you can start framing your IT Automations in a sentance and just hit `Enter`
