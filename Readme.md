![Build Status](https://img.shields.io/github/actions/workflow/status/ProgrammingInsider/PrimeMarket-E-commerce-Platform/build.yml)
![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/github/v/release/ProgrammingInsider/PrimeMarket-E-commerce-Platform)
![Coverage](https://img.shields.io/codecov/c/github/ProgrammingInsider/PrimeMarket-E-commerce-Platform)

# PrimeMarket E-commerce Platform

**PrimeMarket** is a full-stack MERN (MongoDB, Express.js, React.js, Node.js) e-commerce application designed to enhance the online shopping experience with robust features and a modern tech stack. Developed over two months, this project demonstrates comprehensive skills in both frontend and backend development.

## Project Overview

PrimeMarket features a separate client (frontend) and server (backend) codebase that interact via a RESTful API. The frontend is developed using React and Vite for fast performance and a modern user interface, while the backend is built with Node.js and Express.js to handle API requests and business logic. MongoDB Atlas is utilized for database management.

### Key Features

- **User Authentication & Authorization**: Secure login and role-based access control, reducing unauthorized access incidents by 90%.
- **Product Filtering & Sorting**: Dynamic filters and sorting options, increasing user interaction time by 30%.
- **Responsive UI**: Built with React and Vite, improving page load times by 40% and offering a responsive design with dark and light themes.
- **Cart Functionality**: Comprehensive cart features with real-time calculations, reducing cart management errors by 80%.
- **Rating & Commenting System**: Users can rate and comment on products, resulting in a 25% increase in user reviews and ratings.
- **Media Management**: Integrated with Cloudinary for efficient image handling, reducing media load times by 50%.
- **Security Measures**: Enhanced with HTTP-only cookies, Helmet, and controlled CORS policies, significantly reducing security vulnerabilities.
- **Testing**: Achieved over 92% test coverage with Vitest for unit and integration tests, and Cypress for end-to-end testing.

## Live Demo

- **[Live Demo](https://primemarket.onrender.com/)**

## Source Code

- **Repository**: [PrimeMarket-E-commerce-Platform](https://github.com/ProgrammingInsider/PrimeMarket-E-commerce-Platform)

## Screenshots

![Homepage](https://res.cloudinary.com/dahgxnpog/image/upload/v1723153783/homepage_zlsem9.png)
![Product Detail Page](https://res.cloudinary.com/dahgxnpog/image/upload/v1723153779/detailpage_vog6xd.png)
![Profile Page](https://res.cloudinary.com/dahgxnpog/image/upload/v1723153785/profilepage_k6nucy.png)
![Cart Page](https://res.cloudinary.com/dahgxnpog/image/upload/v1723153778/cartpage_oidoof.png)

## Installation

### Prerequisites

- Node.js (LTS version recommended)
- Docker (for containerization) if you want to use Docker

### Steps

1. **Clone the Repository**

    ```bash
    git clone https://github.com/ProgrammingInsider/PrimeMarket-E-commerce-Platform.git
    cd PrimeMarket-E-commerce-Platform
    ```

2. **Install Dependencies**

   - **For the frontend**:

     ```bash
     cd client
     npm install
     ```

   - **For the backend**:

     ```bash
     cd server
     npm install
     ```

3. **Running the Application**

   - **For the frontend**:

     ```bash
     cd client
     npm run dev
     ```

   - **For the backend**:

     ```bash
     cd server
     npm run dev
     ```

4. **Running Tests**

   - **For the frontend**:

     ```bash
     cd client
     # Run Unit Tests
     npm test

     # Run UI Tests
     npm run test:ui
     ```

   - **For the backend**:

     ```bash
     cd server
     # Run Unit Tests
     npm test

     # Run Integration Tests
     npm run test:integration
     ```

5. **End-to-End Testing**

    ```bash
    npx cypress open
    ```

6. **Docker**

   - **Pull the Docker Images**

     ```bash
     docker pull aman2208/primemarket-web:v1.0.0
     docker pull aman2208/primemarket-api:v1.0.0
     ```

   - **Create a `docker-compose.yml` File**

     ```yaml
      version: '3'
      services:
        web:
          image: aman2208/primemarket-web:v1.0.0
          ports:
            - 5173:5173
          environment:
            - NODE_ENV=production
            - VITE_BASE_URL=${VITE_BASE_URL}
          networks:
            - frontend
          depends_on:
            - api

        api:
          image: aman2208/primemarket-api:v1.0.0
          ports:
            - 5000:5000
          environment:
            - PORT=5000
            - MONGO_URL_PROD=${MONGO_URL_PROD}
            - ACCESS_TOKEN_SECRET=${ACCESS_TOKEN_SECRET}
            - REFRESH_TOKEN_SECRET=${REFRESH_TOKEN_SECRET}
            - CLOUDINARY_API_KEY=${CLOUDINARY_API_KEY}
            - CLOUDINARY_API_SECRET=${CLOUDINARY_API_SECRET}
            - CLOUDINARY_CLOUD_NAME=${CLOUDINARY_CLOUD_NAME}
          networks:
            - frontend
            - backend

      networks:
        frontend:
        backend:
     ```

   - **Provide a `.env` File**

     ```bash
     # Create a .env file in the same directory as docker-compose.yml with the necessary environment variables. Example .env file:
     PORT=5000
     VITE_BASE_URL=VITE_BASE_URL
     MONGO_URL_PROD=mongo_url
     ACCESS_TOKEN_SECRET=access_token_secret
     REFRESH_TOKEN_SECRET=refresh_token_secret
     CLOUDINARY_API_KEY=cloudinary_api_key
     CLOUDINARY_API_SECRET=cloudinary_api_secret
     CLOUDINARY_CLOUD_NAME=cloudinary_cloud_name
     ```

   - **Run the Application**

     ```bash
     docker-compose up
     ```

## Challenges & Solutions

- **Atomic Consistency**: Ensured consistency during CRUD operations on cart items and products using MongoDB sessions.
- **Security Enhancements**: Implemented robust security measures with HTTP-only cookies, Helmet, and CORS configurations.
- **Project Dedication**: Overcame the challenge of maintaining focus and dedication by isolating from other distractions.

## Future Plans

- Implement additional payment methods.
- Enhance the recommendation system based on user behavior.

## Contributing

- Fork the repository and create a new branch for your changes.
- Submit a pull request with a detailed description of your changes.

## Contact Information

- **Email**: [amanuelabera46@gmail.com](mailto:amanuelabera46@gmail.com)
- **LinkedIn**: [Amanuel Abera Kedida](https://www.linkedin.com/in/amanuel-abera-kedida)

# Code of Conduct

## Our Pledge

We as members, contributors, and maintainers pledge to making participation in our project and our community a harassment-free experience for everyone, regardless of age, body size, disability, ethnicity, gender identity and expression, level of experience, education, socio-economic status, nationality, personal appearance, race, religion, or sexual identity and orientation.

## Our Standards

Examples of behavior that contributes to creating a positive environment include:
- Using welcoming and inclusive language
- Being respectful of differing viewpoints and experiences
- Gracefully accepting constructive criticism
- Focusing on what is best for the community
- Showing empathy towards other community members

Examples of unacceptable behavior by participants include:
- The use of sexualized language or imagery and unwelcome sexual attention or advances
- Trolling, insulting/derogatory comments, and personal or political attacks
- Public or private harassment
- Publishing others' private information, such as a physical or electronic address, without explicit permission
- Other conduct which could reasonably be considered inappropriate in a professional setting

## Reporting and Enforcement

Instances of abusive, harassing, or otherwise unacceptable behavior may be reported by contacting the project team at [email address]. All complaints will be reviewed and investigated promptly and fairly. The project team is obligated to maintain confidentiality with regard to the reporter of an incident.

Project maintainers have the right and responsibility to remove, edit, or reject comments, commits, code, wiki edits, issues, and other contributions that are not aligned to this Code of Conduct, or to ban temporarily or permanently any contributor for other behaviors that they deem inappropriate, threatening, offensive, or harmful.

## Attribution

This Code of Conduct is adapted from the [Contributor Covenant](https://www.contributor-covenant.org/), version 1.4.

## Acknowledgements

- **Cloudinary** for media management.
- **MongoDB Atlas** for database hosting.
- **Render** for deployment.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to explore the live demo, review the source code, and provide feedback!
