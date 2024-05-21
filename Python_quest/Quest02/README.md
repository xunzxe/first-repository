# AIFFEL Campus Code Peer Review
- 코더 : 서은재
- 리뷰어 : 김재이


# PRT(Peer Review Template)
[ㅇ]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
- 파일이 정상적으로 불러와졌습니다.
```from collections import Counter

file = open('Avengers.txt','r')
x = file.read()
```
- 텍스트의 전처리가 실행되었습니다. 모두 소문자로 처리되었고, 특히 부호 제거 전처리에 신경쓰신 코드였습니다.
```
x=x.lower()
x1=x.replace("'"," ")
special_chars = "!@,.-#?^()*&%$~`/|\<>[]{}"
translation_table = str.maketrans(' ',' ', special_chars)
cleaned_text = x1.translate(translation_table)
```

[ㅇ]  **2. 핵심적이거나 복잡하고 이해하기 어려운 부분에 작성된 설명을 보고 해당 코드가 잘 이해되었나요?**
- 코드 실행 전 주석으로서 코드의 전체 뼈대를 설명해주셔서 아래 진행된 내용을 이해하기 쉬웠습니다.
```
str.maketrans(x, y, z)
x와 y: 변환할 문자 쌍을 정의합니다. x의 각 문자는 y의 같은 위치에 있는 문자로 변환됩니다.
z: 제거할 문자들을 정의합니다. 이 매개변수에 포함된 모든 문자는 제거됩니다.


text = "Hello, World! Welcome to Python 3.9 #2024"

# 제거할 특수 문자 목록
special_chars = "!@#,. "

# 제거할 문자들을 빈 문자열로 매핑하는 번역 테이블 생성
translation_table = str.maketrans('', '', special_chars)

# translate 메서드를 사용해 특수 문자 제거
cleaned_text = text.translate(translation_table)
print(cleaned_text)  # "HelloWorldWelcometoPython392024"
```
        
[ㅇ]  **3. 에러가 난 부분을 디버깅하여 “문제를 해결한 기록”을 남겼나요? 또는 “새로운 시도 및 추가 실험”을 해봤나요?**
- 다양한 시도가 잘 설명되어 있었습니다. 특히 오늘의 주제였던 데이터 전처리에 있어서 어떤 부호를 제거하고, 어떻게 매핑할지 고민하신 흔적이 잘 보였습니다.
  효율적으로 사용할 수 있는 매서드로 최종 결과를 도출하기까지의 과정이 잘 담겨 있었습니다. 이 내용을 주석으로 첨부해주셨습니다.
```
words = cleaned_text.split()

splited_list  = list(zip(words, words[1:]))
print(Counter(splited_list).most_common()[0])
print(Counter(splited_list).most_common())

'''
max_count = -1
max_text = ''

for i in range(len(splited_list)):

  current_count = counter[splited_list[i]]
  if current_count > max_count:
    max_count = current_count
    max_text = splited_list[i]

  print(counter[splited_list[i]], splited_list[i])

count = {}
for letter in counter:
  if letter not in count:
    count[letter] = 0
  count[letter] += 1
'''
```
        
[ㅇ]  **4. 회고를 잘 작성했나요?**
- 다양한 방법으로 고민 후 매서드가 쉽게 해버리자 허무하다고 하셨는데, 공감이 될 정도로 코드, 주석 등 내용과 잘 맞는 회고였습니다. Counter 클래스를 새로 배운 것도 잘 기록되어 있습니다.
```
# 1.배운 점 : from collections import Counter를 새로 배웠다.
# 2.아쉬운 점 : 여러 방식으로 코드를 짰는데, 매서드 하나로 끝난다는 게 힘 빠진다.
```
