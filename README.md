# SpringH2DBExample

` mvn spring-boot:run `

- pom.xml

```
		<dependency>
			<groupId>com.h2database</groupId>
			<artifactId>h2</artifactId>
			<scope>runtime</scope>
		</dependency>
```



- application.properties

```
#DataSource
spring.datasource.url=jdbc:h2:mem:testdb;DB_CLOSE_DELAY=-1;DB_CLOSE_ON_EXIT=FALSE
spring.datasource.driver-class-name=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.sql.init.encoding=UTF-8 
spring.datasource.initialize=true 
spring.sql.init.schema-locations=classpath:schema.sql 
spring.sql.init.data-locations=classpath:data.sql 

#H2DB 
spring.h2.console.enabled=true
```


- DB_CLOSE_DELAY=-1： H2の接続が切れてもデータベースをドロップしなくなる
- DB_CLOSE_ON_EXIT=FALSE： VM終了時の自動データベースクローズを無効にする
- spring.datasource.initialize=true： テーブル作成とデータ投入のSQLを実行する
- spring.sql.init.schema-locations： テーブル作成のSQLを実行する
- spring.sql.init.data-locations： 初期データ投入のSQLを実行する
- classpath： 「src/main/resources」のこと、schema, data.sqlは「resources」直下に設置
- spring.h2.console.enabled=true： http://localhost:8080/h2-console にアクセスしてコンソールを利用できる
