# Planning

---

## URL Shortening

### API
[shrtcode API](https://app.shrtco.de/)

### HTTP Request/Response
Create an Axois layer for making HTTP requests and receiving responses and receiving responses.

---

## Local Storage
- Research local storage solution for Vue apps.
- Plan schema for storing created urls into storage.
- Plan retrieving list of shortened urls by user.

---

## Deployment

Setup early deployment of this app to ensure build files are working as intended.
Maybe look into setting up a pipeline using GitHub Actions for automatic update of deployment based on code pushes to main branch.

---

## Components

- Header (Logo, Navbar, Login/Sign Up, Hero/Call to action)
- Form for URL shortening (main tag)
- Advanced statistics cards (section tag)
- Boost links call to action (section tag)
- Footer (Logo, Features list, resources list, Company list, social media logos)

---

## Styling

### Media Queries

- Advanced statistics and footer columns should collapse into one column at smaller screen sizes.
- Navbar links collapse into a hamburger menu at smaller screens.

### Details

The line going between the advanced statistics cards changes from horizontal to vertical when columns collapse into one. Create these elements with pseudo elements.
