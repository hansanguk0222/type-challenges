# 110-Capitalize

## 1. 풀이
```ts
type MyCapitalize<S extends string> = S extends `${infer R}${infer T}` ?
  R extends 'a' | 'b' | 'c' | 'd' | 'e' | 'f' | 'g' | 'h' | 'i' | 'j' |'k' | 'l' | 'm' | 'n' | 'o' | 'p' | 'q' | 'r' | 's' | 't' | 'u' | 'v' | 'w' | 'x' | 'y' | 'z'
    ? `${Uppercase<R>}${T}` : `${R}${T}`
        : S;
```

## 2. 해설
1. 먼저 infer를 이용해 S를 두 개의 문자열로 분리한다.
2. 앞 글자가 소문자면 Uppercase 타입을 이용해 대문자로 변경한다.
3. 그 경우가 아니면 원래 문자열을 뱉어낸다.
