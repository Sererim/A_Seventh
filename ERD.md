```xml

Products {
	id integer pk increments
	name varchar
	price decimal
	description text null
	provide integer *> Provider.id
}

DeliveryTo {
	id integer pk increments
	product integer *> Products.id
	arrival datetime *> Provider.canDeliver
}

Stock {
	id integer pk increments
	address text
	product integer *> Products.id
	amount integer
	phonenumber varchar
}

DeliveryOut {
	id integer pk increments
	stock integer *> Stock.id
	product integer *> Products.id
	date datetime
}

Provider {
	id integer pk increments
	name text
	price decimal
	amount integer
	phonenumber varchar
	description text
	canDeliver datetime
}
```
