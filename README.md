# Try Out Development Containers: JHipster

This is a sample project that lets you try out the **[VS Code Remote - Containers](h
ttps://aka.ms/vscode-remote/containers)** extension in a few easy steps. +

> **Note:** If you're following the quick start, you can jump to the [Things to try](#things-to-try) section.

## Setting up the development container

Follow these steps to open this sample in a container:

1. If this is your first time using a development container, please follow the [gett
   ing started steps](https://aka.ms/vscode-remote/containers/getting-started).

2. If you're not yet in a development container:
   - Clone this repository.
   - Press <kbd>F1</kbd> and select the **Remote-Containers: Open Folder in Container...** command.
   - Select the cloned copy of this folder, wait for the container to start, and try things out!

## Things to try

Once you have this sample opened in a container, you'll be able to work with it like
you would locally.

1. **Generate a JHipster app:**
   - Run `jhipster` and answer questions
2. Start the app
   - Run `./mvnw` or `./gradlew` in a terminal
   - See your app on [localhost:8080](http://localhost:8080)

- Run `./mvnw` in a terminal

3. Start the front-end hot-reload server
   - Run `npm start` in an other terminal
   - See your app on [localhost:9000](http://localhost:9000)
4. Start the front-end hot-reload server
   - Run `npm start` in an other terminal
   - See your app on [localhost:9000](http://localhost:9000)
5. Open `bug-tracker.jh`
   - Edit the JDL with the JHipster IDE extension already setup for you !
   - Import it in your app: `jhipster import-jdl bug-tracker.jh`
