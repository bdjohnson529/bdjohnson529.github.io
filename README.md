# Jekyll deployed on Heroku

This is a Jekyll blog, deployed on Heroku. Documentation is included to demonstrate deployment.


## Deployment
Configure Git repo for Heroku deployment.

		heroku git:remote -a myherokusite
		heroku buildpacks:add heroku/ruby

Deploy:

		git push heroku master
		heroku open


## References
- [Jekyll on Heroku](https://blog.heroku.com/jekyll-on-heroku)