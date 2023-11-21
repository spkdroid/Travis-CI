# Travis-CI

### Step 1: Set up your Java project with Gradle

1. Create a new Gradle project or use an existing one.

2. Add a basic JUnit test to your project.

### Step 2: Create a Travis CI configuration file

Create a file named `.travis.yml` in the root of your project. This file will define the build and test configurations for Travis CI.

```yaml
language: java
jdk:
  - openjdk11

# Specify the script to run for the build
script:
  - ./gradlew test
```

This configuration file tells Travis CI to use Java, specifically OpenJDK 11, and run the Gradle test task.

### Step 3: Set up Travis CI

1. Go to [Travis CI](https://travis-ci.org/) and sign in with your GitHub account.

2. Once signed in, click on your profile picture in the top-right corner and select "Accounts."

3. Enable Travis CI for your Java project repository.

### Step 4: Trigger a build

1. Commit and push your changes to GitHub.

2. Go to your Travis CI dashboard, and you should see a new build triggered for your repository.

3. Monitor the build progress on Travis CI. If everything is set up correctly, your build should pass.

### Optional: Add more build steps

You can extend your `.travis.yml` file to include additional steps, such as deploying your application after a successful build.

```yaml
language: java
jdk:
  - openjdk11

# Specify the script to run for the build
script:
  - ./gradlew test

# Example: Deploy to Heroku after a successful build
deploy:
  provider: heroku
  api_key: $HEROKU_API_KEY
  app: your-heroku-app-name
```

In this example, the `deploy` section is configured to deploy the application to Heroku. Replace `your-heroku-app-name` with the actual name of your Heroku app. Ensure you set the `HEROKU_API_KEY` environment variable in the Travis CI repository settings.
