# AWS

- [Configuring region in Node.js AWS SDK](https://stackoverflow.com/questions/31039948/configuring-region-in-node-js-aws-sdk)

- [How do you use “NextToken” in AWS API calls](https://stackoverflow.com/questions/52068066/how-do-you-use-nexttoken-in-aws-api-calls)

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
