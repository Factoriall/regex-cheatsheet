# regex-cheatsheet

## 대표 문자
- \d: 숫자를 대표
- \D: 숫자를 제외한 문자
- \w: 글자를 대표, 문자와 숫자 포함, 특수문자 중 언더 바(_)를 제외하고는 포함하지 않음
- \W: 글자 대표를 제외한 글자들(특수문자, 공백 등)
- \s: 공백 문자(스페이스, 탭, 뉴라인)
- \S: 공백 문자를 제외한 문자
## 횟수 정하기(Quantifier)
- +: 하나 혹은 그 이상 연결된
  * \d+ : 하나 혹은 그 이상 연결된 숫자
- *: 0개 이상
  * \d* : 0개 이상의 숫자
- ?: 있거나 없거나
  * -? : -가 있거나 없다
- []: 조건 괄호
  * [- ]? : - 또는 공백이 있거나 없다
- {숫자}: ‘숫자’번 반복한다
  * \d{2} : 숫자가 연속 2번 나온다
- {숫자1, 숫자2}: 숫자1부터 숫자2까지 반복한다
  * \w{2,3} : 문자가 2-3번 나온다
## 고르기
- [‘아무 글자’]: 해당 글자 모두 선택
  * [aeiou]: 모든 소문자 알파벳 선택
  * [a-z]: a부터 z까지 글자를 모두 선택
  * [a-z]+: 연속된 영어 소문자 선택
  * [가-힣]+: 한글 단어 선택
  * [ㄱ-ㅎ]: 낱글자 선택
## 프로그래밍 언어별 정규표현식
### Java
- Pattern, Matcher 클래스 사용
- \ 대신 \\ 사용
  * 코드  
Pattern pattern = Pattern.compile("[정규 표현식]");  
        Matcher matcher = pattern.matcher(searchTarget);  
        while(matcher.find()){  
            System.out.println(matcher.group(0));  
        }  

### javascript
- String class의 match 함수 이용

  * 코드  
var regex = /[정규 표현식]/g;  
console.log(searchTarget.match(regex));

### c#
- Regex.matches 메소드 사용
- \ 대신 \\ 사용

  * 코드  
string regex = "[정규 표현식]";
foreach (Match m in Regex.Matches(searchTarget, regex)){  
            Console.WriteLine(m.Value);  
        }

### python
- re 라이브러리의 findall 메소드 사용

  * 코드  
import re  
result=re.findall([정규 표현식],search_target)  
print(result)  

