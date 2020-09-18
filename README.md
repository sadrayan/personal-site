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

### Github Action
```
name: Upload Website

on:
  push:
    branches:
    - master

jobs:
  jekyll:
    name: Build and deploy Jekyll site
    runs-on: ubuntu-latest

    steps:
    - name: Checkout
      uses: actions/checkout@v2
      
    - name: Build
      uses:  lemonarc/jekyll-action@1.0.0

    - name: Configure AWS credentials
      uses: aws-actions/configure-aws-credentials@v1
      with:
        aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
        aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        aws-region: us-west-2

    - name: Sync output to S3
      run: |
        aws s3 sync ./_site/ s3://sadrayan --delete
```
