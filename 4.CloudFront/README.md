# CloudFront

## 1. What is CloudFront?

A content delivery network(CDN) is a system of distributed servers(network) that deliver webpages and other web content to a user base on the geographic locations of the user, the origin of the webpage, and a content delivery server.

Amazon CloudFront는 개발자 친화적 환경에서 짧은 지연 시간과 빠른 전송 속도로 데이터, 동영상, 애플리케이션 및 API를 전 세계 고객에게 안전하게 전송하는 고속 콘텐츠 전송 네트워크(CDN) 서비스이다.
Amazon CloudFront는 .html, .css, .js 및 이미지 파일과 같은 정적 및 동적 웹 콘텐츠를 사용자에게 더 빨리 배포하도록 지원하는 웹서비스이다.
CloudFront는 엣지 로케이션이라고 하는 데이터 센터의 전 세계 네트워크를 통해 콘텐츠를 제공한다. CloudFront를 통해 서비스하는 콘텐츠를 사용자가 요청하면 지연 시간이 가장 낮은 엣지 로케이션이 라우팅되므로 콘텐츠 전송 성능이 뛰어나다

애플리케이션 오리진으로서 Amazon S3, Elastic Load Balancing 또는 Amazon EC2를 사용하고, Lambda@Edge와 연동되어 사용자지정 코드를 고객의 사용자에서 가까운 위치에서 실행하고 맞춤화된 사용자 경험을 제공한다. Amazon S3, Amazon EC2 또는 Elastic Load Balancing과 같은 AWS 오리진을 사용하는 경우, 이러한 서비스와 CloudFront 간에 전송된 데이터에 대해서는 비용을 지불하지 않는다.

- 컨텐츠가 이미 지연 시간이 가장 낮은 엣지에 있는 경우 CloudFront가 콘텐츠를 즉시 제공한다
- 컨텐츠가 엣지 로케이션에 없는 경우 CloudFront는 컨텐츠의 최종 버전에 대한 소스로 지정된 오리진 - 예: Amazon S3 버킷, MediaPackage 채널, HTTP 서버(예: 웹서버) 등에서 컨텐츠를 검색한다

CloudFront는 AWS 백본 네트워크를 통해 컨텐츠를 효과적으로 서비스할 수 있는 엣지로 각 사용자 요청을 라우팅하여 컨텐츠 배포 속도를 높인다. 일반적으로 CloudFront 엣지가 최종 사용자에게 가장 빨리 제공한다. AWS 네트워크를 사용하면 사용자의 요청이 반드시 통과해야 하는 네트워크의 수가 줄어들어 성능이 향상되며 파일의 첫 바이트를 로드하는 데 걸리는 지연 시간이 줄어들고 데이터 전송 속도가 빨라진다.
또한 파일(객체라고도 함)의 사본이 전 세계 여러 엣지 로케이션에 유지(또는 캐시)되므로 안정성과 가용성이 향상된댜.

## 2. Key Terminology

- **Edge Location** : This is the location where content will be cached. This is seperate to an AWS Region/AZ.
- **Origin** : This is the origin of all the files that the CDN will distribute. This can be an S3 bucket, an EC2 intance, an Elastic Load Balancer, or Route53
- **Distribution** : This is the name given the CDN which consists of a collection of Edge Locations.

Amazon CloudFront can be used to deliver your entire website, including dynamic, static, streaming, and interactive content using a global network of edge locations.
Requests for your content are automatically routed to the nearest edge location, so content is delivered with the best possible performance.

- Edge locations are not just READ only - you can write to them too. (ie. put an object on to them.)
- Objects are cached for the life of the TTL(Time To Live)
- You can clear cached objects, but you will be charged.

## 3. 사용 사례

- **Web Distribution** : Typically used for Websites.
- **RTMP** : Used for Media Streaming
