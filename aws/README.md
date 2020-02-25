# [AWS](https://aws.amazon.com/ko/)

## [AWS Media Services](https://aws.amazon.com/ko/media-services/?nc1=h_ls)

### [MediaStore](https://aws.amazon.com/ko/mediastore/)

### [MediaLive](https://aws.amazon.com/ko/medialive/)



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

### Aws::CloudFront::Errors::NoSuchOrigin: One or more of your origins do not exist.

- [Aws::CloudFront::Errors::NoSuchOrigin: One or more of your origins do not exist](https://forums.aws.amazon.com/message.jspa?messageID=694708)
- [Error: ENOENT: no such file or directory, open '../config.json'](https://stackoverflow.com/questions/51921605/error-enoent-no-such-file-or-directory-open-config-json)
- [Node.js and aws credentials error](https://stackoverflow.com/questions/37507464/node-js-and-aws-credentials-error)
- [Solving ‘One or more of your origins do not exist’ for Cloud Front](https://maxrohde.com/2016/11/15/solving-one-or-more-of-your-origins-do-not-exist-for-cloud-front/)
- [Using CloudFormation to configure CloudFront with an S3 origin](https://stackoverflow.com/questions/35851374/using-cloudformation-to-configure-cloudfront-with-an-s3-origin)
