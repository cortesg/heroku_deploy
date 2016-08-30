# Rails app deployment: #

## In any folder (you only need to do this once in your lifetime): ##
* $brew install postgresql

## On your app folder/repo: ##
1. $heroku login
2. database.yml - copy from this repo and paste into your database.yml.
3. Gemfile - Starting from line 36, copy and paste into your Gemfile.
4. $bundle
5. *(If you have an API Key)* secrets.yml - copy and paste code in production like so (but replace googlemaps_api_key with yours):
6. $git add -A && $git commit -m "deployment" *(the commit message can be whatever)* && $git push origin master
7. $heroku create
8. $heroku apps:rename <newname> *(if you want a new name)*
9. $git push heroku master *(if successful, move to next step)*
10. $heroku run rake db:migrate
11. *(If you have an API key)* On heroku.com, go into Settings in your app. Click "Reveal Config Vars" and paste your actual API code.
12. $heroku open
