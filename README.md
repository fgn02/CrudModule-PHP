# Laravel CRUD Module

This repository contains a simple CRUD module built using the Laravel framework. The module allows users to create, read, update, and delete products. The frontend is enhanced with Vue.js for a dynamic user interface.

## Features
- Create, Read, Update, Delete (CRUD) functionality for products.
- File upload support for product images.
- Integration with Vue.js for the frontend (optional).
- Validation and error handling.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/CrudModule-PHP.git
    ```

2. Navigate into the project directory:
    ```bash
    cd CrudModule-PHP
    ```

3. Install PHP dependencies:
    ```bash
    composer install
    ```

4. Install Node.js dependencies:
    ```bash
    npm install
    ```

5. Copy the `.env.example` file to `.env` and modify the environment variables as needed:
    ```bash
    cp .env.example .env
    ```

6. Generate an application key:
    ```bash
    php artisan key:generate
    ```

7. Set up the database:
    - Create a database and update the `.env` file with the database credentials.
    - Run the migrations:
      ```bash
      php artisan migrate
      ```

8. Serve the application:
    ```bash
    php artisan serve
    ```

9. Compile the frontend assets:
    ```bash
    npm run dev
    ```

## Usage
- Access the application via the URL provided by the `php artisan serve` command (default: `http://localhost:8000`).
- Navigate to `/products` to view the CRUD module.

## Project Structure
- **app/**: Contains the core application code (models, controllers, etc.).
- **resources/views/**: Blade templates for rendering the frontend.
- **resources/js/components/**: Vue.js components for dynamic UI.
- **routes/web.php**: Routes for handling CRUD operations.
- **public/uploads/products/**: Directory for uploaded product images.

## Contributing
If you wish to contribute, please fork the repository and create a pull request.

## License
This project is open-source and available under the [MIT License](LICENSE).

