# Symfony CodeSpaces

This repository contains a Symfony project configured to work with CodeSpaces, making it easy to get started with Symfony development.

## Prerequisites

Before setting up this project, make sure you have the following dependencies installed on your system:

- [PHP](https://www.php.net/) (version 8.2 or higher)
- [Composer](https://getcomposer.org/)
- [Symfony CLI](https://symfony.com/download)

## Getting Started (local)

To set up this Symfony project locally, follow these steps:

1. Clone this repository to your local machine:

```bash
git clone https://github.com/your-username/symfony-codespaces.git
```

2. Navigate to the project's directory:

```bash
cd symfony-codespaces
```

3. Setup a symfony project
```
symfony new my_project --version="6.3.*" --webapp
```

4. Install the project dependencies using Composer:
```bash
composer install
```

5. Start the Symfony development server:
```bash
symfony server:start
```

6. Open your web browser and visit http://localhost:8000 to see the Symfony application running.

## Getting Started (CodeSpaces)
This repository is pre-configured to work with CodeSpaces, allowing you to easily develop in a cloud-based development environment. To set up CodeSpaces for this project, follow these steps:

1. Create a CodeSpace from this GitHub repository by clicking on the green "Code" button and selecting "Open with CodeSpaces."
(you can also fork the repository and commit your project changes there as well)

3. Wait for the CodeSpace to be created and initialized.

4. Once the CodeSpace is ready, you can start developing right away in the cloud.

5. Example setup in the CodeSpaces
```
symfony new my_project --version="6.3.*" --webapp
```
Then `cd new_project` and `symfony server:start` - now you can access you symfony instance and start developing.

### CodeSpaces Profiler
To display the symfony profiler (very useful), in your symfony project, go to `config/packages/framework.yaml` and add the following under `framework`:
```
trusted_proxies: '127.0.0.1'
trusted_headers: ['x-forwarded-for', 'x-forwarded-host', 'x-forwarded-proto', 'x-forwarded-port', 'x-forwarded-prefix']
```

## Useful Commands
Here are some useful commands that you can use while working with this Symfony project:

1. Run PHPUnit tests:
```bash
php bin/phpunit
```

2. Generate the database schema (if using Doctrine):
```bash
php bin/console doctrine:schema:create
```

3. Clear the cache:
```bash
php bin/console cache:clear
```

For more information about Symfony and its commands, refer to the [Symfony documentation](https://symfony.com/doc/current/index.html).

## Contributing
If you'd like to contribute to this project, please follow these guidelines:

1. Fork this repository.

2. Create a new branch for your feature or bug fix:
```bash
git checkout -b my-feature
```

3. Make your changes and commit them with descriptive commit messages.

4. Push your changes to your forked repository:
```bash
git push origin my-feature
```

5. Open a pull request in this repository and provide a detailed description of your changes.

## License
This project is licensed under the MIT License.

You can copy this markdown content and use it as your README.md file for your Symfony CodeSpaces GitHub repository.
