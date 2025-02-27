# Question
> 메모리 할당 중, 연속(Contiguous) 방식과 불연속(Non-Contiguous) 방식에 대해 설명해주세요.

# Answer

## 메모리 할당은 언제?

- 프로그램 → 프로세스(프로그램의 실행상태)가 되기 위해서 메모리에 할당되어야함.
    - 시작 메모리 위치, 메모리 할당 크기를 기반으로 할당 위치를 정해야 할당함.

### 연속 할당

- 프로세스(context)를 하나의 연속된 메모리 공간에 할당하는 것.
- 또 2가지로 나뉘는데
    - 고정 분할 방식 : “메모리”를 미리 같은 크기로 분할해서 할당 →  내부 단편화 생길 수 있음.
    - 가변 분할 방식 : “메모리”를 프로그램 크기에 맞게 할당 → 외부 단편화 생길 수 있음.

### 불연속 할당

> 메모리를 연속적으로 할당하지 않는 방법 → 현대 운영체제에서 사용하는 방식
> 

“메모리”를 쪼개놓는 것이 아니라, “프로그램”을 쪼개놓고 할당하는 것.

<b> 불연속 할당도 2가지로 나뉨 </b>

- 페이징 방식 : 프로그램을 동일한 크기로 쪼갬(페이지) → “서로 다른 위치”에 할당
- 세그멘테이션 방식 : 프로그램을 동일한 크기가 아닌 논리적인 단위로 쪼갬 → 이 또한 다른 위치에 할당

---
## 추가 정리
### 연속 할당

[[OS] Lec 8. Memory Management (2/3) - Fixed Partition Multiprogramming / 운영체제 강의](https://www.youtube.com/watch?v=te-GU7NKa5Y&list=PLBrGAFAIyf5rby7QylRc6JxU5lzQ9c4tN&index=25)

[[OS] Lec 8. Memory Management (3/3) - Variable Partition Multi-programming / 운영체제 강의](https://www.youtube.com/watch?v=o1TB9NWvG9w&list=PLBrGAFAIyf5rby7QylRc6JxU5lzQ9c4tN&index=26)

### 불연속 할당

[[OS] Lec 9. Virtual Memory (1/5) - Non-continuous allocation / 운영체제 강의](https://www.youtube.com/watch?v=YCfP9I4K-8Y&list=PLBrGAFAIyf5rby7QylRc6JxU5lzQ9c4tN&index=27)

<br>

## 배치 전략

- First-Fit (최초 적합)
    - 처음 마주하는(10MB) 공간에 할당
- Best-Fit(최적 적합)
    - 가장 알맞는 곳(10MB) 공간에 할당
    - 탐색 시간이 오래 걸림 (테이블 순회 시간)
    - 작은 크기의 파티션이 많이 발생 → 활용도 ↓
- Worst-Fit(최악 적합)
    - 제일 큰 공간(30MB)에 할당
- Next-Fit(순차 최초 적합)
    - 최초 적합 전략과 유사
    - 위에서부터 순회하면 윗 공간만 사용될 가능성이 크다.
    - 그래서 마지막 탐색한 위치부터 최초적합 진행

근데 생각해보면 빈 공간들 합치면 되는게 아닌가? → 외부 단편화 해결하는 방법

⇒ Coalescing holes(공간 통합)

: 프로세스가 메모리 회수하고 나가면 이러한 작업 수행

⇒ Storage Compaction(메모리 압축)

: 모든 빈 공간을 하나로 통합

: 모든 프로세스 재배치 해야하므로 오버헤드가 굉장히 크다. (자주하면 안됨)
