# Rails app deployment: #
# IF YOU DO NOT HAVE A BACKEND, YOU MAY BE ABLE TO SKIP STEPS 2, 3, 4, and 10 (but please confirm with Orlando :D) 

## In any folder (you only need to do this once in your lifetime): ##
* $brew install postgresql

## On your app folder/repo (commit your code before starting this process): ##

1. $heroku login
2. database.yml - copy from this repo and paste into your database.yml.
3. Gemfile - Delete gem 'sqlite3' from your current app's Gemfile. Then, starting from line 36, copy and paste my Gemfile into your Gemfile. 
4. $bundle
5. *(If you have an API Key)* secrets.yml - copy and paste code in production like so (but replace googlemaps_api_key with yours)
6. $heroku create
7. $git add -A && $git commit -m "deployment" *(the commit message can be whatever)* && $git push origin master
8. $heroku apps:rename NewNameHere *(if you want a new name)*
9. $git push heroku master *(if successful, move to next step)*
10. $heroku run rake db:migrate
11. *(If you have an API key)* On heroku.com, go into Settings in your app. Click "Reveal Config Vars" and paste your actual API code.
12. $heroku open

## Troubleshooting ##

* $heroku logs --tail *(to see latest in logs)*
* $heroku restart (to restart)

#Please let Gino know if there are any errors. I will gladly fix it. :D#
:+1: :octocat:
