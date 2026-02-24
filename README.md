# Little Shop - Backend

Little Shop is a Ruby on Rails backend API that powers an e-commerce style application for managing merchants and their items. The application exposes RESTful endpoints that allow users to view all merchants, view a single merchant and their associated items, browse all items across merchants, and sort results for flexible data exploration.

The API supports full CRUD functionality for merchants, including the ability to create, update, and delete records. Items are associated with merchants through relational database modeling, enabling nested routes such as viewing all items that belong to a specific merchant.

This backend is fully tested using RSpec and includes test coverage reporting with SimpleCov, ensuring reliable behavior and maintainable code. The project emphasizes clean RESTful design, strong model relationships, and comprehensive test-driven development practices.

## Installation Instructions:
1. Fork and clone this repository to your local machine
2. Install any dependencies with ```bundle install```
3. Run ```rails db:create```
4. Run ```rails db:migrate```
5. Run ```rails db:seed```
6. Start the server with ```rails s```
7. Frontend server can be found here https://github.com/MaiaKBard/little-shop-fe

## Running rspec tests and simpleCov report:
In your terminal at the root directory run: 
```bash 
bundle exec rspec
```
To view simpleCov report:
```bash
open coverage/index.html
```

## API Endpoints
### Invoices
* ``GET /api/v1/merchants/#{merchant.id}/invoices?status=shipped`` <br>
  returns all invoices that have the status of 'shipped'
* ``GET /api/v1/merchants/#{merchant.id}/invoices?status=returned`` <br>
  returns all invoices that have the status of 'returned'
### Items
* ``GET /api/v1/items`` <br>
  returns all items
* ``GET /api/v1/items?sorted=price`` <br>
  returns all items, sorted by price
* ``GET /api/v1/items/item_id`` <br>
  returns a single item
* ``DELETE /api/v1/items/#{item.id}`` <br>
  deletes an item
* ``POST /api/v1/items`` <br>
  creates a new item
* ``PATCH /api/v1/items/:id`` <br>
  updates an item
* ``GET /api/v1/merchants/#{merchant.id}/items`` <br>
  returns all of a merchants items
### Merchants
* ``GET /api/v1/items/#{item.id}/merchant`` <br>
  returns a merchant for a particular item
* ``GET /api/v1/merchants`` <br>
  returns all merchants
* ``GET /api/v1/merchants?sorted=age`` <br>
  returns all merchants sorted by when they were created, newest first
* ``GET /api/v1/merchants?status=returned`` <br>
  returns all merchants with returned items
* ``GET /api/v1/merchants/merchant.id`` <br>
  returns one merchant
* ``POST /api/v1/merchants`` <br>
  creates a new merchant
* ``PATCH /api/v1/merchants/:id`` <br>
  updates a single merchant
* ``DELETE /api/v1/merchants/#{merchant.id}`` <br>
  deletes a merchant (also deletes associated items and invoices)
* ``GET /api/v1/merchants/:merchant_id/customers`` <br>
  returns all customers for a merchant



