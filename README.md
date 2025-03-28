<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>留言板</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }
        #messageBox {
            width: 100%;
            height: 100px;
            margin-bottom: 10px;
        }
        #messageDisplay {
            margin-top: 20px;
            padding: 10px;
            background-color: #f5f5f5;
        }
    </style>
</head>
<body>
    <h1>欢迎来到留言板</h1>
    <textarea id="messageBox" placeholder="请输入留言"></textarea>
    <button onclick="submitMessage()">提交留言</button>

    <h2>最新留言：</h2>
    <div id="messageDisplay">暂无留言</div>

    <!-- Firebase SDK -->
    <script src="https://www.gstatic.com/firebasejs/9.22.1/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.22.1/firebase-database.js"></script>

    <script>
        // Firebase 配置信息
        const firebaseConfig = {
    apiKey: "AIzaSyDsZ-VZ7lzklLTlfizbSeVMEC5QjdLnhrY",
    authDomain: "interoperability-b22f0.firebaseapp.com",
    databaseURL: "https://interoperability-b22f0-default-rtdb.asia-southeast1.firebasedatabase.app",
    projectId: "interoperability-b22f0",
    storageBucket: "interoperability-b22f0.firebasestorage.app",
    messagingSenderId: "697557753503",
    appId: "1:697557753503:web:868ce96bfda21a1e2bccaa"
  };
        // 初始化 Firebase
        const app = firebase.initializeApp(firebaseConfig);
        const database = firebase.database();

        // 提交留言
        function submitMessage() {
            const message = document.getElementById('messageBox').value;
            if (message.trim() !== "") {
                const messageRef = database.ref('messages');
                messageRef.push({
                    message: message,
                    timestamp: Date.now()
                });
                document.getElementById('messageBox').value = ''; // 清空输入框
                loadMessage(); // 加载最新留言
            } else {
                alert("请输入留言内容！");
            }
        }

        // 加载留言
        function loadMessage() {
            const messageRef = database.ref('messages');
            messageRef.limitToLast(1).on('child_added', function(snapshot) {
                const message = snapshot.val().message;
                document.getElementById('messageDisplay').textContent = message || "暂无留言";
            });
        }

        // 页面加载时加载留言
        window.onload = loadMessage;
    </script>
</body>
</html>
