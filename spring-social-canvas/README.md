This sample app demonstrates how to use Spring Social within a Facebook Canvas application.

IMPORTANT NOTE: As it currently is written, Spring Social Canvas uses Spring Social's ProviderSignInController
to obtain an access token and perform signin. While it works, it is not the proper way of obtaining an
access token in a Facebook canvas application. 

The proper approach is much simpler and does not follow any OAuth 2 flow. Instead, Facebook will
pass a signed_request parameter to the application's canvas URL in a POST request. When handing that
request, the application will decode the signed_request parameter and extract the access token. From
there, a connection can be created and signin can be performed. 

This sample is due to be updated to reflect the correct approach (see https://jira.springsource.org/browse/SOCIALFB-65).
Until then know that the better way of obtaining an access token in in a FB canvas application is to
use Spring Social Facebook's SignedRequestDecoder to extract the access token. We expect that when working
through SOCIALFB-65, new features will be created in Spring Social Facebook to address this problem directly.
Until then, you will need to write a custom Spring MVC controller to handle the canvas application case.

To run, import the project into your IDE and deploy to a Servlet 2.5 or > container such as Tomcat 6 or 7.
Access the project via Facebook at http://apps.facebook.com/springsocialcanvas.

Discuss at forum.springsource.org and collaborate with the development team at jira.springframework.org/browse/SOCIAL.