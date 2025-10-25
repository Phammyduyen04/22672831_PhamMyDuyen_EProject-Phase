
# EProject Phase 1

## Project Overview

EProject Phase 1 is a full-stack application involving multiple services such as authentication, order management, and product handling, all integrated using an API Gateway. The project uses Docker for containerization and Node.js for backend services.

## Project Structure

The project is structured into several key components:

- **api-gateway**: Manages API requests and routes them to the appropriate services.
- **auth**: Handles user authentication and authorization.
- **order**: Manages orders and related functionality.
- **product**: Manages products, including their creation, updates, and retrieval.

Additionally, the project includes configuration files for Docker (`docker-compose.yml`), environment settings (`.env`), and version control setup (`.git`, `.gitignore`).

EProject-Phase/
├── .github/workflows/
│   └── test.yml                 # CI/CD pipeline
├── auth/
│   ├── src/
│   │   ├── controllers/         # Auth business logic
│   │   ├── routes/             # API endpoints
│   │   ├── services/           # Core auth services
│   │   └── test/               # Auth tests
│   ├── Dockerfile
│   └── package.json
├── product/
│   ├── src/
│   │   ├── controllers/        # Product business logic
│   │   ├── routes/            # API endpoints
│   │   ├── services/          # Core product services
│   │   └── test/              # Product tests
│   ├── Dockerfile
│   └── package.json
├── order/                     # Future service
├── api-gateway/              # Future service
├── docker-compose.yml        # Local development
└── README.md

## Testing with Postman

Once the services are up and running, you can test the API endpoints using Postman. Below are the details of the key endpoints for each service:

### 1. **Auth Service**

- **Login**
  - **Method**: `POST`
  - **URL**: `http://localhost:3003/auth/login`
  - **Body** (JSON):
    ```json
    {
      "username": "username",
      "password": "your_password"
    }
    ```
  - **Response**:
    ```json
    {
      "token": "your_jwt_token"
    }
    ```

- **Register**
  - **Method**: `POST`
  - **URL**: `http://localhost:3003/auth/register`
  - **Body** (JSON):
    ```json
    {
      "name": "username",
      "password": "password"
    }
    ```
  - **Response**:
    ```json
    {
      "username": "username",
      "password": "password_encryption",
      "_id": "id"      
      
    }
    ```

### 2. **Product Service**

- **Get All Products**
  - **Method**: `POST`
  - **URL**: `http://localhost:3003/products`
  - **Response**:
    ```json
    {
    "name" : "name_product",
    "description": "description",
    "price": 000
    }
    ```

- **Create Product**
  - **Method**: `POST`
  - **URL**: `http://localhost:3003/product/buy`
  - **Body** (JSON):
    ```json
    [
    {
        "_id": "id_product",
        "quantity": 000
    }
    ]
    ```
  - **Response**:
    ```json
    {
    "_id": "",
    "status": "",
    "products": [
        {
            "_id": "",
            "name": "",
            "quantity": ,
            "price": 
        }
    ],
    "username": "",
    "orderId": "",
    "totalPrice": ,
    "createdAt": ""
    }
    ```

## Folder Descriptions

- **api-gateway**: Responsible for managing API requests and routing them to the appropriate services.
- **auth**: Handles user authentication, registration, and token management.
- **order**: Manages the lifecycle of orders.
- **product**: Responsible for managing products in the system.

## Contributing

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Commit your changes and push them.
4. Submit a pull request.

## License

This project is licensed under the MIT License.
