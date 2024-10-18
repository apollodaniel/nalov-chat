# Nalov Chat
Nalov Chat is a fully working chat made in Typescript, using express, postgres, react and bootstrap.

### Youtube Vídeo Showcase
[![Nalov Showcase](https://img.youtube.com/vi/yfa7i3I8zb4/0.jpg)](https://www.youtube.com/watch?v=yfa7i3I8zb4)


> [!WARNING]
> This app is currently using Portuguese as main language. New languages may be implemented soon

> [!WARNING]
> The app is still under development, so if you find a bug please report.

### How to run it
To get started, you'll need `docker` and `docker-compose` installed to get this working. <br>
You can get the installation guide on their [official website](https://docs.docker.com/compose/install/).

#### Clone this repository
```$ git clone --recurse-submodules https://github.com/apollodaniel/nalov-chat```

> [!WARNING]
> To get this working you will need the flag `--recurse-submodules` to clone the
> **project submodules**

#### Execute using docker-compose
```$ docker-compose up``` <br>
Or this one if you don't wanna logs
```$ docker-compose up -d```
<br>
After that, the website will may be available on the following url: <br>
```http://localhost:8085```

> [!WARNING]
> Notice that if you have anothers services running in the following ports, the application may conflict and don't work as expected.
> - 8085 -> Frontend port
> - 8175 -> Backend port
