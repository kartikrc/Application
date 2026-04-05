# Application
Small projects

## ASP.NET Core Web Application

This is a simple ASP.NET Core web application that responds with "Hello World!" on the root endpoint.

### Prerequisites
- .NET 5.0 SDK or later

### Building the Application
Run the following command to build the application:
```
dotnet build
```

### Running the Application Locally
Run the following command to start the web server:
```
dotnet run
```
The application will be available at `http://localhost:5000` (or the port shown in the console).

### Deployment to Azure App Service

This project includes CI/CD setup using GitHub Actions to automatically deploy to Azure App Service.

#### Setup Steps

1. **Create an Azure App Service**:
   - Go to the Azure Portal.
   - Create a new Web App (App Service).
   - Choose .NET 5.0 as the runtime stack.
   - Note the app name (e.g., `your-app-name`).

2. **Get the Publish Profile**:
   - In the Azure Portal, go to your App Service.
   - Under "Deployment", click "Deployment Center" or "Get publish profile".
   - Download the publish profile XML.

3. **Add Secrets to GitHub**:
   - Go to your GitHub repository.
   - Navigate to Settings > Secrets and variables > Actions.
   - Add a new repository secret named `AZUREAPPSERVICE_PUBLISHPROFILE`.
   - Paste the entire content of the publish profile XML as the value.

4. **Update the Workflow**:
   - Edit `.github/workflows/azure-deploy.yml`.
   - Replace `'your-app-name'` with your actual Azure App Service name.

5. **Push Changes**:
   - Commit and push the changes to the `main` branch.
   - The GitHub Actions workflow will automatically build and deploy the app.

After deployment, your app will be available at `https://your-app-name.azurewebsites.net`.
