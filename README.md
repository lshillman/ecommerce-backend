# eCommerce Backend

[![Hippocratic License HL3-FULL](https://img.shields.io/static/v1?label=Hippocratic%20License&message=HL3-FULL&labelColor=5e2751&color=bc8c3d)](https://firstdonoharm.dev/version/3/0/full.html)

Minimalist backend for a theoretical ecommerce site. Uses node, express, and mysql/sequelize.


---
**Table of Contents**
* [Installation](#installation)
* [Usage](#usage)
* [Demo video](#demo-video)
* [License](#license)
* [Questions](#questions)
---

## Installation

You'll need Node.js, npm, and mysql. Clone this repo. From your command line, go to the repo directory and run `npm install`, then log into mysql and run `source db/schema.sql`. If you want, you can also seed the resulting new database by running `node ./seeds/index.js`.

Open `.env.EXAMPLE` and change the database user and password to your own. Optionally, change the database name and host; these are `ecommerce_db` and `localhost` by default. Rename the file to `.env`.

With that out of the way, you can run `node server.js`.

## Usage

You can hit the endpoints to perform CRUD actions for categories, products, and tags.

Performing a GET request to `/api/categories`, `/api/products`, or `/api/tags` will return arrays of all categories, products, or tags, respectively.

### Categories
To **add a category**, send a POST request to `/api/categories` with a json body containing the new category's name, like so:

````JavaScript
{
	"category_name": "Underwear"
}
````
This will respond with the newly-created category's ID.

To **update** or **delete** a category, make a PUT or DELETE request to `/api/categories/id`, where "id" is your target category's ID number. Include the fields to update in the body of your request.

### Products
To **add a product**, send a POST request to `/api/products` with a json body containing the new products's info, like so:

````JavaScript
{
	"product_name": "Slice of ham",
	"price": 3.50,
	"stock": 400,
	"tagIds": [5, 7]
}
````
This will respond with the newly-created product's ID.

To **update** or **delete** a product, make a PUT or DELETE request to `/api/products/id`, where "id" is your target product's ID number. Include the fields to update in the body of your request.

### Tags
To **add a tag**, send a POST request to `/api/tags` with a json body containing the new tag's name, like so:

````JavaScript
{
	"tag_name": "best seller"
}
````
This will respond with the newly-created tag's ID.

To **update** or **delete** a tag, make a PUT or DELETE request to `/api/tags/id`, where "id" is your target tag's ID number. Include the fields to update in the body of your request.

## Demo video

https://user-images.githubusercontent.com/5232938/182014047-46431d76-a6e6-4c41-8c0e-bd4109896fd5.mp4


## License
This project uses the [Hippocratic License, v3.0](https://firstdonoharm.dev). TL;DR, it's not *quite* open source, but as long as you're not violating human rights, being a fossil fuel company, conducting military operations, etc (see license for full details), you can essentially treat it as open source.

## Questions?

Contact [lshillman](https://github.com/lshillman) via methods described at [lukehillman.net](https://lukehillman.net).
