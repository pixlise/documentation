# Environment Management Application

To help manage the different environments and software versions along with the review environment capability, we have developed a basic environment management application that edits the files and runs the pipelines for you so you don't have to remember the steps required.

### Access

You can login to the environment by visiting this url:

{% embed url="http://ad883bb45ed2a42dda94831caa991a5d-9909360.us-east-1.elb.amazonaws.com/" %}

Credentials can be obtained from other members of the Pixlise team.

Once you've logged in you should be greated with the following screen

<figure><img src="../.gitbook/assets/Screenshot 2023-01-06 143803.png" alt=""><figcaption><p>Release Manager Landing Page</p></figcaption></figure>

### Updating a Fixed Environment

If you click on the Fixed Environment Management link you'll be sent to a screen that looks like this:

<figure><img src="../.gitbook/assets/Screenshot 2023-01-06 143820.png" alt=""><figcaption><p>Fixed Environments Screen</p></figcaption></figure>

Here you can see the configuration for the different fixed environments. From here you can then click the Edit button to make changes to an environment.

<figure><img src="../.gitbook/assets/Screenshot 2023-01-06 143838.png" alt=""><figcaption><p>Edit Environment Screen</p></figcaption></figure>

Once you've landed on the edit environment screen you can change a few variables.

Pipeline Name links the environment to a certain pipeline we have stage and prod, these process the incoming data so that we can simulate data processing prior to it going live.

Then there is the UI and API image tag, these are read from Github and allow you to pick from the list, to help reduce the likelyhood of typos.

When you press the Update button it will update the files in the infrastructure repo to the new values and trigger an build of that environment.

### Creating and managing a Review Environment

Due to multiple developers wanting to test changes to their code on the platform at the same time, whilst users are also testing new features and the like, the fixed environments can become quite congested, to help resolve that, we have the ability to deploy review environments which will start fully functioning environments for users to test in which are standalone from the rest of the system.

From the landing page, if you then click through to the review environments you'll be greeted with the following screen.

<figure><img src="../.gitbook/assets/Screenshot 2023-01-06 143916.png" alt=""><figcaption><p>Review Environment Screen</p></figcaption></figure>

At the top of the screen it will display which review environments are currently deployed, on the bottom half it will show which review environments are configured but not deployed currently.

To launch a new review environment click on the "Deploy new review environment" link at the top of the page. From here you'll then see this:

<figure><img src="../.gitbook/assets/Screenshot 2023-01-06 143931.png" alt=""><figcaption><p>Deploy Review Environment</p></figcaption></figure>

Put your environment name in the top, then you can select the pipeline name which as explained above, allows you to connect to the staging or production pipeline which will trigger when data flows through one of the other. The seed env will allow you to pick where you want the seed data to come from. Finally the image tags are read from github and allow you to pick you API and UI of choice.

Hit the update button and it will deploy allowing you to access your environment via a custom url once it has been deployed.



## Making changes to the codebase

The codebase for the deployement manager lives here [https://gitlab.com/pixlise/deployment-manager](https://gitlab.com/pixlise/deployment-manager)

It is developed on top of the Beego framework [https://github.com/beego/beego](https://github.com/beego/beego) which provides the templating and REST integration.
