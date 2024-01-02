# Spring으로 만드는 메모장 서비스
Spring을 이용한 메모장 서비스 개발을 목표로, REST API를 활용하여 기본적인 CRUD 기능을 구현

## 메모장 프로젝트 설계
- 프로젝트 상황
- 메모장 기능 설계
    1. 전송 하지마자 메모 전체 목록 조회하기
       a. GET API 사용해서 메모 목록 불러오기
    2. 메모 생성하기
       a. POST API 사용해서 메모 신규 생성하기
       b. 생성된 메모 반환
    3. 메모 변경하기
       a. PUT API 사용해서 메모 내용 변경하기
       b. 사용자가 클릭한 메모가 DB에 존재하는지 확인하기
       c. 해당 메모 내용 변경
    4. 메모 삭제하기
       a. DELETE API 사용해서 메모 삭제하기
       b. 사용자가 삭제하려는 메모가 DB에 존재하는지 확인하기
       c. DB에서 해당 메모 삭제

## 생성한 API 테이블
| 기능        | Method | URL            | Return                 |
|-------------|--------|----------------|------------------------|
| 메모 생성하기 | POST   | /api/memos     | MemoResponseDto        |
| 메모 조회하기 | GET    | /api/memos     | List<MemoResponseDto>  |
| 메모 변경하기 | PUT    | /api/memos/{id}| Long                   |
| 메모 삭제하기 | DELETE | /api/memos/{id}| Long                   |


## DTO: Data Transfer Object
데이터 전송 및 이동을 위해 생성된 객체 <br/><br/>
[용도]
1. Client에서 보내오는 데이터를 객체로 처리할 떄 사용
2. 서버의 계층간 이동에도 사용
3. DB와의 소통을 담당하는 Java Class를 그대로 Client에 반환하는게 아니라 DTO로 한번 변환한 후 반환할 때도 사용