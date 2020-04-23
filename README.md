# uncertain (In Progress)
A personal tool used to track CBT and ERP therapy.

### To setup:

##### Setup Mongo and Mongo Express
- Create a network for your containers:
  - docker network create test-network
- Create a mongo database (https://hub.docker.com/_/mongo) instance on docker using the following command: 
  - docker create --name mongo-test --network test-network -p 27017:27017 mongo
- Create a mongo-express (https://hub.docker.com/_/mongo-express) instance on docker using the following command:
  - docker create -e ME_CONFIG_MONGODB_SERVER=mongo-test  --name mongo-express-test --network test-network -p 8081:8081 mongo-express

You can verify that the database is running by navigating to localhost:27017. If it is running, it will display the text: It looks like you are trying to access MongoDB over HTTP on the native driver port.

You can access the mongo-express interface by navigating to localhost:8081. Using this tool you should be able to edit/update your databases.

##### Node.js and Loopback 4
https://loopback.io/doc/en/lb4/Getting-started.html

Using loopback to create a rest api.
- Create a lb4 app.
- Use "lb4 datasource" to create a new datasource to connect to our mongo database.
- Use "lb4 repository" to setup a collection in the database.
- Use "lb4 model" to create the object definition.
- Use "lb4 controller" to create a new controller.
- Run "npm start" and navigate to localhost:3000/explorer to explore and test apis.
