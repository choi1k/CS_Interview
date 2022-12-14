# Redis

In-Memory DB

Redis는 고성능 key-value 저장소로 문자열, 리스트, 해시, 셋, 정렬 셋 형식의 데이터를 지원하는 NoSQL임

### Redis란?

Redis는 Memcached와 유사한 캐시 시스템으로 영속성, 다양한 데이터 구조 등 부가적 기능을 지원함

모든 데이터를 메모리에 저장하므로 하드 디스크에 메모리를 저장할 떄 발생하는 디스크 스캐닝 과정이 없어\
 속도가 매우 빠른 것이 특징임

 다양한 자료구조를 지원하기 때문에 개발의 편의성은 높아지고 난이도는 낮아짐

### Redis 영속성
Redis는 영속성을 보장하기 위해 데이터를 디스크에 저장할 수 있음

서버가 다운돼도 디스크에 저장된 데이터를 읽어 메모리에 로딩함

    RDB(Snapshotting) 방식

        순간적으로 메모리에 있는 내용 전체를 디스크에 옮겨 담는 방식

    AOF(Append On File) 방식

        Redis의 모든 write/update 연산을 로그 파일에 기록하는 형태