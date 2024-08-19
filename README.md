# PPMS Homepage Project

## Overview

This project is a front-end web application that demonstrates my skills in CSS, user experience design, and modern web development techniques. The project consists of a homepage for the PPMS (Project and Portfolio Management System) with a dark mode feature. The goal was to create a user-friendly and accessible interface adhering to WCAG accessibility standards.

## Features

- **Responsive Design**: The layout adapts to various screen sizes, ensuring usability across different devices.
- **Dark Mode**: A dark mode feature that allows users to toggle between light and dark themes.
- **Header**: Contains navigation tabs (Home, Training, Projects, Orders, Documents, Incidents, Profile, Logout).
- **Body**: A customizable layout design where users could theoretically add or remove sections.
- **Section Components**: Reusable components representing different types of sections (e.g., MyUserProfile, MyDocuments, MyTrainingSessions, etc.).
- **Popup Component**: A design for a popup that could allow users to add or remove sections.
- **Footer**: Includes the website logo, application version, and a "Contact Us" link.

## Project Structure

```plaintext
PPMS-Homepage-Project/
├── public/
│   ├── index.html
├── src/
│   ├── assets/
│   │   ├── logo_name.png
│   │   ├── logo.png
│   │   ├── moon.svg
│   │   ├── sun.svg
│   ├── components/
│   │   ├── Header.vue
│   │   ├── Body.vue
│   │   ├── Popup.vue
│   │   ├── Footer.vue
│   ├── App.vue
│   ├── main.js
├── README.md
```
## Key Files
- **App.vue** : The main application file that orchestrates the components.
- **Header.vue**: Contains the header section with navigation tabs.
- **Body.vue** Manages the main content area with customizable sections.
- **Popup.vue** Represents the popup design for adding/removing sections.
- **Footer.vue** The footer with the logo, version, and contact link.

## Installation and Setup
Prerequisites
Make sure you have the following installed:

Node.js (v14 or later)
Vue CLI
Steps to Run the Project
