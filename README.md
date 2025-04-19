# Hello Vue Developer (hello-vue-developer)

## Overview
A Vue application illustrating core concepts like components, props, and events within a domain-driven design.

**Author**: Web Application Development Team

## Purpose

This project showcases:
- Component-based architecture with the Options API.
- Event-driven communication (e.g., registration events).
- Reactive state management.
- A Greetings bounded context with a clear model and components.

## Features

- **Register**: Developers provide first and last names to register as Vue developers.
- **Greet**: Welcomes the last registered developer with their full name (appears only after registration).
- **Track**: Counts valid registrations for stakeholders (ignores invalid inputs).
- **Defer**: Allows developers to skip registration and try again later.
- **Validation**: Rejects empty or spaces-only names with feedback.

## User Stories
Detailed requirements for the app’s functionality, including registration, greeting, tracking, and deferral, are described in [docs/user-stories.md](docs/user-stories.md).

## Class Diagram
A PlantUML diagram illustrating the app’s structure, including the Developer entity and Vue components in the Greetings bounded context, is available in [docs/class-diagram.puml](docs/class-diagram.puml).
Following you can find a preview of the diagram:
![class-diagram](https://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/upc-pre-202510-1asi0730-sandbox/hello-vue-developer/refs/heads/master/docs/class-diagram.puml?token=GHSAT0AAAAAAC7JG2V4KWN6Y6QGC6SFZTTKZ72LIEA)


## Setup

### Prerequisites
- Node.js (v16 or higher)
- npm (v8 or higher)

### Installation
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd hello-vue-developer
    ```
2. Install dependencies:
    ```bash
    npm install
    ```
3. Start the development server:
    ```bash
    npm run dev
    ```
4. Open the app in your browser (typically [http://localhost:5173](http://localhost:5173)).