# PHP and NGINX docker

![Image](docs/img/135923857-ee22eb05-a18f-47c9-a582-17271c89c488.png)

## About the project

This project it's just a PHP and NGINX docker optimized and ready to use for (production or development) configured by target on docker-compose file. Why you should use this code base? Because this repo provide a nicely and simple docker environment, you will find just the necessery extensions for production app or development.

## Prerequisites 📋

* Docker
* docker-compose

## Instalation 🔧

The installation of the project is very simple, it consists of two steps a first step is to download the repository using git clone.

```bash
    git clone git@github.com:matheusbloise/docker-multi-stage-php-nginx.git
```

And the second step, to start the project is to execute the following command

```bash
    docker-compose up
```

## Deployment 📦

### Local or dev environments

To use it locally you have to run docker-compose and the project will start in development mode, this mode will be used both for local development and for the development environment.

```bash
    docker-compose up
```

### Production environment

For the production environment, the execution of the project is a bit different from the other environments as you have to run the docker-compose with two files to be able to apply the production configuration.

```bash
    docker-compose -f docker-compose.yml -f docker-compose-cloud.yml up
```

## Contributing 🖇️

Please see [CONTRIBUTING.md](https://gist.github.com/matheusbloise/xxxxxx) for details of our code of conduct, and the process for submitting pull requests to us.

## Wiki 📖

You can find much more on how to use this project in our [Wiki](https://github.com/matheusbloise/docker-multi-stage-php-nginx/wiki)

## Contributors ✒️

You can also see the list of all [contributors](https://github.com/matheusbloise/docker-multi-stage-php-nginx/graphs/contributors) who have participated in this project.

## License 📄

This project is under the License (Your License) - see the file [LICENSE](LICENSE) for details.
