This folder structure should be suitable for starting a project that uses a database:

* Fork this repo
* Clone this repo
* Run `bundle install` to install `active_record`
* `rake generate:migration <NAME>` to create a migration (Don't include the `<` `>` in your name, it should also start with a capital)
* `rake db:migrate` to run the migration and update the database
* Create models in lib that subclass `ActiveRecord::Base`
* ... ?
* Profit


## Rundown

```
.
├── Gemfile             # Details which gems are required by the project
├── README.md           # This file
├── Rakefile            # Defines `rake generate:migration` and `db:migrate`
├── config
│   └── database.yml    # Defines the database config (e.g. name of file)
├── console.rb          # `ruby console.rb` starts `pry` with models loaded
├── db
│   ├── dev.sqlite3     # Default location of the database file
│   ├── migrate         # Folder containing generated migrations
│   └── setup.rb        # `require`ing this file sets up the db connection
└── lib                 # Your ruby code (models, etc.) should go here
    └── all.rb          # Require this file to auto-require _all_ `.rb` files in `lib`
```

1) Users.count = 50

2) Items.order('price DESC').first(5)
1.	Small Cotton Gloves
2.	Small Wooden Computer
3.	Assome Granite Pants
4.	Sleek Wooden Hat
5.	Ergonomic Steel Car

3) Items.where(category: 'Books').order('price ASC').first
⁃	Ergonomic Granite Chair

4a) Users.where(id: Addresses.where(street: '6439 Zetta Hills').pluck(:user_id))
⁃	Corrine Little

4b) Addresses.where(user_id: 40)
⁃	Second Address: 54369 Wolff Forges, Lake Bryon, CA, 31587

5) 

6) Items.where(Category: 'Tools').sum('price')
⁃	7383

7) Orders.sum('quantity')
⁃	2125

8)  

9) 
⁃	Users.create({id: Users.count + 1, first_name: 'Travis', last_name: 'Montgomery',  email: 'travisbm@gmail.com'})
⁃	Orders.create({id: Orders.count + 1, user_id: 51, item_id: 4, quantity: 2})



