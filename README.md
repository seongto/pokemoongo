# 포켓문고 (POKEMOONGO)
![포켓문고](https://github.com/user-attachments/assets/39dc627a-c264-43f0-a4d0-423be6690354)

## 1. 프로젝트 개요

- **프로젝트명** : 포켓문고 (PokeMoonGo)
- **프로젝트 기간** : 2024.12.26 - 2025.01.06
- github: https://github.com/seongto/book-store
- **프로젝트 설명**
    - 내가 입력한 키워드로 책을 검색하고, 책에 대한 정보를 볼 수 있습니다.
    - 선택한 책을 담아두고 나중에 손쉽게 확인할 수 있어요.
    - 책을 보다보면 랜덤하게 몬스터볼을 얻을 수 있습니다.
    - 얻은 몬스터볼로 포켓몬을 잡을 수 있어요!
    - Advanced + Challenge 과제를 모두 수행하는 것을 목표로 한다.
- **프로젝트 플로우**
    - Figma로 기본적인 에셋 디자인 후 이를 코드로 컴포넌트화 하여 프로젝트에 적용
    - 추후 다른 프로젝트에서 재활용 가능한 코드들을 라이브러리로 분리
- **개발 목표 및 기술 스택**
    
    
    | **구분** | **세부 사항** |
    | --- | --- |
    | **개발 아키텍처** | MVVM + Coordinator, UseCase, Repository |
    | **데이터 관리** | CoreData 및 UserDefaults를 통한 데이터 관리 |
    | **네트워크 통신** | Alamofire 사용 |
    | **UI 개발** | UIKit, AutoLayout, SnapKit, RxSwift, KingFisher, CompositionalLayout |
    | **코드 관리** | Git 사용, `develop` 브랜치에서 기능별 `feature/*`로 작업 후 머지 |

<br/><br/><br/>
---

## 2. 기능 구현 목표

- Level 1 : 각각의 화면 생성 및 연결 구현. 각 화면의 컨텐츠는 다음 레벨.
    - [ ]  `UITabBarController` 를 사용하여 탭 구현.
    - [ ]  검색 UI와 최근 본 책, 검색 결과 등이 포함된 메인화면
    - [ ]  책을 선택했을 경우 보여주는 책 상세 정보 화면
    - [ ]  담기를 통해 만들어진 담은 책 리스트를 보여주는 화면
   
     **+ 챌린지 과제**
    
    - [ ]  `NetworkManager` 구현
        - 싱글톤 패턴을 사용.
        - 다음의 형태를 만족하는 메서드 작성 : **`func** fetch<T: Decodable>(url: URL) -> Single<T>`

- Level 2 : 책 검색 화면 구현
    - [ ]  서치바를 이용한 책 검색 UI 구현
    - [ ]  검색 이후 검색 결과를 리스트로 구현 : **CompositionalLayout**
    - [ ]  카카오 책 검색 REST API를 이용하여책 정보 가져오기
    - [ ]  xcconfig를 활용한 환경변수 관리 도입
    
     **+ 챌린지 과제**
    
    - [ ]  `NetworkManager` 에 `limit` 개씩 `offset` 부터 ****포켓몬 정보 가져오는 API 추가하기
    - [ ]  포켓몬 번호로부터 포켓몬 디테일 정보 로드하는 API추가하기

- Level 3 : 책 상세 보기 & 담기 기능 구현
    - [ ]  책의 상세 정보 보여주기 : `title, authors, contents, thumbnail` 등
    - [ ]  담기 기능 구현 : 담기 성공 시 알람창으로 알려주기
    - [ ]  닫기 기능 구현
    - [ ]  책 설명 스크롤 기능
    - [ ]  담은 책 목록은 앱 종료시에도 유지
    - [ ]  스와이프 방식으로 각 항목 삭제 기능 구현
    - [ ]  추가버튼을 누를 경우 서치바로 바로 이동 및 포커스.
    
     **+ 챌린지 과제**
    
    - [ ]  RxSwift를 활용하여 위의 기능 구현하기

- Level 4 : 최근 본 책 기능 구현
    - [ ]  최근 본 책 10개의 목록을 보여준다.
    - [ ]  섹션 기능을 활용하여 기존 검색 결과와 섹션으로만 구분 된 하나의 컬렉션뷰로 구현
    - [ ]  최근 본 책이 없으면 섹션 노출하지 않음.
    - [ ]  최근 본 책 탭 시에도 책 상세화면 보여주기.
    - [ ]  최근 본 책은 중복을 허용하지 않는다.
    
    **+ 챌린지 과제**
    
    - [ ]  포켓몬스터 리스트를 담고 있는 뷰컨트롤러 구현하고 탭바에 추가하기

- Level 5 : 무한 스크롤 + MVVM
    - [ ]  검색 결과를 무한 스크롤로 구현한다.
    - [ ]  MVVM으로 프로젝트를 만든다.
    
    **+ 챌린지 과제**
    
    - [ ]  포켓몬의 디테일 화면을 보여주는 뷰 컨트롤러를 만들어 포켓몬 목록 중 선택 시 화면 전환 기능 구현

<br/><br/><br/>

![hard mode](https://staticdelivery.nexusmods.com/mods/5113/images/headers/229_1676449560.jpg)

<br/>

- Level 6
    
    **+ 챌린지 과제**
    
    - [ ]  RxSwift, ViewModel을 활용하여 선택한 포켓몬에 대한 데이터를 가져오는 기능 구현

- Level 7
    
    **+ 챌린지 과제**
    
    - [ ]  가져온 포켓몬 데이터로 포켓몬 상세화면 UI 구현 완료.
    - [ ]  포켓몬 정보 들을 한글화하여 저장하기 기능 구현
    - [ ]  포켓몬 상세 페이지의 배경색을 각 포켓몬의 색상으로 구현하기
    
- Level 8
    
    **+ 챌린지 과제**
    
    - [ ]  포켓몬 목록화면에서 무한 스크롤 기능 구현

- 추가 도전!
    - [ ]  포켓몬 잡기 기능 추가
    - [ ]  잡은 포켓몬에게 담은 책을 선물하기 기능
    - [ ]  잡은 포켓몬 목록을 보여주기
    - [ ]  포켓몬 잡기 기능에 몬스터볼 제한 두기
    - [ ]  책 정보를 읽을 때 랜덤하게 몬스터볼 얻는 기능
    - [ ]  오늘의 추천 책 보여주기
 
---

## 기타 자료
- [프로젝트 노션페이지 바로가기](https://seongto.notion.site/241225_-168a2764a65780ed91b4f316afab7b62?pvs=4)