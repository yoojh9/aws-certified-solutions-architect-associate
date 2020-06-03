# WAF

## 1. WAF

### 1) What is WAF?
AWS WAF is a web application firewall that lets you monitor the HTTP and HTTPS requests that are forwarded to Amazon CloudFront, an Application Load Balancer or API Gateway.
AWS WAF also lets you cntrol access to your content.

You can configure conditions such as What IP addresses are allowed to make this request or what query string parameters need to be passed for the request to be allowed.
Then the application load balancer or CloudFront or API Gateway will either allow this content to be received or to give a HTTP 403 status Code.

AWS WAF는 Amazon CloudFront 배포, Amazon API Gateway API 또는 Application Load Balancer에 전달되는 HTTP(S) 요청을 모니터링할 수 있게 해주는 웹 애플리케이션 방화벽입니다.
또한 AWS WAF을 사용하여 콘텐츠에 대한 액세스를 제어할 수 있습니다. 요청이 허용되는 IP 주소나 쿼리 문자열의 값으로부터 지정하는 조건 등 지정하는 조건에 따라, Amazon CloudFront 배포, Amazon API Gateway API 또는 Application Load Balancer는 요청된 콘텐츠나 HTTP 403 상태 코드(금지됨)로 요청에 응답합니다. 또한 요청이 차단될 때 사용자 지정 오류 페이지를 반환하도록 CloudFront를 구성할 수 있습니다.

#### At its most basic level, AWS WAF allows 3 different behaviours:
 - Allow all requests except the ones you specify
 - Block all requests except the ones you specify
 - Count the requests that match the properties you specify

#### Extra protection against web attacks using conditions you specify. You can define conditions by using characteristics of web requests such as:
 - IP addresses that requests originate from.
 - Country that requests originate from.
 - Values in request header.
 - Strings that appear in requests, either specific strings or string that match regular expression(regex) patterns.
 - Legnth of requests.
 - Presence of SQL code that is likely to be malicious(Known as SQL injection)
 - Presence of script that is likely to be malicious(Known as cross-site scripting)

#### In the exam you will be given different scenarios and you will be asked how to block malicious IP address.
 - Use AWS WAF
 - Use Network ACLS