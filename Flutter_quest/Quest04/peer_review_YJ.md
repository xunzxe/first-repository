<aside>
🔑 **PRT(Peer Review Template)**<br><br>
코더 : 서은재<br>
리뷰어 : 이유진<br><br>

- [O]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 기능이 정상적으로 작동하는지?
        - 해당 조건을 만족하는 부분의 코드 및 결과물을 근거로 첨부<br><br>
달력, 시간, 텍스트입력창 등 다양한 기능을 사용해서 스케줄관리앱을 만들었습니다. 새로운 앱을 구현하시는 거였는데 상세하게 구현을 잘 해주신 것 같습니다.

        ```
        # 시간입력 위젯
        final TimeOfDay? picked = await showTimePicker(     // retry :  시간을 입력받고자 showTimePicker라는 Flutter의 내장된 시간 선택 다이얼로그를 사용함
            context: context,
            initialTime: _selectedTime,
            if (picked != null && picked != _selectedTime) {
                setState(() {
                _selectedTime = picked;

        GestureDetector(
              onTap: () => _selectTime(context),
              child: InputDecorator(
                decoration: InputDecoration(
                  labelText: '시간',
                ),
                child: Text(
                  _selectedTime.format(context),
                  style: TextStyle(fontSize: 16),

        # 텍스트 입력 위젯
        final _titleController = TextEditingController();
        body: SingleChildScrollView(
        padding: EdgeInsets.all(16.0),
        child: Column(
          children: [
            TextField(
              controller: _titleController,
              decoration: InputDecoration(labelText: '일정명'),
        
        # 달력위젯
        child: CalendarCarousel(                     // retry : 캘린더 기능을 위해 Flutter에서 캘린더 위젯을 제공하는 패키지를 이용함
              onDayPressed: (date, events) {
                setState(() {
                  _selectedDate = date;
                });
              },
              selectedDateTime: _selectedDate,
              weekendTextStyle: TextStyle(
                color: Colors.red,
              ),
              todayButtonColor: Colors.blue,
              selectedDayTextStyle: TextStyle(
                color: Colors.yellow,
        ```


    
- [O]  **2. 핵심적이거나 복잡하고 이해하기 어려운 부분에 작성된 설명을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation/markdown이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
    <br><br>
    1번에서 캡처한 부분들과 동일합니다. 필요한 곳에 주석이 달려있어 코드에 대해 이해하기 쉬웠습니다.
        
- [O]  **3.** 에러가 난 부분을 디버깅하여 “문제를 해결한 기록”을 남겼나요? 또는
   “새로운 시도 및 추가 실험”을 해봤나요? ****
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인 또는
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
        
         <br>
         실제로 작동하는 일정관리 어플이었습니다. 날짜. 시간, 내용을 지정하면 값을 저장해 두고 있다가 삭제하여 관리할 수도 있고, 새로운 일정을 추가하게 되면 시간순으로 배열되는 점에서도 꼼꼼함이 돋보이셨습니다. 


- [O]  **4. 회고를 잘 작성했나요?**
    - 프로젝트 결과물에 대해 배운점과 아쉬운점, 느낀점 등이 상세히 기록 되어 있나요?
    <br><br>
    네. 회고를 잘 작성해주셨습니다

- [O]  **5. 코드가 간결하고 효율적인가요?**
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 모듈화(함수화) 했는지
        - 잘 작성되었다고 생각되는 부분을 근거로 첨부합니다.
        <br><br>
        필요한 부분들이 함수와 클래스 처리로 잘 정리가 되어 깔끔한 코드였습니다.
</aside>
