
# JKFramework-Core

It is a set of API's, utilites, and wrapper that enables faster and reliable applications development, such as configurations, exception handling, context, I/O, and many others, and which are the intensivly used by the other projects in the framework

## Configuration  

This section includes the user-guide of JK-Framework configurations.

### Configuration properties

Please check the below link for more details about the list of available configs properties used by JK-Framework:
Available properties.

### Configuration Order
In JKFramework, the configuration are loaded from the following config sources based on the priorities-order:
1. Load `smartcloud.config` file if exists from current working directory, and override any configuration from the following config sources (useful for standalone deployments).
2. Load `test.config.properties` file if exists from the classpath, and override any configuration from the following config sources (useful for test automation).
3. Process `pre.config.properties` which shall contains a local path for the config and/or Git repository settings and overrider and properties configured in the later config sources (usefull for Microservices and Multi components systems). In this approach:  
  a) Look for _app.name_ property, if not found, look for it in the following config sources.   
  b) If _config.local.path_ is available, read `system.config.properties` and `${app.name}.config.properties` from it.   
  c) if _git-url_ is there, repository will be cloned to local folder  _config.local.path_ value if configured.   
  d) Read `system.config.properties` and `YOUR_APP_NAME.config.properties` from cloned repository.       
  e) If _git-keep-local_ property is false (default), the cloned local folder will be deleted once loaded.   
4. Load _JKFRAMEWORK_ENV_ key from system environment variable if exists, where the value is CSV key-value format of the configuration, and override any of the following configurations (usefull for apps with simple configurations which requireshost  operator ownership).
5. Load configuration from `config.properties` and override any of the following configurations.
6. Load configuration from `app.config.properties` and override any of the following configurations.
7. Load configuration from `system.config.properties` and override any of the following configurations.
8. Load configuration from `default.config.properties` (not recommended to use, since its loaded from the framework Data API’s).

Example of `pre.config.properties` that should put in _src/main/resources_ folder of your Maven project.

```properties
app.name=....
config.local.path=....
git-url=....
git-username=....
#git-password=.....
git-password-plain=.....
```

In your repository, you can have _system.config.properties_ file as default configuration for all the apps in your applications, also you can specify the configuration per module by having a file named _${app.name}.config.properties_ where ${app.name} is the value of your _app.name_ property in the _pre.config.properties_ mentioned above.

**TIP**: For confgurations profiles, you can use git branches as profiles, for example, you can create _dev_, _test_,  _staging_, and _prod_ branches.

**TIP:** If you have multiple projects and you don’t want to duplicate the git repository configuration in each project, you can place the _pre.config.properties_ in a commons lib project, and have _app.config.properties_ in each project with the _app.name_ key only.

To have more flexibility and security, you can replace your _config.properties_ or _pre.config.properties_ during the CICD process to have the right configuration or adding environment variables to avoid exposing production and other environments configurations to the non-authorized people.

JKFramework configuration is based on _Apache Commons Config_, so you can use the _system_, _constants_, or _environment_ variables as follows:

```properties
user.file = ${sys:user.home}/settings.xml
action.key = ${const:yourclass.CONSTANT_NAME}
java.home = ${env:JAVA_HOME}
```

### Basic Usage

Create `src/main/resources/config.properties` file inside your project in case of Maven projects, and the configurations you need. You may add predefined confguration values needed by the framework components or a custom config for your applications.

The following as an example of database configurtinos for a JKFramework-Data project:

````properties
#H2 Configurations
hibernate.connection.url = jdbc:h2:file:./h2db.data

#MySQl Config
#hibernate.connection.url = jdbc:mysql://localhost:3306/app?createDatabaseIfNotExist=true

#hibernate.connection.url = jdbc:oracle:thin:@localhost:1521/orclpdb1

hibernate.connection.username = sa
hibernate.connection.password = sa

#To build tables from Entities
hibernate.hbm2ddl.auto=update

#Package to scan for JPA entities, CSV value is allowed for multiple packages
db-entities-packages=com.app
````

### Config Initialization   
In most cases, configuration will be auto initlized and loaded during the application startups using listeners. However, if for some reason you want to initialize it your self, the first call to `JKConfig.get()` will auto configure it.

And to retrieve value from the configuration, use the following code:

String property = JKConfig.getDefaultInstance().getProperty("your-variable-name", "default value);
Multi-Database Support
In the config file, you can add a prefix to the same configuration used in normal database setup. Then you can call the

mydb.hibernate.connection.driver_class = oracle.jdbc.driver.OracleDriver
mydb.hibernate.connection.url =jdbc:oracle:thin:@0.0.0.0:1521:DB
mydb.hibernate.dialect =org.hibernate.dialect.Oracle12cDialect
mydb.hibernate.connection.username =user
mydb.hibernate.connection.password = pass
Microservices
jk.service.crosscutting.logservice.enabled=false jk.service.crosscutting.logservice.base jk.service.crosscutting.logservice.async=false jk.service.url.visibleOnError=true

Access Properties
Properties are all used internally by the framework, but if you need for any reason, you can access any property, use

Prior to versions 1-3, all the configuration was set on System properties, and could retrieved by:

System.getProperty(propertyName);
In version 4, it should be retrieved like this:

JKConfig.getDefaultInstance().getProperty(propertyName);
Home | License | FAQ | Contact | Smart-API
All copyrights reserved to Dr. Jalal Kiswani.
