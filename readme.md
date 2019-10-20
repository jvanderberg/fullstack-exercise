# Yes Energy Fullstack exercise

This is a fully self-contained exercise which has a React based front end, a Django/Python based middle tier, and a Postgres backend.

This is a 'toy' application that uses data that resembles data we use every day at Yes Energy, and data sets that are large enough to present some of the problems we face, but not large enough we can't deliver it embedded in a git repository that's easy to install.

## Installing / Running

1. Install Docker
2. Clone the repo into a local directory
3. In that directory run ```docker-compose up```

You will likely have to wait a good bit of time, as yarn can take quite a bit of time to install dependencies in the React project.  You should see a log message referencing localhost:3000, when you see that, everything is up and running.

This long wait should only happen the first time you run.

## Using the application

Navigate to http://localhost:3000.  This is a simple React application that makes a fetch request to the Django middle tier.  The Django middle tier issues SQL to the Postgres data base which contains a small subset of public energy market data.

## Making changes

Both the Django application and the React application watch for file changes and reload immediately to reflect those changes.

To change the React application, edit the files in frontend/src.

To change the Djando application, edit the files in server/composeexample, views.py and urls.py.

## Connecting to the database

Make sure the docker instance is running, and then in another terminal issue the command:

```docker-compose run web psql -p 5432 -U postgres -h db```

psql cheatsheet

- \l List databases
- \dt List tables
- \di List indexes
- \dv List views
- \d tablename Describe tablename

psql supports most common SQL syntax
See: https://gist.github.com/Kartones/dd3ff5ec5ea238d4c546
