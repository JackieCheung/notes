**Spring boot配置支持vue-router的history模式**

```
@Bean
public WebServerFactoryCustomizer<ConfigurableWebServerFactory> webServerFactoryCustomizer(){
 return factory -> {
  ErrorPage error404Page = new ErrorPage(HttpStatus.NOT_FOUND, "/index.html");  
  factory.addErrorPages(error404Page);
 };
}
```

