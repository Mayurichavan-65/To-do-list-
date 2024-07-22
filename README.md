<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive To-Do List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRzUi63M3lr018YmFPZbH4yJUnAdSw6C_86G1fQmpxk4SVQqAloNYUR2YGdhMbjMxkBX8w&usqp=CAU'); /* Replace with your image URL or file path */
            background-size: cover;
            background-position: center;
        }

        .container {
            background: rgba(255, 255, 255, 0.329);
            padding: 50px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 500px;
            text-align: center;
        }

        h1 {
            margin-bottom: 20px;
        }

        input[type="text"] {
            width: calc(100% - 22px);
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            margin-bottom: 10px;
        }

        button {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            background-color: #28a745;
            color: white;
            cursor: pointer;
        }

        button:hover {
            background-color: #218838;
        }

        ul {
            list-style: none;
            padding: 0;
        }

        li {
            padding: 10px;
            border-bottom: 1px solid #ccc;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        li button {
            background: none;
            border: none;
            color: rgb(255, 255, 255);
            cursor: pointer;
        }

        li button:hover {
            color: darkred;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <input type="text" id="taskInput" placeholder="Add a new task">
        <button onclick="addTask()">Add</button>
        <ul id="taskList"></ul>
    </div>
    <script>
        function addTask() {
            const taskInput = document.getElementById('taskInput');
            const taskList = document.getElementById('taskList');

            if (taskInput.value.trim() === '') {
                alert('Please enter a task');
                return;
            }

            const listItem = document.createElement('li');
            listItem.innerHTML = `${taskInput.value} <button onclick="removeTask(this)">Remove</button>`;

            taskList.appendChild(listItem);
            taskInput.value = '';
        }

        function removeTask(button) {
            const listItem = button.parentElement;
            listItem.remove();
        }
    </script>
</body>
</html>
