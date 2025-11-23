# OSV Client

A java http client library for OSV Client.

## Core Library

**Coordinates**

```
implementation("io.github.primelib:osv4j:<version>")
```

**Create client instances using the factory, you can choose different interfaces by changing the `api` parameter.**

```java
OsvClientApi client = OsvClientFactory.create(spec -> {
    spec.api(OsvClientApi.class);
    spec.baseUrl("https://api.osv.dev");
    //spec.meterRegistry(meterRegistry);
    //spec.logLevel("FULL");
});
```

## Spring Boot Starter

**Coordinates**

```
implementation("io.github.primelib:osv4j-spring-boot-starter:<version>")
```

**Auto Configuration**

| Property                                                   | Description                      | Default Value    | Allowed Values                     |
|------------------------------------------------------------|----------------------------------|------------------|------------------------------------|
| osv-client.url                       | Base URL of the API              | ""               |                                    |
| osv-client.backend-name              | Backend name for metrics tagging | ""               |                                    |
| osv-client.log-level                 | Log level for HTTP client        | ""               | none, full                         |
| osv-client.insecure                  | Disable SSL verification         | false            | false, true                        |
| osv-client.auth.type                 | Type of authentication           | ""               | oauth2-client, oauth2-user, bearer |
| osv-client.auth.token-endpoint       | Full token endpoint URL          | ""               | oauth2 token endpoint              |
| osv-client.auth.client-id            | Client ID for authentication     | ""               | oauth2 client id                   |
| osv-client.auth.client-secret        | Client secret for authentication | ""               | oauth2 client secret               |
| osv-client.auth.username             | Username for authentication      | ""               | oauth2 username (oauth2-user)      |
| osv-client.auth.password             | Password for authentication      | ""               | oauth2 password (oauth2-password)  |
| osv-client.auth.token                | Token / API Key                  | ""               |                                    |
| osv-client.auth.token-property-key   | Header key to pass the token in  | "Authorization"  |                                    |
| osv-client.auth.token-value-template | Template to generate token value | "Bearer {token}" |                                    |


## License

This project is licensed under the [MIT](https://github.com/primelib/osv-client/blob/main/LICENSE) license.
