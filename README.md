Buildpack for the D programming Language for heroku
=========

This is the first prototype for an heroku buildpack for the D programing language.
For an example of use see https://github.com/pussinboots/dfirstweb this is a simple
rest service written in the D programming language based on the vibe.d framework.

Personal
=========

I'am a newbee in programming with D. Before 2 years Java was my first choice to 
work with but after a while i did some projects with scala, groovy and also javascript.
So D was i think the next step to give it a try. What i love about java, scala was the
good tool support specialy the open continous server travis ci (https://travis-ci.org) 
and as Platform as a Service heroku of course. So i know where to start my journey with D
. I found a good buildpack for D (https://bitbucket.org/mikehouston/heroku-buildpack-d/wiki/Home) 
but it was not up to date so i fixed it and the result here it is.

Travis Ci
=========

How to build a project written with the D language see the .travis.yml file here https://github.com/pussinboots/dfirstweb/blob/master/.travis.yml .

    language: dlang
    script: dub build
    before_install: 
    - sudo wget http://netcologne.dl.sourceforge.net/project/d-apt/files/d-apt.list -O /etc/apt/sources.list.d/d-apt.list
    - sudo apt-get update && sudo apt-get -y --allow-unauthenticated install --reinstall d-apt-keyring && sudo apt-get update
    - sudo apt-get install dub
    - sudo apt-get install dmd-bin
