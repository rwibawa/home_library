# home_library
Rails 5.1.4 as RESTful API
[tutorial](https://www.angularonrails.com/getting-started-with-angular-and-rails/)

## 1. Rails setup
```bash
$ rvm --default use 2.3.0
$ rvm list
$ rvm gemset list
$ rvm gemset create rails-5.1.4
$ rvm gemset use rails-5.1.4
$ gem install rails -v 5.1.4

$ rails new home_library --api -T -d postgresql
$ cd home_library/
```

## 2. Create resource

### 1. Create db by configure `config/database.yml`
```bash
$ rails db:create
$ rails generate scaffold book name:string
$ rails db:migrate

$ vi db/seeds.rb
```

### 2. Create seeds in `db/seeds.rb`
```ruby
Book.create!([
  { name: 'Copying and Pasting from Stack Overflow' },
  { name: 'Trying Stuff Until it Works' }
])
```

```bash
$ rails db:seed
$ rails server
```

Open [http://localhost:3000/books.json](http://localhost:3000/books.json).
Open [http://localhost:3000/books/1](http://localhost:3000/books/1).

## 3. Enable CORS
Uncomment 'rack-cors' in the Gemfile, also uncomment the CORS configuration in `config/initializers/cors.rb`.
