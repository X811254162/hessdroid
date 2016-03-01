# hessdroid - android hessian library #

hessdroid is an Android port of the Java hessian library provided by Caucho (0). it is supposed to be very light-weight, even lighter as the original Java lib since it doesn't contain most of the server-side classes and JEE related stuff (servlets, JNDI, etc.).

hessdroid is built on top of standard JDK classes found in Android - without further dependencies to third-party libraries.

hessian is a binary web service protocol. among other design goals it was designed to be as fast, as compact and as simple as possible. the up-to-date specification can be found at (1).

Since it is language-independent, a number of implementations are available for a vast majority of programming languages (2).

**Quick-Start**

let's assume we have a web service with the following interface

```
public interface TestAPI  {
   public abstract String saySomething();
}
```

in order to instantiate a web-service client, use `HessianProxyFactory`

```
String webServiceUrl = "https://localhost/testAPI";

HessianProxyFactory proxyFactory = new HessianProxyFactory();
// setting a user/password calls the web service with basic authentication
proxyFactory.setUser("john");
proxyFactory.setPassword("doe");

TestAPI api = (TestAPI) proxyFactory.create(TestAPI.class, webServiceUrl, getClassLoader());

System.out.println(api.saySomething());
```

_hint:_ the only thing that is specific to Android is the last parameter of the `HessianProxyFactory.create()`call: `getClassLoader()`. if we wouldn't specify the class-loader `Thread.getContextClassLoader()` would have been used which is - in the case of Android - not the correct class loader. In Android you have to use Context.getClassLoader (3) which returns the application package class-loader.

Of course `TestAPI` is a very simple interface as you might have noticed. indeed, hessian serialization was designed for real object-orientation, which includes using reference types (custom classes) as return or parameter types.

A brief introduction to Hessdroid is found on slideshare: http://www.slideshare.net/hessdroid/hessdroid

**References**

(0) http://hessian.caucho.com/#Java

(1) http://hessian.caucho.com/doc/hessian-serialization.html

(2) http://hessian.caucho.com/#Hessian%20Implementations/Download

(3) http://developer.android.com/reference/android/content/Context.html#getClassLoader()