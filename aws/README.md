# [AWS](https://aws.amazon.com/ko/)

- [Amazon 리소스 이름(ARN)](https://docs.aws.amazon.com/ko_kr/general/latest/gr/aws-arns-and-namespaces.html)
- [AWS 서비스 엔드포인트](https://docs.aws.amazon.com/ko_kr/general/latest/gr/rande.html)
- [AWS에서 보안 감사 및 이상징후 탐지](https://woowabros.github.io/security/2019/01/18/aws-cloudtrail-security.html)



## Amazon Web Services 한국 블로그

- [Amazon CloudFront를 활용한 동적 콘텐츠 전송 성능 개선하기](https://aws.amazon.com/ko/blogs/korea/how-to-improve-dynamic-contents-delievery-using-amazon-cloudfront/)
- [Amazon CloudFront와 AWS Media Services를 활용한 콘텐츠 전송 방법](https://aws.amazon.com/ko/blogs/korea/using-amazon-cloudfront-and-aws-media-services/)
- [Category: AWS Elemental MediaLive](https://aws.amazon.com/ko/blogs/korea/category/media-services/aws-elemental-medialive/)
- [클라우드 기반 미디어 생방송 품질 최적화 및 개선 방법 – 1) 지연 시간의 정의와 측정](https://aws.amazon.com/ko/blogs/korea/part-1-how-to-compete-with-broadcast-latency-using-current-adaptive-bitrate-technologies/?nc1=b_rp)



## [AWS Media Blog](https://aws.amazon.com/ko/blogs/media/)

- [Part 1: How to Compete with Broadcast Latency Using Current Adaptive Bitrate Technologies](https://aws.amazon.com/ko/blogs/media/how-to-compete-with-broadcast-latency-using-current-adaptive-bitrate-technologies-part-1/)



### [CloudWatch]()

- [채널 로그 활성화](https://docs.aws.amazon.com/ko_kr/medialive/latest/ug/enabling-disabling-logs.html)
- [CloudWatch 메트릭 그래프 스냅샷 만들기](https://brunch.co.kr/@alden/53)
- [10. AWS 서비스를 모니터링하는 CloudWatch](https://interconnection.tistory.com/48)



## Config

- [글로벌 구성 객체 사용하기](https://docs.aws.amazon.com/ko_kr/sdk-for-javascript/v2/developer-guide/global-config-object.html)



## IAM

- [IAM 정책을 잘 알아야 AWS 보안도 쉬워진다. 이것은 꼭 알고 가자! - 신은수 솔루션즈 아키텍트, AWS :: AWS Summit Seoul 2019](https://www.slideshare.net/awskorea/iam-aws-aws-aws-summit-seoul-2019)



### [S3]()

- [[AWS 파헤치기] #4 S3 권한설정 ACL & Bucket Policy](https://real-dongsoo7.tistory.com/101)
- [Amazon Simple Storage Service 엔드포인트 및 할당량](https://docs.aws.amazon.com/ko_kr/general/latest/gr/s3.html)
- [AWS S3 vs Elemental MediaStore](https://stackoverflow.com/questions/53005213/aws-s3-vs-elemental-mediastore)
- [Create an S3 Bucket for File Uploads](https://serverless-stack.com/chapters/ko/create-an-s3-bucket-for-file-uploads.html)
- [S3 bucket policy has invalid action](https://stackoverflow.com/questions/46212531/s3-bucket-policy-has-invalid-action)


## [AWS Media Services](https://aws.amazon.com/ko/media-services/?nc1=h_ls)

- [워크플로우 기반의 AWS 미디어서비스 활용하기::이상오::AWS Summit Seoul 2018](https://www.slideshare.net/awskorea/workflow-foundation-aws-media-services-introduction-leesangho-95052558)



### [MediaLive](https://aws.amazon.com/ko/medialive/)

- [[Reinvent2017] 주요 서비스 업데이트 - 미디어 분야(AWS Elemental MediaLive)](https://wisen.co.kr/pages/blog/blog-detail.html?idx=2325)
- [AWS Elemental MediaLive](https://blog.leedoing.com/110)
- [AWS MediaLive MediaPackage - How to store realtime streaming videos to S3?](https://stackoverflow.com/questions/52900656/aws-medialive-mediapackage-how-to-store-realtime-streaming-videos-to-s3)
- [MediaLive 두개의 출력을 MediaStore에서 완벽한 이중화 하기 (Redundant Manifest)](https://m.blog.naver.com/PostView.nhn?blogId=tomnet&logNo=221414251940&proxyReferer=https%3A%2F%2Fwww.google.com%2F)



### [MediaStore](https://aws.amazon.com/ko/mediastore/)

- [AWS MediaStore](https://blog.leedoing.com/154)
- [Monitor Performance with AWS Elemental MediaStore HTTP Access Logs](https://aws.amazon.com/ko/blogs/media/monitor-performance-with-mediastore-http-access-logs/)



## References

- [Configuring region in Node.js AWS SDK](https://stackoverflow.com/questions/31039948/configuring-region-in-node-js-aws-sdk)
- [How do you use “NextToken” in AWS API calls](https://stackoverflow.com/questions/52068066/how-do-you-use-nexttoken-in-aws-api-calls)
- [How to use AWS Media Services for media projects](https://www.cleveroad.com/blog/aws-media-services)
- [OBS Studio Streaming](https://forums.aws.amazon.com/thread.jspa?threadID=268535)
- [デフォルトのCloudFront設定](https://qiita.com/motchi0214/items/bf7a2d3f334b7b1b0a53)

cf. cloudfront-default.json

```js
{
  ETag: '{CLOUDFRONT_DESTRIBUTION_ID}',
  DistributionConfig: {
    CallerReference: '1471603622154',
    Aliases: {
      Quantity: 0,
      Items: []
    },
    DefaultRootObject: '',
    Origins: {
      Quantity: 1,
      Items: [{
        Id: 'Custom-{YOUR_BUCKET_NAME}.s3-website-{S3_REGION}.amazonaws.com/',
        DomainName: '{YOUR_BUCKET_NAME}.s3-website-{S3_REGION}.amazonaws.com',
        OriginPath: '/',
        CustomHeaders: {
          Quantity: 0,
          Items: []
        },
        CustomOriginConfig: {
          HTTPPort: 80,
          HTTPSPort: 443,
          OriginProtocolPolicy: 'http-only',
          OriginSslProtocols: {
            Quantity: 3,
            Items: ['TLSv1', 'TLSv1.1', 'TLSv1.2']
          }
        }
      }]
    },
    DefaultCacheBehavior: {
      TargetOriginId: 'Custom-{YOUR_BUCKET_NAME}.s3-website-{S3_REGION}.amazonaws.com/',
      ForwardedValues: {
        QueryString: false,
        Cookies: { Forward: 'none' },
        Headers: { Quantity: 0, Items: [] }
      },
      TrustedSigners: {
        Enabled: false,
        Quantity: 0,
        Items: []
      },
      ViewerProtocolPolicy: 'allow-all',
      MinTTL: 0,
      AllowedMethods: {
        Quantity: 2,
        Items: ['HEAD', 'GET'],
        CachedMethods: {
          Quantity: 2,
          Items: ['HEAD', 'GET']
        }
      },
      SmoothStreaming: false,
      DefaultTTL: 86400,
      MaxTTL: 31536000,
      Compress: false
    },
    CacheBehaviors: { Quantity: 0, Items: [] },
    CustomErrorResponses: { Quantity: 0, Items: [] },
    Comment: '',
    Logging: {
      Enabled: false,
      IncludeCookies: false,
      Bucket: '',
      Prefix: ''
    },
    PriceClass: 'PriceClass_All',
    Enabled: true,
    ViewerCertificate: {
      CloudFrontDefaultCertificate: true,
      MinimumProtocolVersion: 'SSLv3',
      CertificateSource: 'cloudfront'
    },
    Restrictions: {
      GeoRestriction: {
        RestrictionType: 'none',
        Quantity: 0,
        Items: []
      }
    },
    WebACLId: ''
  }
}
```



### Effective

- [[AWS] S3 객체 업로드 및 액세스 설정](https://zamezzz.tistory.com/299)



### Aws::CloudFront::Errors::NoSuchOrigin: One or more of your origins do not exist.

- [Aws::CloudFront::Errors::NoSuchOrigin: One or more of your origins do not exist](https://forums.aws.amazon.com/message.jspa?messageID=694708)
- [Error: ENOENT: no such file or directory, open '../config.json'](https://stackoverflow.com/questions/51921605/error-enoent-no-such-file-or-directory-open-config-json)
- [Node.js and aws credentials error](https://stackoverflow.com/questions/37507464/node-js-and-aws-credentials-error)
- [Solving ‘One or more of your origins do not exist’ for Cloud Front](https://maxrohde.com/2016/11/15/solving-one-or-more-of-your-origins-do-not-exist-for-cloud-front/)
- [Using CloudFormation to configure CloudFront with an S3 origin](https://stackoverflow.com/questions/35851374/using-cloudformation-to-configure-cloudfront-with-an-s3-origin)
