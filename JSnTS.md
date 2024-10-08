# JS

## 1. Learn JavaScript

<https://web.dev/learn/javascript>

## 2. 자바스크립트는 어떻게 약속을 지킬까?

Promise, async/await, setTimeout이 브라우저에서 어떻게 동작하는지를 ECMAScript 표준 문서를 기반으로 추적하고 정리한 글이다.    
비동기 상태에 대한 처리는 항상 많이 이야기되었던 주제이기도 하지만 근본적으로 웹의 기능을 이해하기 위해 어떻게 접근해야 하는지를 알려주는 좋은 글   

<https://ui.toast.com/posts/ko_20220725>   


## 3. 자바스크립트 async와 await   

<https://joshua1988.github.io/web-development/javascript/js-async-await/>   


## 4. sort()
sort함수는 사용하면 원본도 바꾸기 때문에    
원본은 유지하고 변수에만 정렬해서 가지고 싶다면 '비구조화 할당(destucturing assignment)' 표현식을 사용해야함   

* 구조분해 할당   
<https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment>

* Spread syntax (...)   
<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax>  


## 5. .some()
배열 메서드   
배열 내의 항목 중 특정 조건에 해당하는 것이 하나라도 존재하는지 확인      

<https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/some> 


## 6. .every()
배열 메서드   
배열 내의 모든 항목이 특정 조건을 만족하는지 확인   

<https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/every>


## 7. .fill()   

```TS
private getDayCategories(): string[] {
        const {selectedDateTime} = this.state

        return new Array(getLastDayOfMonth(selectedDateTime.getFullYear(), selectedDateTime.getMonth() + 1)).fill("")
            .map((value, index) => `${index + 1}일`)
    }
```

## 8. .toLocaleString()

<https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleString>    

## 9. .scrollIntoView()
<https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView>

## 10. 자바스크립트 맵 객체 (Javascript Map Object)    
<https://wooncloud.com/104>    

## 11. ES6 문법으로 이차원 배열 생성하는 방법   

```TS 
const arr = new Array(5).fill(0).map(() => new Array(4));
```

## 12. 2차원 배열 new Array().fill()로 값 할당할 때 주의할 점   

<https://aeunhi99.tistory.com/257>   


## 13. 피셔 예이츠 알고리즘

<https://velog.io/@choisy/Js-%ED%94%BC%EC%85%94-%EC%98%88%EC%9D%B4%EC%B8%A0-%EC%85%94%ED%94%8C-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-Fisher-Yates-Shuffle>   

## 14. MutationObserver
<https://developer.mozilla.org/ko/docs/Web/API/MutationObserver/observe>   

MutationObserver 인터페이스는 DOM 트리의 변경을 감지하는 기능을 제공하는 Web API   
다크, 화이트 모드 변경을 감지하기 위해 리액트에서 MutationObserver.observe()를 아래와 같이 사용했음   

<https://developer.mozilla.org/ko/docs/Web/API/MutationObserver/observe>   

```TS
  private observer: MutationObserver | null = null;

  componentDidUpdate(prevProps: Props, prevState: State) {
    if (this.state.isThemeChanged !== prevState.isThemeChanged) {
      const targetNode = document.body;
      const observerOptions = {
        attributes: true,
        attributeFilter: ["style"],
        subtree: true,
      };

      this.observer = new MutationObserver((mutationsList, observer) => {
        for (let mutation of mutationsList) {
          if (mutation.type === "attributes") {
            setTimeout(() => this.setState({ isThemeChanged: false }), 1000);
          }
        }
      });

      this.observer.observe(targetNode, observerOptions);
    }
  }

  componentWillUnmount() {
    if (this.observer) {
      this.observer.disconnect();
    }
  }

```


# TS

## 1. TypeScript에서 string key로 객체에 접근하기   
<https://soopdop.github.io/2020/12/01/index-signatures-in-typescript/>
