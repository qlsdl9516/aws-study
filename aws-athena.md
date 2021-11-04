# AWS Athena

**Athena 개념**
- ANSI SQL를 사용하여 Amazon S3에 있는 데이터를 직접 간편하게 분석할 수 있는 대화형 쿼리 서비스
> ANSI SQL  
  DBMS(Oracle, MySQL 등)들이 각기 다른 SQL을 사용하므로, 미국 표준협회(American National Standards Institute)에서 이를 표준화하여 표준 SQL문을 정립 시켜놓은 것
  
**Athena 특징**
1. 관리해야 하는 클러스터, 설정하거나 관리할 인프라가 없는 서버리스 형태 (Serverless)
2. 별다른 설치 없이 AWS Console에 접속하여 편리하게 사용
3. AWS에서 관리형 서비스로 제공하기 때문에 고가용성임
4. 쿼리를 병렬로 실행하여 대규모 데이터 집합과 복잡한 쿼리에서도 빠르게 결과를 얻을 수 있음

**AWS Athena 데이터 보관**
- Amazon S3에 있는 데이터를 로딩하거나 변환시킬 필요 없이 직접 쿼리 실행 가능

**AWS Athena 데이터 조회**
- ANSI SQL을 사용하여 데이터 분석
- complex joins, nested queries 지원
- 데이터 파티셔닝(date, time ,custom keys 등) 지원 

**AWS Athena 비용**
- Amazon Athena는 실행한 쿼리에 대한 비용만 지불
- 각 쿼리에서 스캔한 데이터 양에 따라 요금 부과
- DDL 쿼리를 실행하거나 쿼리 실행이 실패 시 요금을 지불하지 않음
- 데이터를 압축 또는 파티셔닝하거나 컬럼 형식으로 변환하면 스캔해야 하는 데이터 양이 감소하므로 비용이 절감됨
