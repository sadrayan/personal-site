# Sadra Abrishamkar Personal Site

Hello. This is my simple personal website. In this excercies we push a simple jekyll based website to AWS S3 with Github Actions pipelines.

## Steps for Setup:

### Make sure you have Ruby

First, make sure you have [Ruby](https://www.ruby-lang.org/en/) installed. 

```sh
$ ruby -v
ruby [version number] (date) [your platform]
```

### Make sure you have Bundler

Next, make sure you have [Bundler](https://bundler.io) installed. 

```sh
$ bundle -v
bundle [version number]
```

### Run this repository

Clone the repository, and `cd` into it:
```sh
$ git clone https://github.com/sadrayan/personal-site.git
$ cd personal-site
```

Install dependencies locally:
```sh
$ bundle install 
```

Now run the server:
```sh
$ bundle exec jekyll serve
```
