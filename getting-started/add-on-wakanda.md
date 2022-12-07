---
coverY: 0
---

# 💶 Add on Wakanda

First you need to add the **api-registry** dependency to your project's BFF (since your UI application is only supposed to call a BFF and then the BFF orchetrates the calls to necessary downstream services),

```
<dependency>  
  <groupId>com.navi.medici</groupId>  
  <artifactId>api-registry</artifactId>  
  <version>${api-registry.version}</version>  
</dependency>
```

Use the latest api-registry version (check nexus or contact the neon team).

**api-registry** is a module within wakanda repository will call wakanda service pods at runtime to fetch page configurations. You'll need to add some environment configs needed by api-registry such as and also base urls of other downstream services from which data will be fetched for your UI.

```
WAKANDA_BASE_URL: <https://dev-wakanda.np.navi-tech.in>
DOWNSTREAM_RESPONSE_MAX_BUFFER_SIZE: 10485760
```

Next and final setup is to add this controller in your application,

```
package com.navi.medici.webbff.controllers.api;

import static org.springframework.http.MediaType.APPLICATION_JSON_VALUE;
import com.navi.medici.webbff.commons.RequestUtils;
import com.navi.sa.metric.MethodMetric;
import com.navi.sa.mjolnir.config.Authorized;
import com.navi.wakanda.apiregistry.service.PageBuilderService;
import java.util.Map;
import javax.servlet.http.HttpServletRequest;
import lombok.extern.log4j.Log4j2;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.HttpHeaders;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@Log4j2
@RequestMapping("/configuration")
@RestController
public class PageConfigurationsController {

@Autowired
private PageBuilderService pageBuilderService;

	@PostMapping(value = "/uri/**", produces = APPLICATION_JSON_VALUE)
	@Authorized(value = {"ui-template.page.config.read"})
	@MethodMetric("bff_get_template_page_config")
	public ResponseEntity<Object> generatePage(HttpServletRequest httpServletRequest, @RequestBody String requestBody) {
	
		final HttpHeaders headers = RequestUtils.duplicateHeaders(httpServletRequest);
		
		Object res = pageBuilderService.sendPageResponse(httpServletRequest.getRequestURI(),
		headers, Map.of(), requestBody);
		
		return ResponseEntity.ok(res);
	}

}
```

With this controller,

* BFF will be able to receive page configuration requests from your UI application. This controller uses `PageBuilderService` from the **api-registry** dependency to fetch configurations, make calls to downstream services if needed, stitch the response data with configuration and return the kind of response needed by _Shuri_ UI dependency.
* Add any necessary customisations like `@Authorized` security permissions or `@MethodMetric` performance metrics needed for your applications' requirements.

**NOTE: Don't forget to add wakanda's outbound connectivity in your BFF's deployment portal manifests.**
