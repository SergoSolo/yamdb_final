# REST API for YaMDb

Current library is REST API for YaMDb service which provides access for reading, creating and editing reviews for the following categories:

- Films;
- Books;
- Music;
- and other...

## Installation

You must have Docker installed and configured on your PC.

You neeb create file .env in directory infra_sp2/api_yamdb/infra/:
```
DB_ENGINE=<the db you are working with> 
DB_NAME=<db name>
POSTGRES_USER=<db login>
POSTGRES_PASSWORD=<create a password>
DB_HOST=<container name>
DB_PORT=<db port>
```

The next step is to run docker-compose:

```bash
docker-compose up -d
```
Make all necessary migrations:
```bash
docker-compose exec web python manage.py migrate
```
Create super user:
```bash
docker-compose exec web python manage.py createsuperuser
```
Collect static:
```bash
docker-compose exec web python manage.py collectstatic --no-input 
```

The project is now available at http://84.252.139.107/admin.

Status workflow:
https://github.com/SergoSolo/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg
1
## Resources

- **auth**: authentication.
- **users**: users.
- **titles**: titles for reviews (particular film, book or song).
- **categories**: categories (types) of titles (*Films, Books, Music*).
- **genres**: genres of titles. One title may be connected to many genres.
- **reviews**: reviews of titles. Review is connected to a particular title.
- **comments**: comments on titles. Comments is connected to a particular review.

## Usage

Every resource is described in documentation: endpoints (address for making query), types of queries which are allowed, access rights and auxiliary parameters if it necessary.

Get the entire description from the link below while your project is running:


```python
http://localhost/redoc/
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## Authors :man_technologist:

> [Alex](https://github.com/learies)

>[Sergey](https://github.com/SergoSolo)

> [Artur](https://github.com/Archy-A)

## License
Free
