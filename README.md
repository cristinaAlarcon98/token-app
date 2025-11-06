# Token App

![React](https://img.shields.io/badge/Frontend-React-61DAFB?logo=react&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Backend-Spring%20Boot-6DB33F?logo=springboot&logoColor=white)
![REST API](https://img.shields.io/badge/API-REST-blue?logo=api&logoColor=white)

Welcome to my **Token App**.  
This app features only one page divided into two sections.

The first section, located on the left side, generates a 16-digit token based on the digits provided by the user.  
The second section, situated on the right side, verifies the validity of a token by employing the **Luhn algorithm**.

![App Screenshot](https://github.com/cristinaAlarcon98/TokenApp/assets/113309965/7a81eb2b-fba8-46b3-999b-f9efcbdd9863)

## Key Features

- **Token Format:**  
  Each token follows the format `XXXX-XXXX-XXXX-XXXX` and is composed exclusively of digits ranging from `0` to `9`.

- **Custom Digit Selection:**  
  Users can choose which digits can be used for generating tokens.  
  For instance, if a user selects the digits `2, 4, 7, 9, 0`, then the token will be formed using only these digits (e.g., `2249-4472-0279-9420`).

- **Token Generation:**  
  The application features a `GeneratorService` that creates tokens.  
  Users can initiate token generation through the UI, which then sends the selected digits to the service.  
  The service generates a token randomly based on the provided digit choices, and the generated token is displayed on the UI.

- **Token Validation:**  
  Users can validate tokens using the application.  
  This process involves sending the token to the `ValidatorService`, which employs the [Luhn algorithm](https://en.wikipedia.org/wiki/Luhn_algorithm) to ascertain its validity.  
  The validation result is then displayed on the UI.

## Technical Specifications

- **Frontend:** The user interface is developed using React.  
- **Backend Services:**  
  - `GeneratorService` - implemented with Spring Boot  
  - `ValidatorService` - implemented with Spring Boot  
- **Communication:** The Frontend and Backend services communicate via a REST API.

## Repository Structure

```
/frontend/       contains all frontend code
/generator/      contains the GeneratorService code
/validator/      contains the ValidatorService code
start.sh         script to launch the application (Linux/Mac)
/start.bat       script to launch the application (Windows)
```

## Installation

1. **Clone the repository**
   ```
   git clone https://github.com/cristinaAlarcon98/TokenApp.git
   cd TokenApp
   ```

2. **Install frontend dependencies**
   ```
   cd frontend
   npm install
   cd ..
   ```

3. **Build backend services**
   ```
   cd generator
   ./mvnw clean package
   cd ../validator
   ./mvnw clean package
   cd ..
   ```

4. **Run the application**
   ```
   ./start.sh
   ```
   or on Windows:
   ```
   start.bat
   ```

## How to Run

Once executed, the frontend will be accessible at:
```
http://localhost:8080
```

