## What is CI/CD in DevOps?

### What is CI/CD?

CI/CD is a significant DevOps practice and an Agile philosophy best practice. This training permits improvement groups to oftentimes convey and send applications and speed up the application advancement process. Presenting a CI/CD pipeline into our product improvement lifecycle permits us to proficiently carry out robotization and screen code changes, new highlights, potential bug fixes, from there, the sky is the limit.

CI/CD ordinarily alludes to constant mix and persistent conveyance, however the "Cd" can likewise represent the consistent organization. Consistent conveyance and constant sending both allude to robotizing phases of the CI/CD pipeline, yet ceaseless organization goes above and beyond. The motivation behind consistent conveyance is to make it simple to send new code. The reason for persistent arrangement is to permit groups to be "hands-off" in the process via robotizing the sending stage.


> Cloud-Native CI/CD: A cloud-native CI/CD pipeline permits us to make the most of distributed computing administrations and highlights, like containerization, going serverless, and executing a multi-cloud framework. A cloud-local application is worked to run in the cloud. The cloud-native CI/CD interaction upholds cloud administrations all through the product advancement lifecycle.

### Benefits of CI/CD

**Increased speed:** With an automated CI/CD pipeline, teams can ship changes every hour, day, week, month, etc., and we can optimize each stage of the process. New changes and features can be launched quickly, which allows you to respond to new trends and address any issues that come up.

**Easy maintenance:** When it’s time to perform routine maintenance, you don’t want all of the system to shut down at once. To address this problem, you can create microservices in the architecture of your code so that individual areas of the system are taken down for maintenance instead of the entire system.

**Improved collaboration and visibility:** A CI/CD pipeline allows many people to get involved in the process, which promotes visibility and collaboration across different teams and orgs.

**Real-time feedback**: Shipping regular updates allows you to receive more immediate feedback from users. It also allows you to experiment with different features and fixes, and then hear about their performance shortly after deployment.


**Continuous reliability and continuous testing:** Continuous reliability, or test reliability, improve in a CI/CD pipeline. This is because incremental changes are implemented one at a time, which allows for more precise and accurate tests to be conducted continuously.

**High-quality code:** With CI/CD, your code is tested regularly. This means that you’ll discover bugs sooner and fix them more quickly.

### What is continuous integration?

Continuous integration refers to the build/integration stage of the software release process. It’s a stage where developers **consistently merge their changes into the main repository** of a version control system (like Git). After these changes are merged into the main repository, automated builds and tests are run. Before code changes are committed, you can run unit tests to verify the code before integrating it into the main repository. If you don’t run the tests yourself, the CI service performs automated tests and builds on any new code changes.

### What is continuous delivery?

Continuous delivery expands upon continuous integration. It is a delivery process that allows us to **automatically test and upload code changes to a repository** (like GitHub), and then deploy all code changes to a testing environment or a production environment. With a continuous delivery pipeline, we can further **automate testing** beyond just unit tests and perform UI tests, integration tests, load tests, and more. When we thoroughly test the codebase, we can verify that the application is error-free and ready for deployment. With continuous delivery, the operations team triggers the deployment instead of it happening automatically (this is where continuous deployment comes in).

### CI/CD tools
A good CI/CD tool can help to create a strong CI/CD pipeline. Popular CI/CD tools include:

- **Jenkins: **Jenkins is an open-source, Java-based automation server that supports building, deploying, and automating software development processes.

- **CircleCI:** CircleCI supports software development and publishing. It allows you to automate the entire pipeline, and integrate with services like GitHub, GitHub Enterprise, and Bitbucket to perform builds when code is committed.

- **GitLab:** GitLab provides a suite of tools for managing the software development lifecycle. You can perform builds, run tests, and deploy code. It also allows you to build jobs in a VM, Docker container, or a different server.

### Major cloud providers, such as Microsoft, Amazon, and Google, also offer CI/CD process tools:

- **Azure DevOps:** Azure DevOps provides a variety of CI/CD tools, like Git repo management, testing, reporting, and more. It provides support for Azure, Kubernetes, and VM-based resources.

- **AWS CodePipeline:** AWS CodePipeline is a continuous delivery service that allows you to automate release pipelines. It easily integrates with third-party services like GitHub.

- **Cloud Build from Google Cloud Platform (GCP):** Cloud Build from GCP is a serverless CI/CD platform that allows you to build software across all languages, such as Java and Go, deploy across multiple environments, and access cloud-hosted CI/CD workflows within your own private network.

## Additional Resource
https://spacelift.io/blog/ci-cd-pipeline




