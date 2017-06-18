# Kong Java Client

[Kong](https://getkong.org/) is a popular Open Source API Gateway. Kong Java Client makes it easy to configure the API Gateway through your code.

## Usage

    KongClient kongClient = new KongClient("http://localhost:8001");
    Consumer request = new Consumer();
    request.setCustomId("1234-5678-9012");
    Consumer response = kongClient.getConsumerService().createConsumer(request);

Look in the tests to find more examples.

## Supported Plugins

Besides the Admin APIs, Plugin configuration is also supported.

### Authentication Plugins
  * Basic Auth
  * Key Auth
  * HMAC Auth
  * JWT Auth
  * OAuth2
  * LDAP

### Security Plugins
  * ACL
  * IP Restriction

### Traffic Control Plugins
  * Rate Limiting
  * Request Size Limiting
  * Request Termination

Only those plugins are supported which might need configuration through code. For example, adding rate limit for a new consumer when there is a new signup. Plugins which require one time configuration are not supported.

Example Usage: To add credentials for a new Consumer for Basic Auth

    kongClient.getBasicAuthService().addCredentials("con-su-mer-id", "username", "password");