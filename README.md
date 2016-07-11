# springboot-manager springboot 自我管理
  springboot 提供了一个强大的自我管理功能。通过http，即可获取下列信息
* 所有的bean信息
* 所有的环境变量
* 健康状态
* 性能变量
* 所有的URL映射
* 等等等等。

真的太方便了。

## 集成方法
### gralde
``` code
    compile("org.springframework.boot:spring-boot-starter-actuator")
```
### maven 
```
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

### 看看效果
```
==> http://localhost:7778/mappings
{
{[/jifen/start/olduser]}: {
bean: "requestMappingHandlerMapping",
method: "public java.lang.String com.sanhao.tech.jifen.web.JifenController.startOldUser()"
},
{[/error]}: {
bean: "requestMappingHandlerMapping",
method: "public org.springframework.http.ResponseEntity<java.util.Map<java.lang.String, java.lang.Object>> org.springframework.boot.autoconfigure.web.BasicErrorController.error(javax.servlet.http.HttpServletRequest)"
},
{[/error],produces=[text/html]}: {
bean: "requestMappingHandlerMapping",
method: "public org.springframework.web.servlet.ModelAndView org.springframework.boot.autoconfigure.web.BasicErrorController.errorHtml(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)"
},
{[/dump || /dump.json],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
},
{[/mappings || /mappings.json],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
},
{[/configprops || /configprops.json],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
},
{[/metrics/{name:.*}],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.MetricsMvcEndpoint.value(java.lang.String)"
},
{[/metrics || /metrics.json],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
},
{[/beans || /beans.json],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
},
{[/trace || /trace.json],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
},
{[/env/{name:.*}],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EnvironmentMvcEndpoint.value(java.lang.String)"
},
{[/env || /env.json],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
},
{[/autoconfig || /autoconfig.json],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
},
{[/jolokia/**]}: {
bean: "endpointHandlerMapping",
method: "public org.springframework.web.servlet.ModelAndView org.springframework.boot.actuate.endpoint.mvc.JolokiaMvcEndpoint.handle(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse) throws java.lang.Exception"
},
{[/info || /info.json],methods=[GET],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
},
{[/health || /health.json],produces=[application/json]}: {
bean: "endpointHandlerMapping",
method: "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.HealthMvcEndpoint.invoke(java.security.Principal)"
}
}
```
