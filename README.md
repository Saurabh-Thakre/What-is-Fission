
<img src="https://www.linkpicture.com/q/Cream-Beige-Simple-Question-Prompt-Instagram-Post_1.png" width="900" height="800">


# Yes, You are, Because I was one too.
Hang in there, I might have a solution for you. Fission is an excellent open-source platform that makes it simple to deploy and administer serverless applications on Kubernetes.

In recent years, serverless computing has grown in popularity as it allows developers from worrying about maintaining the underlying infrastructure so they can concentrate on building code. On Kubernetes, serverless applications may be easily deployed and managed thanks to the robust open-source platform Fission.
Later on, Let's explore the awesome benefits of using Fission for serverless computing. I've even got you some code samples to help you see just how powerful and functional it can be!

Let's explore the benefits of using Fission for serverless computing. One of Fission's most important features I feel is its ability to automatically scale the number of instances of your function to accommodate growing traffic. We can easily compare Fission with a virtual assistant who handles all of your server management needs.

With about everything, first things first, the fundamentals. Fission makes it simple for developers to create, launch, and scale their apps. Because it is built on top of Kubernetes, it is incredibly scalable and stable. I can sum up some of the benefits of Fission with following

**Effortless Use**
Simplicity of usage of fission is one of its main advantages. Fission is relatively simple to use, and programmers may create their functions in several languages, such as Python, Node.js, and Go. Fission also makes it simple to build and manage your functions, and you can even use already-written code as functions without making any changes.

**Speedy performance**
Another fantastic quality, Fission's lightweight and highly efficient design allows for functions to be placed on it to start up in just a few milliseconds. It is a good option for applications that need rapid computation because of its speedy performance.

**Scaling**
Makes scaling your apps simple. You can configure Fission to automatically scale up or down the number of replicas dependent on the workload. Also any required resource to manage all the incoming traffic will be always available for the application to use.

On the other side, if you want to get started with Fission, you need to have a Kubernetes cluster set up. After that, you can install Fission with the Helm chart provided. Creating a new function in Fission is as easy as writing a simple function in your preferred language and deploying it to Fission using the Fission CLI. You can install Fission using the [official Fission documentation](https://fission.io/docs/installation/).

Here's a small code snippet to help you understand how to create a new function in Fission using Python:

```python
def add(a, b):
    return a + b
```

**Run the following command to create a new function named "add" with the Python environment:**

```bash
fission function create --name add --env python --code add.py
```

**Once the function is created, you can deploy it to Fission using the following command:**

```bash
fission route create --function add --url /add
```

What's more, Fission has recently introduced a new feature called "Canary Deployments," which let you deploy multiple versions of a function and gradually route traffic to the new version. This can be extremely useful for testing new code changes without impacting the production environment.

Let's create a new function with a basic "Hello World" example to demonstrate how Canary Deployments work:


```go
package main

import ( 
  "fmt" 
) 

func Handler() (string, error) { 
  return "Hello World!", nil 
}
```

After , we can deploy the function to Fission and create a new version with some changes:

**Deploy initial function**
```bash
$ fission function create --name hello --env go --code hello.go
```

**Create a new version of function with changes**
``` bash
$ fission function update --name hello --env go --code hello.go --version 2
```
Once we have multiple versions of the function, we can use the Fission CLI to create a new canary deployment and gradually route traffic to the new version:

**Create a new canary deployment for version 2**
```bash
$ fission route create --function hello --version 2 --canary=true --weight=10
```
**Update the canary deployment to gradually increase traffic to version 2**
```bash
$ fission route update --function hello --version 2 --canary=true --weight=50
```

Now, we've created a new canary deployment for version 2 of our function and set the initial traffic weight to 10%. We can then gradually increase the traffic weight to version 2 over time by updating the canary deployment. This allows us to test our changes in a controlled manner and ensure that everything is working as expected before fully deploying the new version.

And if we were to compare Fission with other Serverless Platforms for a better understanding of similar work. AWS Lambda, Azure Functions, and Google Cloud Functions are three of the most popular serverless platforms.
AWS Lambda is a fully managed service that provides automatic scaling and support for multiple languages. Azure Functions and Google Cloud Functions offer similar features, with support for multiple languages and automatic scaling.

When you put more thoughts on it, one of the advantages of Fission over these platforms is its integration with Kubernetes. Fission makes it easy to integrate with other Kubernetes resources, such as ConfigMaps, Secrets, and Services, which provides more flexibility in building and deploying applications.

![OpenSource K-native serverless framework](https://d33wubrfki0l68.cloudfront.net/964dac0d5d27fec1d6b6d1a723842f4d14c1ead3/78fef/images/fission-illustration.svg)

An example of a use case for Canary Deployments is updating a function that is essential to the operation of the application. We can make sure that any potential defects or problems are discovered early on and don't have an impact on the program as a whole by progressively redirecting traffic to the new version.

When we talk about some of the real-world use case, Fission has its roots in the Healthcare Sector. To provide patients with appropriate care, the healthcare sector deals with a vast volume of patient data that must be processed in real-time. It can be used to process patient data in real time and automatically launch particular functions to carry out specific actions based on the data.

For instance, a healthcare provider could want to keep track of a patient's vital signs and notify a doctor automatically if any of them fall outside of the typical range. Fission enables the healthcare provider to create functions to manage these events and automatically scale these activities in response to incoming traffic, enabling effective and efficient data processing.
United States Veterans Affairs is a sizable organization that uses fission.

A sizable organization called the Veterans Affairs (VA) of the United States employs fission for medical purposes. Utilizing Fission, the VA has created a serverless architecture that processes patient data as it comes in and calls upon particular functions to take specified actions in response to the data.
With the use of this architecture, the VA can provide its patients with healthcare services that are more effective and efficient, thereby improving patient outcomes. Fission is a great option for real-time applications like those in the healthcare sector since it can handle event-driven workflows and automatically grow functionalities based on demand.

## Conclusion
Because of its features, Fission is a useful tool for businesses in the healthcare sector and other sectors that require real-time data processing. Data processing is efficient and effective thanks to its capacity to manage event-driven processes and automatically scale operations in response to demand.

