## Ansible - The Complete IT Automation

### Contents

- Why Ansible?

- Its Architecture

- Design Goals

- Manage Your inventory in simple text files

- SSH keys are your friends

- Playbook: A Automation Language

- Use Cases

- Advantage & Disadvantage 

**Ansible **is a radically simple IT automation engine that automates cloud provisioning, configuration management, application deployment, intra-service orchestration, and many other IT needs.

Designed for multi-tier deployments since day one, Ansible models your IT infrastructure by describing how all of your systems inter-relate, rather than just managing one system at a time. It uses no agents and no additional custom security infrastructure, so it's easy to deploy - and most importantly, it uses a very simple language (YAML, in the form of Ansible Playbooks) that allow you to describe your automation jobs in a way that approaches plain English.

### WHY ANSIBLE?🤔
There are many other IT automation tools available, including more mature ones like Puppet and Chef, so why would you choose Ansible? The main reason is simplicity. Michael DeHaan, the creator of Ansible, already had a lot of experience with other configuration management tools when he decided to develop a new one. He said that he wanted “a tool that you could not use for six months, come back to, and still remember.”

DeHaan accomplished this by using YAML, a simple configuration language. Puppet and Chef, on the other hand, use Ruby, which is more difficult to learn. This makes Ansible especially appealing to system administrators.

DeHaan also simplified Ansible deployment by making it agentless. That is, instead of having to install an agent on every system you want to manage (as you have to do with Puppet and Chef), Ansible just requires that systems have Python (on Linux servers) or PowerShell (on Windows servers) and SSH.


![1612699066480.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1620643336694/2FyGdRHd2.png)

### ARCHITECTURE 🛠

Ansible works by connecting to your nodes and pushing out small programs, called "Ansible Modules" to them. These programs are written to be resource models of the desired state of the system. Ansible then executes these modules (over SSH by default) and removes them when finished.

Your library of modules can reside on any machine, and there are no servers, daemons, or databases required. Typically you'll work with your favorite terminal program, a text editor, and probably a version control system to keep track of changes to your content.

### DESIGN GOALS 🎯
The design goals of Ansible include:

- **Minimal in nature**. Management systems should not impose additional dependencies on the environment.
- **Consistent**. With Ansible one should be able to create consistent environments.
- **Secure**. Ansible does not deploy agents to nodes. Only OpenSSH and Python are required on the managed nodes.
- **Highly reliable**. When carefully written, an Ansible playbook can be idempotent, to prevent unexpected side-effects on the managed systems. It is entirely possible to have a poorly written playbook that is not idempotent.
- **Minimal learning required**. Playbooks use an easy and descriptive language based on YAML and Jinja templates.

### MANAGE YOUR INVENTORY IN SIMPLE TEXT FILES 📃
By default, Ansible represents what machines it manages using a very simple INI file that puts all of your managed machines in groups of your own choosing. 

To add new machines, there is no additional SSL signing server involved, so there's never any hassle deciding why a particular machine didn’t get linked up due to obscure NTP or DNS issues. If there's another source of truth in your infrastructure, Ansible can also plugin in that, such as drawing inventory, group, and variable information from sources like EC2, Rackspace, OpenStack, and more.

### SSH KEYS ARE YOUR FRIENDS 🔑
Passwords are supported, but SSH keys with ssh-agent are one of the best ways to use Ansible. Though if you want to use Kerberos, that's good too. Lots of options! Root logins are not required, you can log in as any user, and then su or sudo to any user.

Ansible's "authorized_key" module is a great way to use ansible to control what machines can access what hosts. Other options, like Kerberos or identity management systems, can also be used.

![1612699212158.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1620643354459/wfoP631YL.png)

### PLAYBOOKS: A AUTOMATION LANGUAGE 💻

Playbooks can finely orchestrate multiple slices of your infrastructure topology, with very detailed control over how many machines to tackle at a time. This is where Ansible starts to get most interesting.

They are YAML files that express configurations, deployment, and orchestration in Ansible, and allow Ansible to perform operations on managed nodes. Each Playbook maps a group of hosts to a set of roles. Each role is represented by calls to Ansible tasks.


![1612701327697.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1620643590522/f38Ps20iB.png)

### USE CASES 😎
There are 6 main places where ansible is being used right now:

- **Provisioning **- All the services like websites, apps, etc. need to be deployed somewhere and ansible helps in provisioning the deployment environment like virtual machines, cloud platforms, etc. 
-** Configuration Management** - Ansible is widely being used as a configuration management tool.
- **Application Deployment** - When you define your application with Ansible and manage the deployment with Ansible Tower
- **Continuous delivery** - Creating a CI/CD pipeline requires buy-in from numerous teams. You can’t do it without a simple automation platform that everyone in your organization can use. 
- **Security **- When you define your security policy in Ansible, scanning, and remediation of security policy can be integrated into other automated processes.
- **Orchestration **- Configurations alone don’t define your environment. 

### ADVANTAGE OF USING ANSIBLE 🤩
1. Can perform tasks parallelly at a time on multiple servers.
2. No need to install any agent on the client machine. Or we can say Ansible is agentless.
3. No need to open any external port. Ansible uses ssh service port.
4. Configuration management
5. We can manage our deployment.

### DISADVANTAGE OF USING ANSIBLE 😓
1. Error reporting method is not user-friendly. It will display numbers of lines in logs that will create confusion at all times.
2. After executing the playbook, we cannot edit it. If we will do ansible will not update the latest changes.
3. Ansible is OS-dependent means it is not necessary playbook that is working on Centos will work on Ubuntu also.

![1612701354307.jfif](https://cdn.hashnode.com/res/hashnode/image/upload/v1620643576658/00tokwsUF.jpeg)

I hope you found the article useful😃! If this is something that interests you, please share the article with your friends and connections🤝& also hit the like button ❤️. It will encourage me to write more such articles. You can also subscribe to my newsletter to get updates every time I write something!. Thank you for reading😊.

This article was originally posted on  [Linkedin](https://www.linkedin.com/pulse/ansible-complete-automation-prathmesh-bhansali/).