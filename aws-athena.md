# AWS Athena

**Athena 개념**
- ANSI SQL를 사용하여 Amazon S3에 있는 데이터를 직접 간편하게 분석할 수 있는 대화형 쿼리 서비스
> **ANSI SQL**  
  DBMS 특성에 따라 SQL이 다르므로 미국 표준협회(American National Standards Institute)에서 이를 표준화하여 표준 SQL문을 정립 시켜놓은 것
  
**Athena 특징**
1. 관리해야 하는 클러스터, 설정하거나 관리할 인프라가 없는 서버리스 형태 (Serverless)로 복잡한 ELT 설정 없이 사용 가능
2. 별다른 설치 없이 AWS Console에 접속하여 편리하게 사용
3. 쿼리를 병렬로 실행하여 대규모 데이터 집합과 복잡한 쿼리에서도 빠르게 결과를 얻을 수 있음
4. Amazon S3에 있는 데이터를 로딩하거나 변환시킬 필요 없이 직접 쿼리 실행 가능
5. 데이터가 파티션 단위로 나뉘어 있기 때문에 실시간 조회 불가능

**Athena 쿼리**
- 관계형, 비관계형, 객체 및 사용자 지정 데이터 원본에 저장된 데이터에 대해 SQL 쿼리 실행
- 익숙한 SQL 구문을 사용하여 여러 데이터 원본의 데이터를 결합하여 빠른 분석을 수행하고, 후속 사용을 위해 Amazon S3에 결과 저장
- complex joins, nested queries 지원
- 데이터를 파티셔닝하면 각 쿼리가 스캔하는 데이터의 양을 제한하여 성능을 향상시키고 비용 절감
> **데이터 파티셔닝**  
  용량이 큰 테이블이나 인덱스를 관리하기 쉬운 파티션(partition)이라는 작은 단위로 분할하는 것

**Athena 비용**
- Amazon Athena는 실행한 쿼리에 대한 비용만 지불
- 각 쿼리에서 스캔한 데이터 양에 따라 요금 부과
- DDL 쿼리를 실행하거나 쿼리 실행이 실패 시 요금을 지불하지 않음
- 데이터를 압축 또는 파티셔닝하거나 컬럼 형식으로 변환하면 스캔해야 하는 데이터 양이 감소하므로 비용이 절감됨

**테이블 생성**
```
  CREATE EXTERNAL TABLE point_log (
    type STRING,
    owner STRING,
    requestId STRING,
    timestamp BIGINT,
    yearMonth DATE,
    increase INT,
    total INT,
    point INT,
    remain Int
  ) PARTITIONED BY (type STRING, owner STRING, requestId STRING, timestamp BIGINT, yearMonth DATE)
  LOCATION 's3://bucket_name/[folder]/'
```
