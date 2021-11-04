# AWS Athena

**AWS Athena 개념**
- ANSI SQL를 사용하여 Amazon S3에 있는 데이터를 직접 간편하게 분석할 수 있는 대화형 쿼리 서비스
- 설정하거나 관리할 인프라가 없는 서버리스(Serverless) 서비스로 실행한 쿼리의 비용만 지불하면 됨
- 쿼리를 병렬로 실행하여 대규모 데이터 집합과 복잡한 쿼리에서도 빠르게 결과를 얻을 수 있음
> ANSI SQL  
  DBMS(Oracle, MySQL 등)들이 각기 다른 SQL을 사용하므로, 미국 표준협회(American National Standards Institute)에서 이를 표준화하여 표준 SQL문을 정립 시켜놓은 것
    
**AWS Athena 데이터 수집**
**AWS Athena 데이터 보관**
**AWS Athena 데이터 조회(파티셔닝)**

**AWS Athena 비용**
- Amazon Athena는 실행한 쿼리에 대한 비용만 지불
- 각 쿼리에서 스캔한 데이터 양에 따라 요금 부과
- 데이터를 압축 또는 파티셔닝하거나 컬럼 형식으로 변환하면 스캔해야 하는 데이터 양이 감소하므로 비용이 절감됨
