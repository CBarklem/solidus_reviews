# Reviews

[![Build Status](https://travis-ci.org/spree-contrib/spree_reviews.svg?branch=master)](https://travis-ci.org/spree-contrib/spree_reviews)
[![Code Climate](https://codeclimate.com/github/spree-contrib/spree_reviews/badges/gpa.svg)](https://codeclimate.com/github/spree-contrib/spree_reviews)

Straightforward review/rating functionality.

---

## Installation

```ruby
 gem 'spree_reviews', github: 'spree-contrib/spree_reviews', branch: 'X-X-stable'
 ```

 The `branch` option is important: it must match the version of Spree you're using.
 For example, use `3-0-stable` if you're using Spree `3-0-stable` or any `3.0.x` version.

Now bundle up with:

    bundle

Next, run the rake task that copies the necessary migrations and assets to your project:

    bundle exec rails g spree_reviews:install

And finish with a migrate:

    bundle exec rake db:migrate

Now you should be able to boot up your server with:

    bundle exec rails s

That's all!

---

## Usage

Action "submit" in "reviews" controller - goes to review entry form

Users must be logged in to submit a review

Three partials:
 - `app/views/spree/products/_rating.html.erb` -- display number of stars
 - `app/views/spree/products/_shortrating.html.erb` -- shorter version of above
 - `app/views/spree/products/_review.html.erb` -- display a single review

Administrator can edit and/or approve and/or delete reviews.

## Implementation

Reviews table is quite obvious - and note the "approved" flag which is for the
administrator to update.

Ratings table holds current fractional value - avoids frequent recalc...

---

## Discussion


