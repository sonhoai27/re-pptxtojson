# 🎨 PPTX2JSON
PPTX2JSON Đây là một công cụ có nguồn gốc từ PPTX2HTML. Các tệp .pptx có thể được phân tích cú pháp thành dữ liệu JSON. Nó vẫn chưa đủ để sử dụng cho sản xuất.

# install
> npm install pptxtojson

# 💿 use
```html
<input type="file" accept="application/vnd.openxmlformats-officedocument.presentationml.presentation"/>
```

```js
import { parse } from 'pptxtojson'

document.querySelector('input').addEventListener('change', evt => {
	const file = evt.target.files[0]
	
	const reader = new FileReader()
	reader.onload = async e => {
		const json = await parse(e.target.result)
		console.log(json)
	}
	reader.readAsArrayBuffer(file)
})
```