# Main Configurations List in JKFramework

This section includes the available confituration and its defaults in the framework.

## Generic
| Config Name	| Default	| Description|
|---|----|----|
|app.name|JKFramework-App| A name for your app or your component|
|jk.encKey|SetMeIneEnvVaria|The encryption key used in encryption and decryptions, this shuold be set as environment variable |

## Pre Config
| Config Name	| Default	| Description|
|---|----|----|
|git-url|-|Repository URL used for loading your configuration|
|git-keep-local|false|Keep/Remove cloned repository folder|
|git-branch|master|Target Git branch|
|git-password-plain|-|Repo password in plain text (Not recommanded)|
|git-password|-|Encrypted Password of your git account|
|git-username|-|Usename of you git account|
|git-local-path|Temporary folder that will be created automcatally|The path where your repository should be cloned|

## Web and WebStack
| Config Name	| Default	| Description|
|---|----|----|
|jk.web.config.resetjk.web.config.reset|true|Enable reload config servlet by calling /config/reset|
|jk.web.versions|true| Enable version servlets at /version|
|jk.web.mvc.models.package|com.app| Under development|
|jk.security.enabled|false|Enable spring security for this app, default usename/password wil be admin/admin|
|jk.web.security.public_url|/services/*, /index.xhtml, /error/*, /login/*, /public/*, /resources/*, *.css, *.js, /javax.faces.resource/*, /util/* |-| 

## Microservices
| Config Name	| Default	| Description|
|---|----|----|
|jk.service.crosscutting.logservice.enabled|false|Enable unified logging service for all mciroservices out of the box|
|jk.service.crosscutting.logservice.base|-|The url of the logging service|
|jk.service.crosscutting.logservice.async|true|Log service using Async to avoid blocking|
|jk.service.url.visibleOnError|true|Show microserices URLs on communications failures|
|jk.service.allowed.ip|-|Comma serpated values of the allowed IP's to call a microservice|
|jk.service.connect_timeout|10 seconds|The connection timeout from Microserice client to amicroservice|
|jk.service.read_timeout|20 seconds|The default timeout waiting for a microsrvice to return a result|
|jk.services.headers.enabled|false|Utility used to dump the header of the header of Microservice client on the Microservice side| 
|jk.config.allowReload|true|Allow reload microservices configurations|
|jk.services.info.enabled|flase|| 
|jk.logs.allowReadFile|false||
|jk.config.allowReadConfig|false|-|
|jk.services.workflow.url|-|URL of the workflow microservice |

## JPA Config
| Config Name	| Default	| Description|
|---|----|----|
|db-entities-packages|com.app|The package names to scan for JPA entities. CSV value is allowed for multiple packages|
|jk.data.connection.set_client_info|false|Set the client information on the database session, usfull for troubleshooting purposes|
|jk.data.orm.results.max|1000|-|

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

## MongoDB Config:
If you don’t provide the configuration, defaults will be applied:

| Config Name	| Default	| Description|
|---|----|----|
|nosql.url|mongodb://localhost:27017/|-|
|nosql.db.name|app|Default Database name|
|nosql.db.user|-|Default Database user|
|nosql.db.password|-|Default Database password|
