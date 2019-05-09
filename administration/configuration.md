# Configuration

Medkey can be configured via `.env` file, located in the root application directory.

Also there available two sample files of `.env`:

* `.env.prod` — production environment sample file;
* `.env.dev` — development environment sample file.

Each param at `.env` file must start from new line.

## .env parameters reference

### APP\_ENV

Describe application environment. Can be one of two values:

* `prod` — production environment
* `dev` — development environment

In production environment disabled debug errors output, disabled page error output \(using web error page with call stack trace\).

### APP\_DEBUG

Can be `true` or `false`. If true — you can see on page Yii2 debug panel.

For production must be `false`.

### APP\_DB\_CONNECTION

Can be one of two values:

* `pgsql` — will be used PostgreSQL driver;
* `mysql` — will be used MySQL/MariaDB driver.

### APP\_DB\_HOST

Hostname of database server. Can be 

* IPv4 address \(for example `127.0.0.1`\);
* URL \(for example `localhost`\).

For PostgreSQL you can set your database cluster host. By default for local installation of PostgreSQL it is `127.0.0.1`.

### APP\_DB\_PORT

Port of your database cluster \(for PostgreSQL\) or server \(for MySQL\).

By default for PostgreSQL main cluster port value is `5432`.

### APP\_DB\_NAME

Database name for your application. Must be created before setting.

### APP\_DB\_USERNAME

You database username, which will be used for all application to database connections.

### APP\_DB\_PASSWORD

Your database username password.

### SUPER\_LOGIN

Application superuser login. It will have all permissions inside application.

### SUPER\_PASSWORD

Application superuser login. It will have all permissions inside application.

### APP\_TYPE\_KEY

Application supports two types of database records identifiers: biginteger and UUID. Value can be:

* `bigint` — for biginteger type;
* `uuid` — for UUID \(GUID\) identifiers type.

Must be set before database migrations installation, cannot be changed on deployed application instance.

We recommend to use biginteger identifiers.

### WIDGET\_LOADER\_URL

URI with starting slash of widget loader. By default use `/ui/widget-loader/factory`.

Can be changed only in development purposes. For production use default value.

### APP\_TITLE

Application title, which used at the top side of menu and at login form. Can be overwritted by parameter set in user interface.

You can set here any line of text you want to see in your UI.

### JOB\_TIMEOUT

Timeout for background workers. By default `1200`, but can be increased.

### AUTH\_WITH\_EMPLOYEE

Can be `true` or `false`. If you want to disable login users without employee record — set value to `false` \(production value\).

If you have service users without employee records — set this value to `true` to enable their authentication ability.

### LANGUAGE

Default application language. Can be overriden by default language param, which can be set at UI. It will be used for all users, which haven't set their personally preferred language.

Value can be:

* `ru` - for russian language;
* `en` - for english language.



