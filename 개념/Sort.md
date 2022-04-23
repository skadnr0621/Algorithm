## Sort 정렬



## 🛒 출처

## https://coding-factory.tistory.com/549

---



### 정렬 개념

배열이나 리스트 정렬시 java.util.Arrays 클래스의 sort 메소드를 이용해서 정렬 로직 없이 정렬을 할 수 있습니다.

- **배열 오름차순 정렬**
  
  - Arrays.sort() 메서드의 매개값으로 기본 타입 배열이나 String 배열 지정시 자동으로 오름차순 정렬이 됩니다. **기본이 오름차순! /**
    ex) **Arrays.sort(arr);**
  
- **배열 내림차순\ 정렬**
  
  - 내림차순 정렬할 때는 Collections 클래스의 reverseOrder() 메서드를 사용합니다. 
    ex) Collections.reverseOrder()
    ex) **Arrays.sort(arr, Collections.reverseOrder());**
  - 기본타입 배열을 내림차순으로 정렬하고 싶을 시 기본 타입의 배열을 래퍼클래스로 만들어(?) Comparator를 두번째 인자로 넣어줘야 역순으로 정렬 가능. 
    - 주의! String은 기본타입이 아닙니다. 
    - 다른 for문도 연습하세요. 
  
- **배열 일부분 정렬**

  - 매개변수로 배열, 시작index, 끝index 를 넣어주면 해당 범위만 정렬할 수 있습니다. 
  - 끝 index는 항상 미만으로 적용됩니다. 
    ex) Arrays.sort(arr, 0, 4); // 0~3 요소만 정렬됩니다. 

- **객체 배열 정렬**

  - 객체로 이뤄진 배열의 경우는 객체 클래스가 Comparable 인터페이스의 CompareTo() 메서드를 구현하고 있어야 정렬이 됩니다. **나이별**로 정렬하는 예제를 보자면,

    ``` java
    import java.util.*;
    
    class People implements Comparable{
        private String name;
        private int age;
        
        public People(String name, int age){
            this.name = name;
            this.age = age;
        }
        
        public String print(){
            return name + "(" + age + ")";
        }
        
        @Override
        public int compareTo(People people){
            if(this.age < people.age){
                return -1;
            } else if(this.age == people.age){
                return 0;
            } else{
                return 1;  
            }
        }
    }
    
    public class Sort{
        public static void main(String[] args){
            People[] arr = {
                new People("상현", 20),
                new People("철수", 14),
                new People("경완", 31),
                new People("대호", 40),
                new People("지운", 34),
                           };
            Arrays.sort(arr); //오름차순 정렬
            
            for(People i : arr){ //오름차순 출력
                System.out.print("[" + i.print() + "]");
            }
            
            Arrays.sort(arr, Collections.reverseOrder());// 내림차순 정렬
            System.out.println();
            
            for(People i : arr){ // 내림차순 출력
                System.out.print("[" + i.print() + "]");
            }
        }
    }
    ```

    







