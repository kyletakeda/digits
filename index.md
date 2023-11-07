![](https://github.com/kyletakeda/digits/blob/main/doc/LandingPage.png)

Digits is an application that allows users to:
  * Register an account.
  * Create and manage a set of contacts.
  * Add a set of timestamped notes regarding their interactions with each contact.

## Installation

First, [install Meteor](https://www.meteor.com/install).

Second, go to [https://github.com/ics-software-engineering/meteor-application-template-react](https://github.com/ics-software-engineering/meteor-application-template-react), and click the "Use this template" button. Complete the dialog box to create a new repository that you own that is initialized with this template's files.

Third, go to your newly created repository, and click the "Clone or download" button to download your new GitHub repo to your local file system.  Using [GitHub Desktop](https://desktop.github.com/) is a great choice if you use MacOS or Windows.

Fourth, cd into the app/ directory of your local copy of the repo, and install third party libraries with:

```
$ meteor npm install
```

## Running the system

Once the libraries are installed, you can run the application by invoking the "start" script in the [package.json file](https://github.com/ics-software-engineering/meteor-application-template-react/blob/master/app/package.json):

```
$ meteor npm run start
```

The first time you run the app, it will create some default users and data. Here is the output:

```
 meteor npm run start 

> meteor-application-template-react@ start /Users/carletonmoore/GitHub/ICS314/meteor-application-template-react/app
> meteor --no-release-check --exclude-archs web.browser.legacy,web.cordova --settings ../config/settings.development.json

[[[[[ ~/GitHub/ICS314/meteor-application-template-react/app ]]]]]

=> Started proxy.                             
=> Started HMR server.                        
=> Started MongoDB.                           
I20220529-12:09:18.384(-10)? Creating the default user(s)
I20220529-12:09:18.389(-10)?   Creating user admin@foo.com.
I20220529-12:09:18.453(-10)?   Creating user john@foo.com.
I20220529-12:09:18.515(-10)? Creating default data.
I20220529-12:09:18.515(-10)?   Adding: Johnson (john@foo.com)
I20220529-12:09:18.599(-10)?   Adding: Casanova (john@foo.com)
I20220529-12:09:18.600(-10)?   Adding: Binsted (admin@foo.com)
=> Started your app.

=> App running at: http://localhost:3000/
```

Periodically, you might see `Error starting Mongo (2 tries left): Cannot run replSetReconfig because the node is currently updating its configuration` after the `=> Started HMR server.`. It doesn't seem to be a problem since the MongoDB does start.

### Viewing the running app

If all goes well, the template application will appear at [http://localhost:3000](http://localhost:3000).  You can login using the credentials in [settings.development.json](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/config/settings.development.json), or else register a new account.

### ESLint

You can verify that the code obeys our coding standards by running ESLint over the code in the imports/ directory with:

```
meteor npm run lint
```

## User Interface Walkthrough

The following sections describe the major features of Digits:

#### Landing page

When you first bring up the application, you will see the landing page that provides a brief introduction to the capabilities of Digits:

![](https://github.com/kyletakeda/digits/blob/main/doc/LandingPage.png)

#### Login page

Clicking on the Login link, then on the Sign In menu item displays this page:

![](https://github.com/kyletakeda/digits/blob/main/doc/SignIn.png)

#### Register page

Alternatively, clicking on the Login link, then on the Sign Up menu item displays this page:

![](https://github.com/kyletakeda/digits/blob/main/doc/Register.png)


#### User home page

After successfully logging in, the system takes you to your home page. It is just like the landing page, but the NavBar contains links to list contact and add new contacts:

![](https://github.com/kyletakeda/digits/blob/main/doc/UserHomePage.png)

#### Add Contact page

After logging in, here is the page that allows you to add new contacts:

![](https://github.com/kyletakeda/digits/blob/main/doc/AddContact.png)

#### List Contacts page

Clicking on the List Contacts link brings up a page that lists all of the contacts associated with the logged in user:

![](https://github.com/kyletakeda/digits/blob/main/doc/ListContacts.png)

This page also allows the user to add timestamped “notes” detailing interactions they’ve had with the Contact. For example:

![](https://github.com/kyletakeda/digits/blob/main/doc/ContactNotes.png)

#### Edit Stuff page

From the List Contacts page, the user can click the “Edit” link associated with any Contact to bring up a page that allows that Contact information to be edited:

![](https://github.com/kyletakeda/digits/blob/main/doc/EditContacts.png)

#### Admin page

It is possible to designate one or more users as “Admins” through the settings file. When a user has the Admin role, they get access to a special NavBar link that retrieves a page listing all Contacts associated with all users:

![](https://github.com/kyletakeda/digits/blob/main/doc/Admin.png)
