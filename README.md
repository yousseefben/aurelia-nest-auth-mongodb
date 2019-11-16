# Aurelia / NestJS / MongoDB / GraphQL and OAuth
Full stack boilerplate with Aurelia, NestJS, GraphQL, MongoDB and OAuth login.

## Client TypeScript Webpack

### Client installation
Start by cloning the repo and then install it (with `npm` or [yarn](https://yarnpkg.com/))
```bash
cd aurelia-nest-auth-mongodb/client
npm install # or: yarn install
```

### VScode Workspaces
If you use VSCode (Visual Studio Code) as your main editor, you can load the VSCode workspace. Once the workspace is loaded, you will then have access to multiple tasks (defined in `client/tasks.json`) which makes it easy to execute the code without even typing any command in the shell (you still have to make sure to `npm install` in both `client` and `server` folders).


### Running the App
The simplest way of running the App is to use the VSCode tasks there were created **Aurelia (client)** and **NestJS Dev (server)** (or _NestJS Debug (server)_ if you wish to debug your code with NestJS)

The second way would be to type the shell command `yarn start` in both `client` and `server` folders.
```bash
npm start # or: yarn start
```

### Backend Server installation (NestJS)
To install and start the backend server (NestJS), go into the server folder and run `npm start` (make sure you ran the `npm install` first)
```bash
cd aurelia-nest-auth-mongodb/server
npm install # or: yarn install
npm start # or: yarn start
```

### OAuth
For the OAuth to work, we use Passport and you will need to rename a file and configure your keys to get going. Here are the steps
1. rename [server/src/auth/auth-config.development.template.ts](https://github.com/ghiscoding/aurelia-nest-auth-mongodb/blob/master/server/src/auth/auth-config.development.template.ts) to `server/src/auth/auth-config.development.ts`
2. open the file and change all necessary `clientID` and `clientSecret` properties then save the file.
3. run the project

### Web UI
If everything goes well, your application should now run locally on port `9000`. So, in your browser just go to the URL [http://localhost:9000](http://localhost:9000).

## License
MIT

## Getting started

Before you start, make sure you have a recent version of [NodeJS](http://nodejs.org/) environment *>=10.0* with NPM 6 or Yarn.

From the project folder, execute the following commands:

```shell
npm install # or: yarn install
```

This will install all required dependencies, including a local version of Webpack that is going to
build and bundle the app. There is no need to install Webpack globally.

To run the app execute the following command:

```shell
npm start # or: yarn start
```

### GraphQL
After installing and starting the server you should be able to see your GraphQL playground on http://localhost:3000/graphql.
You can see if it works by typing the following in the query window 
```ts
{
  hello 
}
```
Also note that most of the GraphQL query are protected and cannot be run directly in the GraphQL playground unless you use the JWT token.


### TODO
- [x] Exclude authConfig(s) from Git
- [x] Refine Auth Configuration for both Backend/Frontend
- [x] Update to latest Aurelia/CLI
- [x] Save user to MongoDB
- [x] User Login
	- [x] Use JWT with Passport and bcrypt for the password encryption while saving in DB
	- [x] Validate username/password in UI
	- [x] Add form validation
	- [ ] Add possibility to update Password in User Profile when using username/password
- [x] User Signup Frontend
	- [x] Encrypt password instead of plain text when sending it over the line
	- [x] Redirect to Profile after doing a sign up
	- [x] Add form validation
	- [x] Display warning when trying to signup duplicate email
- [ ] CRUD on User Profile ("Me" controller)
- [ ] Link/Unlink multiple accounts to a single account
    - [x] Ability to add multiple accounts to an OAuth account
    - [ ] Cleanup NestJS code to do it in 1 action instead of currently 2.
	- [ ] Link a user to a local user (username/password) with its email 
- [x] GraphQL add the "whoAmI" (me) resolver 
- [ ] Aurelia Auth separated into its own plugin
  - [x] JWT Storage
  - [ ] Create new plugin repo 
- [ ] Windows Live picture must be pulled from Microsoft Graph API
- [x] Add Cats list in frontend under an authorized endpoint
- [ ] Add User Roles (Admin/Regular User)
- [ ] Show User list only to Admin users
- [ ] Show Cats list to everyone in UI and GraphQL
  - [ ] Create new Cat from UI (cat's owner should be current authenticated user)
- [x] Protect MongoDB with username/password
- [x] Add Node/Chrome Debugger
- [x] Add Swagger with Bearer
