# ReactJs sample project:

## Example of docker commands to build and run the environment

In the project directory, you can run:

```sh
# ...\src\services\frontend\
docker build .
docker run -p 7000:80 --rm -it react-nginx
```

Runs the app in the production mode.\
Open [http://localhost:7000](http://localhost:7000) to view it in the browser.
