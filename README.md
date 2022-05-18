# chmbrlnd.github.io

Before completing these operations, issuing the command ``xcode-select --install`` may be required.


## Get Theme

[GitHub Pages](https://pages.github.com/) support only certain themes.
These themes are aimed at the creation of single-page website for projects, as opposed to more elaborate sites.
Select a theme, such as [minima](https://github.com/jekyll/minima), and clone its repository.
```
git clone https://github.com/jekyll/minima.git
```
Collect pertinent files or change ```git remote```.
```
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
git remote -v
```
Add content in markdown format.


## Installing [Jekyll](http://jekyllrb.com/)

```
sudo gem install jekyll
sudo gem install bundler
cd /path/to/directory      # Dir with Gemfile
bundle install
```


## Updating [Jekyll](http://jekyllrb.com/)

```
sudo gem update jekyll
sudo gem update bundler
cd /path/to/directory      # Dir with Gemfile
bundle update
```

## Building or Running [Jekyll](http://jekyllrb.com/) with [Bundler](http://bundler.io/)

```
cd /path/to/directory      # Dir with Gemfile
bundle exec jekyll serve   # http://127.0.0.1:4000
```

Note that ```bundle exec``` should NOT be run as sudo.

To keep Jekyll up to date, it is important to issue the ```bundle update``` command periodically.
Running executables without ```bundle exec``` may work, however this is unreliable and is often the source of considerable pain.


## Publishing on CoE Server

Edit ```_config.yml``` for CoE server and set target ```url``` and ```baseurl```.
```
url: "https://people.engr.tamu.edu"
baseurl: "/chmbrlnd"
```

Build [Jekyll](http://jekyllrb.com/) with [Bundler](http://bundler.io/).
```
bundle exec jekyll build
```

Push to [CoE server](https://bit.ly/engr-people-site-instructions).
```
cd _site/
sftp people-edit.engr.tamu.edu
sftp> put source destination
sftp> bye
```

Note ```sftp``` is native on the shell, but it is primitive and unpleasant.
