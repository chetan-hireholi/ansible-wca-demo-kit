# IBM watsonx Code Assistant repository for Red Hat Ansible Lightspeed demo

<h3>This repository contains examples which you can use to test out the capabilities of IBM watsonx Code Assistant for Ansible Lightspeed.</h3>

With this VM demo you can test:
- Inferencing from natural language requests.
- Single-task and multi-task content generation for Playbooks
- Content source matching and transparency.

<h3>Getting started</h3>  

<h4>Step 1: Setup your environment</h4>

1. IBM Sellers/Client have to provision a VM at https://techzone.ibm.com/collection/watsonx-code-assistant/journey-code-assistant-for-ansible-lightspeed
2. Update your working directory (`/home/techzone/Documents/ansible-wca-demo-kit`) with the latest examples: Perform `git fetch` & `git pull` on the VS Code terminal.
3. Each example has its own README.md to help give context. You can follow the instructions within the README.md or the individual YAML files.
<img title="Example README.md" src="/Images/Example-read-me.png">

<h4>Step 2: Trying out examples</h4>

We have uploaded few basic scenarios which gives you an idea on how watsonx Code Assistant can interpret the natural lanuguage in prompts and further by uncommenting and hitting `Enter`, you can get content suggestions. To accept the content suggested, hit `Tab`.
<img title="Example list" src="/Images/Example-uncomment.png">

<h4>Step 3: Going beyond examples</h4>

- You can test your own scenarios by writing new playbooks and modifying the prompts the way you like it.
- For single-task content generation, you can type in the task you want to perform in plain english after the `name` parameter and press `Enter` when you are done. Lightspeed will fetch you suggestions from watsonx Code Assistant.
  - <img title="Example list" src="/Images/Single-task.png">
- For multi-task content generation, you can type in the set of tasks separated by an `&` below the `tasks` parameter.
  - <img title="Example list" src="/Images/Multi-task.png">

#### FAQs

1. Who are the main audience for this demo setup? _ONLY IBM INTERNAL. IBM Sellers & IBM Client Engineering teams. To provision a VM go to: https://techzone.ibm.com/collection/watsonx-code-assistant/journey-code-assistant-for-ansible-lightspeed_
2. What is the purpose of this demo setup? _This technical content can help you get acquainted with watsonx Code Assistant's features and provide you an opportunity for a live demo to clients_
3. Even after logging into the VM, it asks me to re-authenticate. Which credentials to provide? _The same credentials you input to connect to the VM_

#### Thank You
_Thanks Pete Nuwayser, Craig Brandt for helping in curating these examples. Some examples _Forked from_ https://github.com/craig-br/lightspeed-demos_
