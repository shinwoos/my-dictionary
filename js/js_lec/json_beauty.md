# JSON beauty

```javascript
    function jsonBeautify(data){

		var jsonData = JSON.parse(data.jsonData);

		// JSON 데이터를 문자열로 변환합니다.
        const jsonString = JSON.stringify(jsonData, null, "\t");

        // JSON key와 value를 정규식을 사용하여 각각 다른 클래스로 만들어서 key value에 따른 색상넣기
        const styledJsonString = jsonString.replace(/"(\w+)": "(.*?)"/g, '"<span class="json-key">$1</span>":"<span class="json-value">$2</span>"');
		const styleJson = styledJsonString.replace(/"(\w+)":/g,'"<span class="json-key">$1</span>":');
		const resultJsonStyle = styleJson.replace(/: (\w+)/g,':<span class="json-value">$1</span>');
        const outputElement = document.getElementById("list_div");
        outputElement.innerHTML = resultJsonStyle;
}
```