# js.github.io
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>无标题文档</title>
</head>
	<script>
		document.querySelector('form').addEventListener('submit', function(event) {
  var username = document.querySelector('#username').value;
  var password = document.querySelector('#password').value;
  if (username === 'admin' && password === '123456') {
    alert('登录成功！');
  } else {
    alert('用户名或密码错误！');
  }
  event.preventDefault();
});
		document.querySelector('form').addEventListener('submit', function(event) {
  var name = document.querySelector('#name').value;
  var email = document.querySelector('#email').value;
  var message = document.querySelector('#message').value;
  alert('提交成功！');
  event.preventDefault();
});
		var comments = document.querySelectorAll('.comment');
for (var i = 0; i < comments.length; i++) {
  var comment = comments[i];
  var topButton = comment.querySelector('.comment-top');
  var deleteButton = comment.querySelector('.comment-delete');
  topButton.addEventListener('click', function(event) {
    var comment = event.target.closest('.comment');
    var comments = comment.parentNode;
    comments.insertBefore(comment, comments.firstChild);
  });
  deleteButton.addEventListener('click', function(event) {
    var comment = event.target.closest('.comment');
    comment.parentNode.removeChild(comment);
  });
}
	var myVideo = document.getElementById("myVideo");
function playPause() {
  if (myVideo.paused)
    myVideo.play();
  else
    myVideo.pause();
}
function makeBig() {
  myVideo.width = 960;
}
function makeSmall() {
  myVideo.width = 320;
}
function makeNormal() {
  myVideo.width = 640;
}
var slideIndex = 0;
showSlides();

function showSlides() {
  var i;
  var slides = document.getElementsByClassName("mySlides");
  for (i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";
  }
  slideIndex++;
  if (slideIndex > slides.length) {
    slideIndex = 1
  }
  slides[slideIndex - 1].style.display = "block";
  setTimeout(showSlides, 3000); 
}
function plusSlides(n) {
  showSlides(slideIndex += n);
}
		
	
	</script>
<style>
	video {
  border: 1px solid #ccc;
  box-shadow: 0px 0px 5px #999;
}
.slideshow-container {
  max-width: 1000px;
  position: relative;
  margin: auto;
}

.mySlides {
  display: none;
}

.prev,
.next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  margin-top: -22px;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
  user-select: none;
}

.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

.prev:hover,
.next:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}

@-webkit-keyframes fade {
  from {
    opacity: 0.4
  }

  to {
    opacity: 1
  }
}

@keyframes fade {
  from {
    opacity: 0.4
  }

  to {
    opacity: 1
  }
}
	
</style>
<body>
	<form>
  <label for="username">用户名：</label>
  <input type="text" id="username" name="username" required>
  <br>
  <label for="password">密码：</label>
  <input type="password" id="password" name="password" required>
  <br>
  <input type="submit" value="登录">
  <label for="name">姓名：</label>
  <input type="text" id="name" name="name" required>
  <br>
  <label for="email">邮箱：</label>
  <input type="email" id="email" name="email" required>
  <br>
  <label for="message">留言：</label>
  <textarea id="message" name="message" required></textarea>
  <br>
  <input type="submit" value="提交">
</form>
	<div id="comments">
  <div class="comment">
    <div class="comment-header">
      <span class="comment-author">张三</span>
      <span class="comment-time">2022-01-01 12:00:00</span>
      <button class="comment-top">置顶</button>
      <button class="comment-delete">删除</button>
    </div>
    <div class="comment-content">
      这是一条评论。
    </div>
  </div>
  <div class="comment">
    <div class="comment-header">
      <span class="comment-author">李四</span>
      <span class="comment-time">2022-01-01 12:01:00</span>
      <button class="comment-top">置顶</button>
      <button class="comment-delete">删除</button>
    </div>
    <div class="comment-content">
      这是另一条评论。
    </div>
  </div>
</div>
	<video id="myVideo" width="640" height="360" controls>
  <source src="myVideo.mp4" type="video/mp4">
  <source src="myVideo.ogg" type="video/ogg">
  Your browser does not support the video tag.
</video>

<button onclick="playPause()">播放/暂停</button>
<button onclick="makeBig()">放大</button>
<button onclick="makeSmall()">缩小</button>
<button onclick="makeNormal()">默认大小</button>
	<div class="slideshow-container">
  <div class="mySlides fade">
    <img src="slide1.jpg" style="width:100%">
  </div>
  <div class="mySlides fade">
    <img src="slide2.jpg" style="width:100%">
  </div>
  <div class="mySlides fade">
    <img src="slide3.jpg" style="width:100%">
  </div>
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>
</div>
</body>
</html>
