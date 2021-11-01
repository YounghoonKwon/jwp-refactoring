# 키친포스

## 요구 사항
### MenuGroup

-[ ] MenuGroup을 저장한다.

-[ ] MenuGroup List를 조회한다.

### Menu

-[ ] Menu를 저장한다.

-[ ] 가격이 null이거나 0보다 작으면 **예외**

-[ ] 해당 ID가 MenuGroup에 존재하지 않으면 **예외**

-[ ] Menu내의 MenuProducts를 사용해 상품*갯수 하여 전체 합을 구한다.

-[ ] MenuProducts의 모든 Product는 DB에 존재해야한다.

-[ ] Menu의 가격이 모든 Product가격의 합보다 크면 **예외**

-[ ] Menu를 DB에 저장 후, MenuProduct에 MenuId Menu에 MenuProduct를 각각 입혀준다.

-[ ] Menu List를 조회한다.

### Order

-[ ] Order를 저장한다.

-[ ] OrderLineItems가 비어있으면 **예외**

-[ ] OrderLineItems의 크기와 MenuDao의 countByIdIn(menuIds)가 같지 않으면 **예외**

-[ ] 해당 Order의 OrderTableId가 orderTableDao 존재하지 않으면 **예외**

-[ ] OrderTable이 Empty이면 **예외**

-[ ] Order에 OrderTableId, OrderStatus, OrderedTime 설정 후 저장

-[ ] OrderLineItems 전체에 각각 OrderId 설정 후 Saved Order에 set

-[ ] Order List를 조회한다.

-[ ] Order Status를 변경한다.

-[ ] OrderId로 Order이 존재하는지 확인한다.

-[ ] Order Status가 Completion 상태이면 **예외**

-[ ] 반환할 Saved Order에 OrderLineItems를 찾아서 set

### Product

-[ ] Product를 저장한다.

-[ ] 가격이 null이거나 가격이 0보다 작으면 **예외**

-[ ] Product List를 조회한다.

### TableGroup

-[ ] Table Group을 저장한다.

-[ ] TableGroup의 orderTables가 empty이거나 사이즈가 2보다 작으면 **예외**

-[ ] OrderTables의 id들이 db에 저장된 갯수를 확인하여 다르면 **예외**

-[ ] DB에서 불러온 orderTables를 각각 하나씩 확인하며, Empty가 아니거나 null이 아닐 경우 **예외**

-[ ] TableGroup에 CreatedDate 지정 후 저장

-[ ] TableGroup의 ID값을 order tables 각각의 엔티티에 지정 후 저장

-[ ] Table Group을 ungroup한다.

-[ ] tableGroupId 기준으로 order tables을 찾는다

-[ ] Order에 orderTableId와 orderStatus가 존재하면 **예외**

-[ ] orderTables의 tableGroupId값을 비우고, empty를 false로 저장해준다.

### Table

-[ ] Order Table을 저장한다.

-[ ] 초기 값은 id null, table group id null이다.

-[ ] Order Tables를 조회한다.

-[ ] Table을 Empty상태로 변경한다.

-[ ] Order Table을 DB에서 찾아오고, 없으면 **예외**

-[ ] 찾아온 Order Table에 Table Group Id 가 존재하면 **예외**

-[ ] OrderTable Id를 이용해서 해당 Order가 Cooking상태 또는 Meal상태이면 **예외**

-[ ] Empty 상태로 변경 후 DB 저장

-[ ] Table의 Guest 숫자를 변경한다

-[ ] Guest의 숫자가 0보다 작으면 **예외**

-[ ] Table Id가 DB에 없으면 **예외**

-[ ] Order Table이 Empty상태이면 **예외**

-[ ] 이외의 경우 Guest숫자 지정 후 저장






## 용어 사전

| 한글명 | 영문명 | 설명 |
| --- | --- | --- |
| 상품 | product | 메뉴를 관리하는 기준이 되는 데이터 |
| 메뉴 그룹 | menu group | 메뉴 묶음, 분류 |
| 메뉴 | menu | 메뉴 그룹에 속하는 실제 주문 가능 단위 |
| 메뉴 상품 | menu product | 메뉴에 속하는 수량이 있는 상품 |
| 금액 | amount | 가격 * 수량 |
| 주문 테이블 | order table | 매장에서 주문이 발생하는 영역 |
| 빈 테이블 | empty table | 주문을 등록할 수 없는 주문 테이블 |
| 주문 | order | 매장에서 발생하는 주문 |
| 주문 상태 | order status | 주문은 조리 ➜ 식사 ➜ 계산 완료 순서로 진행된다. |
| 방문한 손님 수 | number of guests | 필수 사항은 아니며 주문은 0명으로 등록할 수 있다. |
| 단체 지정 | table group | 통합 계산을 위해 개별 주문 테이블을 그룹화하는 기능 |
| 주문 항목 | order line item | 주문에 속하는 수량이 있는 메뉴 |
| 매장 식사 | eat in | 포장하지 않고 매장에서 식사하는 것 |
