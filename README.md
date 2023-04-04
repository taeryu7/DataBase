# DataBase
데이터 베이스는 자료를 저장하고 자료를 추가하고, 수정하고, 찾는 기능을 제공한다.

데이터 베이스는 많은 형태로 나타나지만 실제로 가낭 많이 쓰이는 유형은 관계형 데이터베이스(Relational Database)다.
이것은 각각의 자료들을 표에 기입한다.

다양한 데이터 형식
CREATE TABLE customers (id INTEGER PRIMARY KEY, name TEXT, age INTEGER, weight REAL);

기본키 사용
CREATE TABLE customers (id INTEGER PRIMARY KEY, age INTEGER);

전체 선택
SELECT * FROM customers;

조건으로 필터링
SELECT * FROM customers WHERE age > 21;

다중 조건으로 필터링
SELECT * FROM customers WHERE age < 21 AND state = "NY";

IN으로 필터링
SELECT * FROM customers WHERE plan IN ("free", "basic");

특정 열 선택
SELECT name, age FROM customers;

결과 정렬
SELECT * FROM customers WHERE age > 21 ORDER BY age DESC;

CASE로 변환
SELECT name, CASE WHEN age > 18 THEN "adult" ELSE "minor" END "type" FROM customers;


데이터 집계

집계 함수
SELECT MAX(age) FROM customers;

데이터 그룹화
SELECT gender, COUNT(*) FROM students GROUP BY gender;


관련 테이블에 조인

Inner join
SELECT customers.name, orders.item FROM customers JOIN orders ON customers.id = orders.customer_id;

Outer join
SELECT customers.name, orders.item FROM customers LEFT OUTER JOIN orders ON customers.id = orders.customer_id;


데이터 업데이트 및 삭제

데이터 업데이트
UPDATE customers SET age = 33 WHERE id = 73;

데이터 삭제
DELETE FROM customers WHERE id = 73;

