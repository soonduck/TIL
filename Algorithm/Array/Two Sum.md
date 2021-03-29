# Two Sum

---

## 문제

숫자로 구성된 배열 nums와 타겟이 주어졌을 때, nums 요소 두개의 합으로 타겟을 만들고 두 숫자의 인덱스 값을 배열에 담아 리턴.

## 예시

```js
Given nums = [2, 7, 11, 15], target = 9
return [0, 1]
```

## 접근 방법

1. 임시로 숫자를 저장할 객체를 만든다.
2. 반복문을 돌면서 타겟 숫자에서 nums[i]를 뺀다.
3. 만약 타겟에서 nums[i]를 뺀 값이 객체에 있다면 nums[i]와 해당 값을 더했을 때 타겟이 나오는 것을 의미한다.
4. 따라서 임시 객체에는 프로퍼티 키로 숫자를, 밸류로는 인덱스 넘버를 넣은 다음
   숫자를 찾았을 때 객체의 숫자 인덱스값과 지금 루프를 돌고있는 i를 배열에 담아 리턴한다.
5. 해당사항이 없다면 임시객체에 nums[i] : i 값이 들어간다.

## 풀이

```js
const twoSum = (nums, target) => {
  const map = {};

  for (let i = 0; i < nums.length; i++) {
    const another = target - nums[i];

    if (another in map) {
      return [map[another], i];
    }

    map[nums[i]] = i;
  }

  return null;
};
```

## 후기

1. 혼자서 풀 수도 있었을 것 같은 문제지만 훨씬 더럽게 풀었을 것 같다.
2. if (key in obj)의 형식이 가능하다는 걸 배웠다.. 사실 예전에 배우고 넘어갔던 것 같은데 한번도 활용해 본적이 없었다. 이런 방식으로도 활용할 수 있다는 점을 배웠다.