<h1>MEARN Stack Application Deployment Workflow</h1>

<h2>Method 1: Docker Hub Deployment</h2>

<p><strong>Workflow Description:</strong></p>

<ol>
  <li><strong>Build Docker Images:</strong> The workflow builds Docker images for the frontend, backend, and appew components of the MEARN stack application.</li>
   
  <li><strong>Login to Docker Hub:</strong> It securely logs in to Docker Hub using provided credentials.</li>
   
  <li><strong>Push Docker Images:</strong> After logging in, the workflow pushes the built Docker images for the frontend, backend, and appew components to Docker Hub, making them accessible for deployment.</li>

  <li><strong>Deploy to Server:</strong> The Docker images pushed to Docker Hub are then deployed to the server using SSH. Existing Docker containers for the application components are stopped and removed, and the latest Docker images are pulled from Docker Hub. New Docker containers are then run on the server to deploy the MEARN stack application.</li>

  <li><strong>Cleanup:</strong> At the end of the workflow, temporary resources are cleaned up and the workflow stops.</li>
</ol>

<h2>Method 2: Direct Server Deployment</h2>

<p><strong>Workflow Description:</strong></p>

<ol>
  <li><strong>Build Docker Images:</strong> Similarly, this workflow builds Docker images for the frontend, backend, and appew components.</li>

  <li><strong>Save Docker Images as Tar Archives:</strong> Instead of pushing to Docker Hub, the workflow saves the Docker images as tar archives.</li>

  <li><strong>Upload to Server:</strong> Using SSH, the tar archives containing the Docker images are securely uploaded to the server.</li>

  <li><strong>Deploy from Server:</strong> On the server side, the uploaded Docker images are loaded and deployed directly, eliminating the need for Docker Hub.</li>

  <li><strong>Cleanup:</strong> Temporary resources are cleaned up and the workflow stops.</li>
</ol>

<p>Both methods offer flexibility in deployment options. Method 1 leverages Docker Hub for image storage and distribution, while Method 2 provides a direct route for users who prefer not to use Docker Hub or who face constraints such as limited Docker Hub storage or privacy concerns.</p>

