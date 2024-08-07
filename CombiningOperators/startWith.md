startWith
=========

> 기존 시퀀스의 앞에 지정된 값을 추가하여 새로운 시퀀스를 생성.  
> 원래 시퀀스가 방출하는 요소들 전에 특정 값을 먼저 방출하도록 변경.

&nbsp;

![startWith](https://github.com/user-attachments/assets/9610729c-fe5b-400a-8691-fb1bdcca6431)

&nbsp;

```swift
import UIKit
import RxSwift

let disposeBag = DisposeBag()
let numbers = [1, 2, 3]

// - 출력결과 -
// next(-1)
// next(0)
// next(1)
// next(2)
// next(3)
// completed
Observable<Int>.from(numbers)
    // 이벤트 0 추가
    .startWith(0)
    // 이벤트 -1 추가
    .startWith(-1)
    // LIFO 방식
    .subscribe { print($0) }
    .disposed(by: disposeBag)
```



