## Setup project to ready for Heroku

- nvm/npm
- clone repo
- update dependencies
- pull a postgres image
- run postgres image, remember to expose port on localhost
- psql -U ... -h ...
- create a db (chicken/egg problem if you don't create the DB first...)
- setup .env file
- install db-migrate (supports DATABASE_URL + dotenv) + db-migrate-pg
- install heroku cli
- npm start - oops no schema
- npm release (builds local schema)
- npm start

## Create our first app

- create app (shefdevops-todo-staging)
- add a postgres db
- hook up to Github
- enable automatic deploys (doesn't bootstrap)
- deploy
- show build log, release log, and app

## Create a pipeline

- add to a pipeline (shefdevops-demo)
- add a production app (shefdevops-todo-prod)
- add postgres DB
- deploy

## Release a change

- enable review apps (note app.json)
- fetch; create new branch with new /api/v1/environment endpoint
- push; create PR
- note review app; deploy it
- note endpoint doesn't know what env it is - add TODO_ENV environment variable
- merge PR; show review app is gone, and staging is deploying
- add TODO_ENV to staging
- show
- add TODO_env to production
- Promote; show endpoint works

## DONE!

## Notes
- everything done at the UI can be done on the command line
- branch histories reflect reality (no 'extra' commits on staging or master)
- there is a manual deploy step, plus UI/API to handle it
- CI is available ($10 per month + resource costs), deploy to staging stops if CI doesn't pass
- more complex environments are harder to deal with if they depend on one another
- managing state is always super-important but even more so with changes flowing through pipelines (db-migrate, release task)
- only a handful of source controls systems support (eg. Github)

## Resources
- https://devcenter.heroku.com/articles/pipelines
- https://devcenter.heroku.com/articles/heroku-ci
