# Snowball

## 1. What is Snowball?
Snowball is a petabyte-scale data transport solution that uses secure appliances to transfer large amounts of data into and out of AWS.
Using Snowball addresses common chanllenges with large-scale data transfers including high network costs, long transfer times, and security concerns.
Trnasferring data with Snowball is simple, fast, secure, and can be as little as one-fifth the cost of high-speed internet.

Snowball comes in either a 50TB or 80TB size. Snowball uses multiple layers of security designed to protect your data including tamper-resistant enclosures, 256-bit encryption, and an industry-standard Trusted Platform Module(TPM) designed to ensure both security and full chain-of-custody of your data. once the data transfer jo has been processed and verified, AWS performs a software erasure of the Snowball appliance.

AWS Snowball 서비스는 물리적 스토리지 디바이스를 사용하여 인터넷보다 빠른 속도로 Amazon Simple Storage Service(Amazon S3)와 온사이트 데이터 스토리지 위치 간에 대량 데이터를 전송한다. AWS Snowball으로 작업하면 시간과 비용을 절약할 수 있다. Snowball은 작업을 생성하고 데이터를 추적하고 완료까지 전 과정의 작업 상태를 추적하는 데 사용할 수 있는 강력한 인터페이스를 제공한다. Snowball 디바이스는 AWS Key Management Service(AWS KMS)로 보호되는 물리적으로 견고한 디바이스이다. 이 디바이스는 전송 중 데이터를 안전하게 보호한다.

AWS Snowball은 AWS 컴퓨팅 및 스토리지 기능을 엣지 환경으로 가져오고 AWS와 데이터를 주고 받을 수 있도록, 안전하고 견고한 디바이스를 제공하는 서비스이다. 이 견고한 디바이스를 보통 AWS Snowball 또는 AWS Snowball Edge 디바이스라고 한다. 이전에는 이러한 디바이스의 초기 하드웨어 버전을 AWS Snowball이라고 했으며 해당 모델은 이제 업데이트된 하드웨어로 대체되었다. 이제 AWS Snowball 서비스는 온보드 컴퓨팅 기능과 스토리지를 모두 갖춘 Snowball Edge 디바이스를 사용한다.

## 2. What is Snowball Edge?
AWS Snowball Edge is a 100TB data transfer device with on-board storage and compute capabilities. You can use Snowball Edge to move large amounts of data into and out of AWS, as a temporary storage tier for large local datasets, or to support local workloads in remote or offline locations.
Snowball Edge connects to your existing applications and infrastucture using standard storage interfaces, streamlining the data transfer process and minimizing setup and integration. Snowball Edge can cluster togetherto form a local storage tier and process your data on-premises, helping ensure your applications continue to run even when they are not able to access the cloud

AWS Snowball Edge는 엄선된 AWS 기능을 구현하기 위해 온보드 스토리지 및 컴퓨팅 파워를 갖춘 Snowball 디바이스 유형이다. Snowball Edge는 로컬 환경과 AWS 클라우드 사이에서 데이터를 전송하는 것 외에도 로컬 처리 및 엣지 컴퓨터 워크로드를 처리할 수 있다. 각 Snowball Edge 디바이스는 인터넷보다 더 빠른 속도로 데이터를 전송할 수 있다. 이 전송은 리전 운송업체를 통해 어플라이언스의 데이터를 운송하여 이루어진다. 어플라이언스는 견고한 운송 컨테이너로서 전자 잉크 배송 라벨이 붙어있다.

Snowball Edge는 AWS Snowball 서비스에서 제공하는 엣지 컴퓨팅 및 데이터 전송 디바이스이다. 이 디바이스는 특정 AWS 서비스가 엣지 로케이션에서 사용할 수 있는 온보드 스토리지와 컴퓨팅 성능을 탑재하고 있다. Snowball Edge는 선박, 풍력 발전기 및 원격 공장과 같이 외진 환경에서의 로컬 데이터 프로세싱 및 수집을 지원하기 위해 Storage Optimized 및 Compute Optimized의 두 가지 옵션으로 제공된다

## 3. What is Snowmobile?
AWS Snowmobile is an Exabyte-scale data transfer service used to move extemely large amounts of data to AWS. You can transfer up to 100PB per Snowmobile, a 45-foot-long ruggedized shipping container, pulled by a semi-trailer truck. Snowmobile makes it easy to move massive volumes of data to the cloud, including video libraries, image repositories, or even a complete data center migration. Transferring data with Snowmobile is secure, fast and cost effective.

AWS Snowmobile은 초대용량 데이터 세트를 온프레미스에서 AWS로 이전할 수 있는 첫 번째 엑사바이트 규모의 데이터 마이그레이션 서비스이다. 각 Snowmobile은 고객 사이트로 보내서 고객 네트워크 백본에 직접 연결하여 고속 데이터 마이그레이션을 수행할 수 있는 안전한 데이터 트럭으로 최대 100PB 스토리지 용량을 지원한다. 단일 위치 또는 여러 데이터 센터에서 병렬로 10개의 Snowmobile을 사용해 엑사바이트의 데이터를 신속하게 마이그레이션할 수 있다. Snowmobile은 AWS에서 관리형 서비스로 제공된다.

https://aws.amazon.com/ko/snowmobile/faqs/

## 4. Snowball Edge와 Snowball의 차이점은?
AWS Snowball은 이제 서비스 전체를 가리키며 Snowball Edge는 이 서비스가 사용하는 최신 디바이스 유형을 가리킨다. 때로는 Snowball Edge를 AWS Snowball 디바이스로 통칭하기도 한다. 초기 Snowball 하드웨어 디자인은 데이터 전송용으로만 사용되었다. Snowball Edge에는 네트워크 연결을 사용할 수 없는 경우에도 로컬로 컴퓨팅을 수행할 수 있는 추가 기능이 탑재되어 있다.

