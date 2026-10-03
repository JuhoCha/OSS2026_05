Deployment
Vercel 배포 URL : https://assign05-22400719.vercel.app/


Key Learning
이번 주에 배운 핵심 내용 3가지
1. JS에도 inline, internal, external이 있다. innerHTML사용하면 tag 있고 html요소 있을때 사용
2. JS를 활용해 동적으로 HTML을 만들 수 있는데 querySelector, eventlistener 등을 사용하면 동적 액션을 만들 수 있다. 
3. appendChild 해주면 밑에 자식요소로 추가가 된다. hidden 해주려면 style=”display:none”해주면 숨기기도 가능. remove() : 자기 자신 삭제, Parent.removechild : 자식 요소 삭제


CRUD Service

구현한 서비스 주제 : TODOlist로 할일을 관리하는 프로그램입니다. 제가 평소 할일을 잘 잊는 편이라 이렇게 기록하는데 만들어서 사용하고 싶었습니다. 
사용하는 데이터 Field
1. id 순서 보이기 위해 사용했습니다.
2. title 숙제 이름이 뭔지 확인하기 위해서 만들었습니다. 
3. subject 어떤 과목의 과제인지 보여주기 위해 사용했습니다.
4. task 자세하게 어떤걸 하는지 보여주기 위해서 사용했습니다.
5. deadline 기한 나타내려고 date로 사용했습니다.
6. priority 일에 평소에 중요도로 순서 나타내고 그대로 따르는걸 좋아해 만들어봤습니다. 


Create: 일정등록 버튼을 누르면 안에 내용을 검사하고 잘못된게 있으면 alert해주고 통과되면 array에 추가되게 만들었습니다. 입력값을 array에 추가할 수 있게 render을 사용했습니다.
Read: render가 tbody를 비우고, foreach사용해서 값을 하나하나 읽고 tr, td를 붙였습니다. 
Update: 수정 버튼으로 해당 값을 수정할 수 있게 만들었습니다. 그 값을 선택해서 바꾸면 find로 값을 찾아서 바꿉니다. 
Delete: 삭제를 누르면 confirm 창이 나와서 한번 확인하고, filter을 사용해서 array에서 지울때는 남길걸 선택해야 했어서 지울 값만 빼고 나머지를 선택하게 했습니다. 


JavaScript

querySelector() : 입력창이나 버튼 등에 사용헀고, id로 HTML요소를 선택합니다. 
addEventListener() : button클릭때 사용했고, 이벤트를 만들고 싶을때 동작할것을 선택합니다. 
createElement() : td, tr이런거 추가할때 사용했습니다. HTML요소를 만들때 사용합니다.
appendChild() : td를 tr에 넣을떄 사용하고, 자식(?)처럼 만들어줍니다. 
Array : 데이터 저장소로 어떤 요소들을 넣어주는데 이번 코드에서는 기본적으로 있는 4가지 li정보들이 대표적입니다 
foreach() : array 요소를 하나하나 반복하는데 render할떄 tr, td해서 만들때 사용했습니다. 
filter() : 조건에 맞는 요소만 남기고 새로운 배열을 만듭니다.


AI / Search Usage

사용한 AI 또는 검색 도구 : Gemini, 구글 검색, 교수님께서 주신 ppt
어떤 문제를 해결하기 위해 사용했는지 : 제가 이전에 했던 코드는 단순히 화면에 붙이는 수준이었다면  Array에 대한 개념이 부족해 그게 뭔지 어떻게 하면 등록, 수정을 할 수 있을지 막막해져 구글 검색을 해서 Array개념을 배우고 ai한테 예시좀 만들어 달라고 했습니다. 먼저 힌트를 받아 지금 제가 부족한 개념이 무엇인지 받고, 자세한 주석을 달아달라고 프롬포트를 만들어서 사용법을 익혔습니다. 
실제 코드에 어떻게 적용했는지 : tr을 만드는 코드를 render안으로 옮기고, edit, delete가 끝나면 render()이 되게 만들었습니다. 삭제할떄는 원래 remove나 child삭제 했었는데 filter()을 이용해 삭제했고, 수정은 find와 editID변수로 해결했습니다. 
새롭게 이해한 내용 :
- checkValidity는 HTML태그에 적힌걸 기준으로 판단함
- filter은 지우는 함수가 아니기에 남을걸 선택해야함!


Problem & Solution
- 제가 처음에 시도했던 방향은 HTML 안에서만 구동하는 코드였고, array가 정확하게 뭔지 깊게 생각을 안했었습니다. 그런데 조건을 하나하나 자세하게 읽어보니 array라는 조건이 있었고, tr.remove로 지웠던것을 filter을 사용해 삭제로 변경하고, array를 읽을 수 있는 render라는 것으로 내용을 지워서 해결했습니다. 

Reflection
- Array가 진짜 데이터이고 화면은 그것을 그려놓은 결과라는 것을 알게 되었습니다. 데이터(Array)와 화면(DOM)을 나눠서 생각해야 한다는 것을 알게 되었습니다. 화면만 고치면 데이터와 화면이 서로 달라졌습니다. 그래서 교수님이 DOM을 따로 알려주셨구나 하는것을 알게되었습니다. 

