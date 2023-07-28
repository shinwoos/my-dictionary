## crypto로 math.random() 대체
 
javascript 에서 math.random() 대체 crypto 사용.

math.random()은 "적절하지 않은 난수값" 이라는 이유로 코드 보안에 걸려 crypto를 사용해 보안을 강화해야한다.

```javascript

	crypto.getRandomValues(new Uint8Array(1)); // 8비트 랜덤 배열 1개
	crypto.getRandomValues(new Uint8Array(2)); // 8비트 랜덤 배열 2개
	crypto.getRandomValues(new Uint16Array(3)); // 16비트 랜덤 배열 3개
	crypto.getRandomValues(new Uint32Array(4)); // 32비트 랜덤 배열 4개

	crypto.getRandomValues(new Uint32Array(10)).join(''); 32비트 랜덤 배열10개를 1라인으로 출력

	crypto.getRandomValues(new Uint32Array(1))/4294967296 // Math.random() 과 동일한 포맷
```