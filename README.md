# AWS-IAM-Roles-Anywhere-AWS-Certificate-Manager

AWS IAM Roles Anywhere はオンプレミス等AWSリソース以外からのリクエストに対しいて一時クレデンシャル（STSトークン）を発行するための新しい仕組みを提供します。STSトークンの仕組みについては以下を参照してください。
https://docs.aws.amazon.com/ja_jp/IAM/latest/UserGuide/id_credentials_temp.html

AWS IAM Roles Anywhereでは、PKIの仕組みを用いて、認証局から発行された正当な電子証明書を保有しているクライアントから、電子署名付きのリクエストがあった場合、AWS IAM側でその署名検証が行われSTSトークンが発行される仕組みです。またCRL (Certificate Revocation List)と連携することで、認証局側で破棄した電子証明書からのリクエストを不正なものとして取り扱うことが可能です。

このシナリオでは、認証局にAWS Certificate Manager PCA (Private Certificte Authority)を用いています。

