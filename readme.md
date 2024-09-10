# HubSpot Practicum Exercise for Developers

## Overview

This repository contains the practicum exercise designed to showcase the integration of custom HubSpot modules and templates using HubSpot’s local development environment. The goal of the exercise is to demonstrate the process of creating, managing, and rendering custom HubSpot modules with a focus on simplicity and flexibility.

## Contents

### 1. Custom Team Member Module
The custom Team Member module allows for the dynamic addition of team members with customizable attributes, such as name, role, image, and description. The module supports multiple entries, making it easy to scale the list of team members.

- **fields.json**: Defines the structure for the module’s inputs, including the name, role, image, and description for each team member. This file is written to avoid the inclusion of 'id' fields for simplicity.
  
- **Module Structure**:
  ```json
  [
    {
      "name": "team_members",
      "label": "Team Members",
      "type": "group",
      "repeatable": true,
      "children": [
        {
          "name": "member_name",
          "label": "Name",
          "type": "text",
          "default": "Gouda"
        },
        {
          "name": "role",
          "label": "Role",
          "type": "text",
          "default": "Cheese Boss"
        },
        {
          "name": "image",
          "label": "Image",
          "type": "image",
          "default": {
            "src": "../../images/blue_cheese.jpeg",
            "alt": "Team member"
          }
        },
        {
          "name": "description",
          "label": "Description",
          "type": "text",
          "default": "A brief description about the team member."
        }
      ]
    }
  ]
  ```

### 2. Hero Module
The Hero module is designed to display a prominent banner section with an image and content. It offers a simple and flexible structure to incorporate into various page templates.

- **hero.html**: Contains the HTML structure for rendering the hero section on a HubSpot page.
  ```html
  <div class="hero">
    <img class="hero__image" src="{{ module.image.src }}" alt="{{ module.image.alt }}" />
    <article class="hero__content">{{ module.content }}</article>
  </div>
  ```

### 3. Simplified Context Approach
For this project, a simplified approach to using context in HubSpot templates has been implemented. The modules use straightforward HTML and HubL templating without overcomplicating the context-handling process.

## How to Use

1. Clone this repository to your local environment.
2. Set up your HubSpot local development environment if you haven't already.
3. Place the module files (`fields.json` and HTML templates) in the appropriate module directory.
4. Run `hs watch` to sync changes with your HubSpot account and see the modules in action.

## Prerequisites

- HubSpot developer account with access to the CMS.
- HubSpot CLI installed and configured.
- Basic knowledge of HTML, CSS, and HubSpot modules.

## Notes

This repository reflects a hands-on practicum focusing on efficient HubSpot module development. It is intentionally simplified for educational purposes and can be adapted for more complex use cases.
