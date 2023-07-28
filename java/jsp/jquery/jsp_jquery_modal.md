
 ## jquery 모달창 스타일 받아오기 및 모달창 생성

```html
	<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-modal/0.9.1/jquery.modal.min.js"></script>
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/jquery-modal/0.9.1/jquery.modal.min.css" />
	
	<td><a href="#ex1" rel="modal:open" id="modal-up" onclick="update(${list.partNo})">수정</a></td>
	
	<div id="ex1" class="modal">
	  <a href="#" rel="modal:close" class="modal-text" onclick="RequestUpdate()">완료</a>
 	 <a href="#" rel="modal:close" class="modal-text" onclick="requestDelete()">삭제</a>
 	 <a href="#" rel="modal:close" class="modal-text">취소</a>
	</div>

```