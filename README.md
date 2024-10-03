# Deployment of AI Assignment 2

In this project, we deployed a Machine Learning (ML) model using Docker. The entire deployment process involved creating a Docker container, training the model with data, and testing the application using localhost. Below is a step-by-step overview of the process:

## Steps Overview

1. **Instance Creation**:
   - We began by creating a cloud instance (e.g., on AWS, Google Cloud, or a local VM) where we would set up the Docker environment.

2. **Docker Installation**:
   - Docker was installed on the instance to enable containerization. This involved updating the package manager and installing the Docker engine.

3. **Docker Repository Setup**:
   - We created a project directory that would serve as our Docker repository for the ML model application.

4. **Dockerfile Creation**:
   - A `Dockerfile` was created in the project directory, where we wrote the necessary code for the ML model. This included:
     - Importing libraries such as Flask, scikit-learn, and others.
     - Loading the trained model and defining the prediction logic.

5. **Model Training**:
   - We implemented a script (`train_model.py`) to train the model using the Iris dataset. The trained model was then saved as a `.pkl` file.

6. **Requirements File**:
   - A `requirements.txt` file was created to list all the necessary libraries for model training and application execution. This file is used by Docker to install dependencies when building the container.

7. **Flask Integration**:
   - The ML model was integrated with a Flask application (`app.py`). This app handles incoming requests and provides predictions based on input features.

8. **Project Repository Update**:
   - All code files, including the `Dockerfile`, `train_model.py`, `app.py`, `model.pkl`, and `requirements.txt`, were added to the project repository to ensure version control and collaboration.

9. **Docker Container Building**:
   - The Docker container was built using the following command:
     ```bash
     sudo docker build -t ml-app .
     ```
   - This command creates an image named `ml-app`, containing all the necessary code and dependencies.

10. **Running the Docker Container**:
    - We ran the Docker container with the command:
      ```bash
      sudo docker run -p 4000:80 ml-app
      ```
    - This mapped port 80 of the container to port 4000 of the host machine, allowing access to the Flask application.

11. **Testing the Application**:
    - After the container was running, we tested the prediction functionality by sending a POST request to the `/predict` endpoint using a tool like `curl` or Postman. The response returned the predicted class for the input features provided.

## Conclusion

This project demonstrates the effective use of Docker for deploying a Machine Learning model within a Flask application. The containerization ensures consistent execution across various environments, simplifying the deployment process and making the application easily accessible for predictions. 

By following these steps, we have successfully built, trained, and deployed a Machine Learning model, showcasing our understanding of modern ML application development practices.
