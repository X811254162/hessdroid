# HessianProxyFactory #

Factory for creating Hessian client stubs.

```
String webServiceUrl = "https://localhost/testAPI";

HessianProxyFactory proxyFactory = new HessianProxyFactory();
// setting a user/password calls the web service with basic authentication
proxyFactory.setUser("john");
proxyFactory.setPassword("doe");

TestAPI api = (TestAPI) proxyFactory.create(TestAPI.class, webServiceUrl, getClassLoader());

System.out.println(api.saySomething());
```