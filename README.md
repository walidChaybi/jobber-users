## Users Microservice
* The users microservice is responsible for creating sellers and manging sellers and buyers.
* A buyer can become a seller by creating a profile.
* Sellers can update profile, view sellers dashboard information.
* In this service, events can be `published` to other microservices and `consumed` from other microservices.
* Server side errors from the users microservice is sent to `elasticsearch` and can be viewed on `kibana`.
* Users service uses these tools as the main tools
  * `Your shared library`
  * `NodeJS`
  * `Express`
  * `Typescript`
  * `Rabbitmq`
  * `Elasticsearch`
  * `MongoDB database`
  * `Mongoose`
  * `Json web token`
  * `Faker to create seed data`
* There are other packages that are used.
* You can update the version of `NodeJS` used inside the `Dockerfile` and `Dockerfile.dev`.
* Make sure you already have your own shared library published.
* Copy the `.npmrc` file from your shared library folder and replace `${NPM_TOKEN}` with the actual `personal access token` you created.
* Once you have your `.npmrc` and before you run `npm install` command, replace all occurrences of `@walidchaybi/jobber-shared` with your own shared library.
* After replacing all occurrences of `@walidchaybi/jobber-shared`, you can then run `npm install` command.
* Copy contents of `.env.dev` to `.env` file
  * Create an account on `https://cloudinary.com`
  * Get your `cloud name`, `cloud secret` and `cloud api key` and add to `.env`
  * You can generate a new `GATEWAY_JWT_TOKEN` and `JWT_TOKEN`
    * Just note that whatever you generate, that is what you will need to use in all the microservices that require those variables.
* You can start the service with `npm run dev`.

### Create docker images
* You can create your own docker image from this microservice.
* Create an account on `hub.docker.com` or login if you already have one.
* Make sure to login on your terminal as well.
* Steps to build and push your image to docker hub
  * `docker build -t <your-dockerhub-username>/jobber-users .`
  * `docker tag <your-dockerhub-username>/jobber-users <your-dockerhub-username>/jobber-users:stable`
  * `docker push <your-dockerhub-username>/jobber-users:stable`
