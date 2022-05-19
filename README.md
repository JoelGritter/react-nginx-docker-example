# react-nginx-docker-example

## Steps to get to this point:

### 1. Creating the React app
```
npx create-react-app example-app
cd example-app
npm start
```

Should result in a local version of the React app running. Nice.

### 2. Adding configuration files
Note the additional configuration files:
- `.dockerignore` - ignoring the node_modules to avoid bloat
- `nginx.conf` - for the sake of showing that you can use a custom nginx conf


### 3. Running the thing
Building the image:
```
docker build -t react-nginx .
```

Running the image:
```
docker run -p 8080:80 react-nginx
```

You should now be able to see the React app running at `localhost:8080`!