# CloudFront

## 1. What is CloudFront?
A content delivery network(CDN) is a system of distributed servers(network) that deliver webpages and other web content to a user base on the geographic locations of the user, the origin of the webpage, and a content delivery server.

Amazon CloudFront는 .html, .css, .js 및 이미지 파일과 같은 정적 및 동적 웹 콘텐츠를 사용자에게 더 빨리 배포하도록 지원하는 웹서비스이다. 
CloudFront는 엣지 로케이션이라고 하는 데이터 센터의 전 세계 네트워크를 통해 콘텐츠를 제공한다. CloudFront를 통해 서비스하는 콘텐츠를 사용자가 요청하면 지연 시간이 가장 낮은 엣지 로케이션이 라우팅되므로 콘텐츠 전송 성능이 뛰어나다
 
 - 컨텐츠가 이미 지연 시간이 가장 낮은 엣지에 있는 경우 CloudFront가 콘텐츠를 즉시 제공한다
 - 컨텐츠가 엣지 로케이션에 없는 경우 CloudFront는 컨텐츠의 최종 버전에 대한 소스로 지정된 오리진 - 예: Amazon S3 버킷, MediaPackage 채널, HTTP 서버(예: 웹서버) 등에서 컨텐츠를 검색한다

 CloudFront는 AWS 백본 네트워크를 통해 컨텐츠를 효과적으로 서비스할 수 있는 엣지로 각 사용자 요청을 라우팅하여 컨텐츠 배포 속도를 높인다. 일반적으로 CloudFront 엣지가 최종 사용자에게 가장 빨리 제공한다. AWS 네트워크를 사용하면 사용자의 요청이 반드시 통과해야 하는 네트워크의 수가 줄어들어 성능이 향상되며 파일의 첫 바이트를 로드하는 데 걸리는 지연 시간이 줄어들고 데이터 전송 속도가 빨라진다.
 또한 파일(객체라고도 함)의 사본이 전 세계 여러 엣지 로케이션에 유지(또는 캐시)되므로 안정성과 가용성이 향상된댜.