# JWT Authentication in ASP.NET Core with Weather Forecast API
This project demonstrates how to implement JWT (JSON Web Token) authentication in an ASP.NET Core Web API. It includes a simple WeatherForecastController that is secured using JWT, and an AuthController to handle user login and token generation.

# Features
JWT Authentication: Secure API endpoints using JWT.

Weather Forecast API: A sample API endpoint that returns weather data.

Login Endpoint: Authenticate users and issue JWTs.

Role-Based Authorization: Example of how to include roles in JWTs (optional).

# Technologies Used
ASP.NET Core: For building the Web API.

JWT: For secure authentication and authorization.

Swagger: For API documentation (optional).

# Setup Instructions

1. Clone the Repository
bash
Copy
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/vkeychaudhari/JwtApiExample.git)
cd your-repo-name

2. Configure JWT Settings
Update the appsettings.json file with your JWT configuration:

json
Copy
{
  "Jwt": {
    "Key": "YourSecretKeyMustBeAtLeast128BitsLong",
    "Issuer": "YourIssuer",
    "Audience": "YourAudience"
  }
}

3. Run the Application
Open the project in Visual Studio or Visual Studio Code.

Build and run the project:

bash
Copy
dotnet run
The API will be available at https://localhost:5001.

4. Test the API
Login to Get a JWT
Send a POST request to /api/auth/login with the following body:

json
Copy
{
  "username": "user",
  "password": "password"
}
You will receive a JWT in the response:

json
Copy
{
  "token": "your-jwt-token"
}

Access the Weather Forecast Endpoint
Include the JWT in the Authorization header:
Authorization: Bearer <YourJWT>
Send a GET request to /WeatherForecast.

# Project Structure
Controllers:

AuthController: Handles user login and JWT generation.

WeatherForecastController: A sample API endpoint secured with JWT.

# Models:

LoginRequest: Represents the login request body.

# Configuration:

appsettings.json: Contains JWT settings.

