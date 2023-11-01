# IBM watsonx Code Assistant repository for Red Hat Ansible Lightspeed demo

<h2>This repository contains examples which you can use to test out the capabilities of IBM watsonx Code Assistant for Ansible Lightspeed.</h2>

With this VM demo you can test:
- Inferencing from natural language requests.
- Single-task and multi-task content generation for Playbooks
- Content source matching and transparency.

<h2>Getting started</h2>  

<h3>Step 1: Setup your environment</h3>

1. IBM Sellers/Client have to provision a VM at https://techzone.ibm.com/collection/watsonx-code-assistant/journey-code-assistant-for-ansible-lightspeed
2. Update your working directory (`/home/techzone/Documents/ansible-wca-demo-kit`) with the latest examples: Perform `git fetch` & `git pull` on the VS Code terminal.
3. Each example has its own README.md to help give context. You can follow the instructions within the README.md or the individual YAML files.
<img title="Example README.md" src="/Images/Example-read-me.png">

<h3>Step 2: Trying out examples</h3>

We have uploaded few basic scenarios which gives you an idea on how watsonx Code Assistant can interpret the natural lanuguage in prompts and further by uncommenting and hitting `Enter`, you can get content suggestions. To accept the content suggested, hit `Tab`.
<img title="Example list" src="/Images/Example-uncomment.png">

<h3>Step 3: Testing Single-task and Mutli-task Playbook content generation</h3>

<h4>Traditional Playbook writing experience</h4>

In your Playbook writing experience, you usally tend to write it in a step-by-step approach. You write the single-tasks one after the other. 
<img title="Example list" src="/Images/AWS-single-task-traditional.png">

<h4>Speed up Playbook writing with Single-task & Multi-task content generation</h4>

- The Generative AI capabilities of watsonx Code Assistant will enable you complete your IT Automation in Playbook faster.
- Simply provide your intent in plain English language and watsonx Code Assistant will return the content suggestion for it.
- In the below example we show single-task prompt and the recommendation by watsonx Code Assistant:
<img title="AWS example" src="/Images/AWS-single-task.png">

- Now, take it to the next level by giving all the IT Automation instructions/tasks together. Type in all the individual tasks below the `tasks` parameter by separating it with an `&`. You should comment the line in order for watsonx Code Assistant to interpret the prompt.
- In the below example we show multi-task prompt and the recommendation by watsonx Code Assistant:
<img title="AWS example" src="/Images/AWS-Multi-task-recommendation.png">

This comment line now acts as a prompt to the watsonx Code Assistant.

<h3>Step 3: Going beyond examples</h3>

- Now that you know how watsonx Code Assistant can interpret the prompts, you can start framing your IT Automations in a sentance and just hit `Enter`
- You can test your own scenarios by writing new playbooks and modifying the prompts the way you like it.

#### FAQs

1. Who are the main audience for this demo setup? _ONLY IBM INTERNAL. IBM Sellers & IBM Client Engineering teams. To provision a VM go to: https://techzone.ibm.com/collection/watsonx-code-assistant/journey-code-assistant-for-ansible-lightspeed_
2. What is the purpose of this demo setup? _This technical content can help you get acquainted with watsonx Code Assistant's features and provide you an opportunity for a live demo to clients_
3. Even after logging into the VM, it asks me to re-authenticate. Which credentials to provide? _The same credentials you input to connect to the VM_

#### Thank You
_Thanks Pete Nuwayser, Craig Brandt for helping in curating these examples. Some examples _Forked from_ https://github.com/craig-br/lightspeed-demos_
