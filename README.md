# Image understanding application
It's the take-home work of Recursive application.

## Goal
Our client asked us to create an image understanding tool for their internal use. Here are the features the tool should have from the client perspective:

* The user will upload a photo
* The tool will identify all objects in the photo (e.g. the photo contains 1 car, 1 cat and two birds)
* For each object in the photo, the tool will find similar images in a database of images compiled by the client
* The tool will display to the user the found objects, similar images for each object and associated metadata

## Development

### Language
* [TypeScript](https://www.typescriptlang.org/) - We choose TypeScript because it makes JavaScript to a type-safe language. 
It would be great in refactoring and catching error before runtime when the project growing up.
* [Rust](https://www.rust-lang.org/) - Since this project is about image processing, and it's a heavy cpu loading function which can be very slow in JavaScript, so we choose Rust for our second language.
Rust can be binding to Node.js via [Neon](https://neon-bindings.com/), and can also be compiled to WASM and work in browser to resolve performance issue in both side.
Also, it's useful to parse a large dataset quickly.

### Global dependencies
You need to install following tools to develop this project.
* [Docker](https://www.docker.com/) - Docker provides an easy way to build and run applications in same environment on different devices. 
Our services are all dockerlized, so you need Docker Desktop to run them. **Remember turn on the Kubernetes options in the setting after you install**
* [NVM](https://github.com/nvm-sh/nvm) - NVM is a version manager for Node.js. We suggest using that rather than install Node.js directly.
* [Helm](https://helm.sh/) - The package manager for Kubernetes.
* [Skaffold](https://skaffold.dev/) - Build/deploy tool for local Kubernetes development.

### Cloud service
Since all our service is in docker, we can deploy them to any cloud services, depends on their pricing and service. 
Currently, we prefer GCP or AWS since they are stable and have more support about docker / k8s services. 
We can also deploy our heavy-loading functions to serverless services like GCP Cloud Function or AWS Lambda, depends on the client's budget and performance requirement.

### CI / CD
We have CI/CD via GitHub actions. The application would be deployed to cloud service when the PR merged into `main` branch. 

## Technologies

### Front-end
We use following libraries / frameworks to build our front-end interface.
* [React](https://reactjs.org/) - A popular JavaScript library for building user interfaces.
* [MobX](https://mobx.js.org/README.html) - A simple ans scalable JavaScript state management.
* [TypeStyle](https://typestyle.github.io/#/) - A simple and type safe CSS tool.
We choose this rather than `emotion`, `styled-component` or `jss` because it's more simple and fast.
And the most important point is it makes css type-safe.

### Back-end
We use following libraries / frameworks to build our back-end application.
* [Nest](https://nestjs.com/) - A JavaScript server application framework. 
We choose Nest rather than Express or Fastify because it has more strict struct, and it's more convenient when the project growing up.
We don't use GraphQL in this project because it has very limited endpoints and only a few types of return format, so we can't get benefit from GraphQL.

## Architecture

### Plan A

### Plan B

## Testing & QA

### Unit test

### Functional test

### E2E test

## Author
* [Eddie Hsu](https://github.com/apolkingg8) - apolkingg8@gmail.com

Feel free to contact me if you have any questions. Thank you :) 

