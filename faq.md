# FAQ #

  * It seems hessdroid uses Hessian v1 - is v2 supported?
> Yes it is.
> Though hessdroid uses v1 as default, HessianProxyFactory can be easily switched to v2 mode:

```
  HessianProxyFactory factory = new HessianProxyFactory();
  ...
  factory.setHessian2Request(true);
  ...
```