## OpenFlights 
### A flight reviews app built with Ruby on Rails and React.js

This app is intended to be a simple example of a CRUD app built with **Ruby on Rails** and **React.js** using **Webpacker**.

---

This app uses:

* Ruby version: `2.7`
* Rails version: `6.0.3.4`
* Database: `postgresql`
* React version: `16.12.0`
* React Hooks API
* React Context API

## Running it locally
- run `bundle exec rails db:prepare`
- run `npm install` or `yarn install`
- run `bundle exec rails s`
- in another tab run `./bin/webpack-dev-server` (optional) 
- in another tab run `sidekiq` (optional, but necessary for things like password reset emails)
- navigate to `http://localhost:3000`

## Environment Variables
If you want functionality like password reset emails to work locally, you'll need to set the following environment variables in `config/application.yml` with your own unique values:
```
ROOT_URL: http://localhost:3000
SENDGRID_API_KEY: xxxxxxxxxxxxxx
SENDGRID_USERNAME: xxxxxxxxxxxxxx
SENDGRID_PASSWORD: xxxxxxxxxxxxxx
DEFAULT_FROM_EMAIL: you@example.com
```

## Routes
```shell
             Prefix Verb   URI Pattern                           Controller#Action
               root GET    /                                     pages#index
    api_v1_airlines GET    /api/v1/airlines(.:format)            api/v1/airlines#index
                    POST   /api/v1/airlines(.:format)            api/v1/airlines#create
 new_api_v1_airline GET    /api/v1/airlines/new(.:format)        api/v1/airlines#new
edit_api_v1_airline GET    /api/v1/airlines/:slug/edit(.:format) api/v1/airlines#edit
     api_v1_airline GET    /api/v1/airlines/:slug(.:format)      api/v1/airlines#show
                    PATCH  /api/v1/airlines/:slug(.:format)      api/v1/airlines#update
                    PUT    /api/v1/airlines/:slug(.:format)      api/v1/airlines#update
                    DELETE /api/v1/airlines/:slug(.:format)      api/v1/airlines#destroy
     api_v1_reviews POST   /api/v1/reviews(.:format)             api/v1/reviews#create
      api_v1_review DELETE /api/v1/reviews/:id(.:format)         api/v1/reviews#destroy
                    GET    /*path(.:format)                      pages#index
```

---
