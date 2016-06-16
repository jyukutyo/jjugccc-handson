https://github.com/making/jjugccc-handson を2016/06現在のバージョンで書き直したものです。

|変更前バージョン|変更後バージョン|
|-----------|------------|
|Spring Boot 1.1.8.RELEASE|Spring Boot 1.3.5.RELEASE|
|spring-cloud-starters 1.0.0.M2|spring-cloud-starter-parent Brixton.SR1|

## 詰まった点
### configserver
configserver/src/main/resources/bootstrap.ymlにあるGitリポジトリの場所を見に行かなかったのでconfigserver.ymlのにリネームしました。
またymlの内容も`spring.cloud.config.server.uri`から`spring.cloud.config.server.git.uri`に変更しました。
### urlshorter-ui
`RemoteCommand`クラスの`RestTemplate`オブジェクトがAutoWiredできず`BeanCreationException`となるため、JavaConfigで`RestTemplate`オブジェクトをコンテナ管理させるようにしました。
