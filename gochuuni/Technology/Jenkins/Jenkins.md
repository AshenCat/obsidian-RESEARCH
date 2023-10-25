#### Overview
![[jenkins.png]]

Jenkins is a tool used for automation with CI and CD pipelines. It is claimed that Jenkins is the most commonly used automation server in software development. It allows you to automatically watch for certain events in your repository and react to those events. 

Jenkins allows you do things like build your code, run scripts, perform testing, and then deploy the app if everything passes, or reject the deployment if the test fails. Either way you will be able to see logs of every step of the pipeline and the results of the deployment. 

Jenkins can make sure that your tests are run in the same environtment, or in multiple environments as needed for consistency. Another benefit is that Jenkins have a huge community it has ammased over 20 years.

Another Feature of Jenkins is the plugin architecture. To use Jenkins properly, you will want to install the plugins that make sense to your project. These plugins includes options for compiling and testing, docker plugin, as well as git plugin that allows us to watch github repository and react to changes.

Jenkins is self-hosted by default. No need to pay for enterprise tier. This gives you a lot of options for configuration. it is also a tool that is proven to scale since it is used by a lot of companies around the world. Its not just large companies that uses Jenkins however, many small and medium companies as well.

Why do companies use it? many of them say that it improves their software delivery cycle by making them faster and more performant.

What are some of the benefits of using Jenkins over other alternatives? Jenkins is open source, many others are not. A big one is that you can self-host so you dont have to pay for enterprise plan and you have total control over configuration.

A drawback of using Jenkins is that most plug-ins rely on community support where it may become outdated, undocumented, or conflicting with another plug-in since anyone can create a plug-in. 

#### Terminologies
- **Continuous Integration (CI)** - is the practice of automating the integration of the code changes from multiple contributors into a single software project. It's a primary DevOps best practice, allowing developers to frequently merge code changes into a central repository where builds and tests then run. Automated tools are used to assert new code's correctness before integration.
- **Continuous Delivery (CD)** - is responsible for packaging the app and getting it ready to deploy using automated build tools . It is an extension of continuous integration since it automatically deploys all code changes to a testing and/or production environment after the build stage

![[CICD.png]]

- **Pipeline** - series of steps that build, test, and deploy autoomatically to environments
- **Controller** - main instance of Jenkins that is running. Responsible for configuration, key management, plugins, and centralized hub to manage all of the agents connecting to it.
- **Agents** - is typically a containerized environment that will run the pipeline steps or jobs.