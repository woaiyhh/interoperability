<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>留言板</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            text-align: center;
            padding: 20px;
        }
        .container {
            background: white;
            max-width: 400px;
            margin: auto;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        textarea {
            width: 100%;
            height: 80px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            resize: none;
        }
        button {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            border: none;
            border-radius: 5px;
            background: #007bff;
            color: white;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background: #0056b3;
        }
        .message-box {
            margin-top: 20px;
            padding: 15px;
            background: #e9ecef;
            border-radius: 5px;
            word-break: break-word;
        }
        .copy-btn {
            margin-top: 10px;
            background: #28a745;
        }
        .copy-btn:hover {
            background: #218838;
        }
    </style>
</head>
<body>

    <div class="container">
        <h2>留言板</h2>
        <textarea id="messageBox" placeholder="输入留言..."></textarea>
        <button onclick="submitMessage()">提交留言</button>

        <h3>最新留言：</h3>
        <div class="message-box" id="messageDisplay">暂无留言</div>
        <button class="copy-btn" onclick="copyMessage()">复制留言</button>
    </div>

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
            const message = document.getElementById('messageBox').value.trim();
            if (message !== "") {
                const messageRef = database.ref('messages');
                messageRef.push({
                    message: message,
                    timestamp: Date.now()
                }).then(() => {
                    document.getElementById('messageBox').value = ''; // 清空输入框
                    alert("留言提交成功！");
                }).catch(error => {
                    alert("提交失败：" + error.message);
                });
            } else {
                alert("请输入留言内容！");
            }
        }

        // 加载最新留言
        function loadMessage() {
            const messageRef = database.ref('messages').limitToLast(1);
            messageRef.on('child_added', function(snapshot) {
                const message = snapshot.val().message;
                document.getElementById('messageDisplay').textContent = message || "暂无留言";
            });
        }

        // 复制留言
        function copyMessage() {
            const messageText = document.getElementById('messageDisplay').textContent;
            if (messageText && messageText !== "暂无留言") {
                navigator.clipboard.writeText(messageText).then(() => {
                    alert("留言已复制！");
                }).catch(err => {
                    alert("复制失败：" + err);
                });
            } else {
                alert("没有留言可复制！");
            }
        }

        // 页面加载时获取最新留言
        window.onload = loadMessage;
    </script>

</body>
</html>
