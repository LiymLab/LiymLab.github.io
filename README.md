# regelab.github.io
====================

This website was built using the Zunder lab [website](http://zunderlab.com/), Ramani lab and the Fraser Lab [website](http://fraserlab.com/) as  templates.  These website is open-source and available on [Github_ZunderLab](https://github.com/zunderlab.github.io), [Github_RamaniLab](https://github.com/VRam142/VRam142.github.io) and [Github_FraserLab](https://github.com/fraser-lab/fraser-lab.github.io), 

#Information below retained from Zunder lab. Date: 4-01-2020

Technologies this website uses:  

    Jekyll  
    Github Pages  
    Twitter Bootstrap 3.2  

Before pushing changes, please check that they will work on your system first with the plugins included in the Gemfile using the bundler tool (results served at [0.0.0.0:4000](0.0.0.0:4000)):

    sudo gem install bundler
    bundle install
    bundle exec jekyll serve

To push changes, navigate to the root directory of zunderlab.github.io and execute the following commands:

	git add --all .
	git commit -m "version-specific note"
	git push origin master
