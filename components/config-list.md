# Main Configurations List in JKFramework

This section includes the available confituration and its defaults in the framework.

## Hibernate and C3P0 Connection  
Below are the default Hibernate configuration used by the framework. We use C3p0 connection pool implementation; Detailed configuration description be found at C3p0 Official Documentaion

| Header Name|	Default	|Description|
|-----------|----------|----------|
|hibernate.connection.url| jdbc:h2:file:~/.jk/h2-db/h2db2.data | File based database with name h2db.data in the current working directory.
|hibernate.connection.username|sa|default username of H2|
|hibernate.connection.password|sa|default password of H2|
|hibernate.connection.driver_class|-|-|
|hibernate.dialect|-|-|
|hibernate.c3p0.max_size|100|Maximum number of JDBC connections in the pool|
|hibernate.c3p0.min_size|1|The minimum number of JDBC connections that C3P0 keeps ready at all times|
|hibernate.physical_naming_strategy|-|-|
|hibernate.id.new_generator_mappings|false|-|
|hibernate.globally_quoted_identifiers|true|-|
|hibernate.use_sql_comments|-|-|
|hibernate.format_sql|true|Format the generated SQL statement|
|hibernate.show_sql|true|Show Generated SQL statement|
|hibernate.connection.autocommit|true|Default to Auto Commit|
|hibernate.hbm2ddl.auto|update|Create tables of not exists|
|hibernate.c3p0.contextClassLoaderSource|library|-|-|
|hibernate.c3p0.debugUnreturnedConnectionStackTraces|true|-|
|hibernate.c3p0.unreturnedConnectionTimeout|3600|-|Defines a limit (in seconds) to how long a connection may remain checked out|
|hibernate.c3p0.acquireRetryDelay|10000|-|
|hibernate.c3p0.acquireRetryAttempts|1|-|
|hibernate.c3p0.idleConnectionTestPeriod|30|-|
|hibernate.c3p0.preferredTestQuery||-|-|
|hibernate.c3p0.testConnectionOnCheckout|true|-|
|hibernate.c3p0.maxConnectionAge|-|-|
|hibernate.c3p0.timeout|3600|-|Release un-needed connections above the min-size|
|hibernate.c3p0.acquire_increment|1|-|

Configurations Defaults:
If you don’t provide the configuration, defaults will be as follows:

Header Name	Default	Description
app.name

app

Your application name

nosql.url

mongodb://localhost:27017/

-

nosql.db.name

app

Default Database name.

nosql.db.user

Default Database user.

nosql.db.password

Default Database password.

git-url

-

Repository URL (The place where your code is stored).

git-keep-local

false

Keep/Remove cloned repository folder.

git-branch

master

Target Git branch.

git-password-plain

-

-

git-password

-

Password of your git account.

git-username

-

Usename of you git account.

git-local-path

-

The path where your repository should be cloned.

db-entities-packages

com.app

The package names to scan for JPA entities. CSV value is allowed for multiple packages

jk.data.connection.set_client_info

false

-

jk.data.orm.results.max

1000

-

jk.remote.app.name

-

-

jk.security.enabled

false

-

jk.service.crosscutting.logservice.enabled

false

-

jk.service.crosscutting.logservice.base

-

-

jk.service.crosscutting.logservice.async

true

-

jk.service.url.visibleOnError

true

-

jk.service.allowed.ip

true

-

jk.service.connect_timeout

10

-

jk.service.read_timeout

20

-

jk.services.headers.enabled

true

-

jk.config.allowReload

true

-

jk.services.info.enabled

true

-

jk.logs.allowReadFile

true

-

jk.config.allowReadConfig

false

-

jk.services.workflow.url

-

-

jk.web.security.public_url

DEFAULT_PUBLIC_URLS

-

jk.web.session.username

-

-

jk.web.config.reset

true

-

jk.web.versions

true

-

jk.web.mvc.models.package

com.app

-

jk.encKey

SetMeIneEnvVaria

-

