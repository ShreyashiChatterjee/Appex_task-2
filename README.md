<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contact Form and To-Do List</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            min-height: 100vh;
            background: linear-gradient(135deg, #e0eafc, #cfdef3);
            color: #333;
        }

        /* Flexbox Navigation */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #1a1a2e;
            padding: 1.5rem 2rem;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        nav h1 {
            font-size: 1.8rem;
            color: #fff;
            font-weight: 600;
            letter-spacing: 1px;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            font-size: 1.1rem;
            font-weight: 400;
            transition: color 0.3s ease;
        }

        nav a:hover {
            color: #00ddeb;
        }

        /* Grid Layout for Content */
        .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            padding: 3rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .contact-form, .todo-list {
            background: #fff;
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .contact-form:hover, .todo-list:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 25px rgba(0, 0, 0, 0.15);
        }

        .contact-form h2, .todo-list h2 {
            margin-bottom: 1.5rem;
            color: #1a1a2e;
            font-weight: 600;
            font-size: 1.8rem;
        }

        /* Form Styling */
        .form-group {
            margin-bottom: 1.5rem;
            position: relative;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #1a1a2e;
            font-weight: 400;
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease, box-shadow 0.3s ease;
            background: #f9f9f9;
        }

        .form-group input:focus, .form-group textarea:focus {
            outline: none;
            border-color: #00ddeb;
            box-shadow: 0 0 8px rgba(0, 221, 235, 0.3);
            background: #fff;
        }

        button {
            background: #00ddeb;
            color: #fff;
            padding: 0.8rem 2rem;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 500;
            transition: background 0.3s ease, transform 0.2s ease;
        }

        button:hover {
            background: #00b7c2;
            transform: scale(1.05);
        }

        .error {
            color: #ff4d4d;
            font-size: 0.85rem;
            margin-top: 0.3rem;
            display: none;
            position: absolute;
            bottom: -1.5rem;
        }

        /* To-Do List Styling */
        .todo-input {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .todo-input input {
            flex: 1;
            padding: 0.8rem;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .todo-input input:focus {
            border-color: #00ddeb;
            outline: none;
        }

        .todo-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem;
            border-bottom: 1px solid #f0f0f0;
            background: #f9f9f9;
            border-radius: 8px;
            margin-bottom: 0.5rem;
            transition: background 0.3s ease;
        }

        .todo-item:hover {
            background: #f0f0f0;
        }

        .todo-item span {
            font-size: 1rem;
            color: #1a1a2e;
        }

        .todo-item button {
            background: #ff4d4d;
            padding: 0.5rem 1rem;
            font-size: 0.9rem;
        }

        .todo-item button:hover {
            background: #e63939;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 1.5rem;
                padding: 1rem;
            }

            nav ul {
                flex-direction: column;
                align-items: center;
                gap: 1rem;
            }

            .container {
                grid-template-columns: 1fr;
                padding: 2rem 1rem;
            }
        }

        @media (max-width: 480px) {
            nav h1 {
                font-size: 1.5rem;
            }

            nav a {
                font-size: 1rem;
            }

            .container {
                padding: 1rem;
            }

            .contact-form, .todo-list {
                padding: 1.5rem;
            }

            .contact-form h2, .todo-list h2 {
                font-size: 1.5rem;
            }

            button {
                width: 100%;
                padding: 0.8rem;
            }

            .todo-input {
                flex-direction: column;
            }

            .todo-input button {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <nav>
        <h1>My Website</h1>
        <ul>
            <li><a href="#contact">Contact</a></li>
            <li><a href="#todo">To-Do List</a></li>
        </ul>
    </nav>

    <div class="container">
        <section class="contact-form" id="contact">
            <h2>Contact Us</h2>
            <form id="contactForm">
                <div class="form-group">
                    <label for="name">Name *</label>
                    <input type="text" id="name" name="name" required>
                    <span class="error" id="nameError">Please enter your name</span>
                </div>
                <div class="form-group">
                    <label for="email">Email *</label>
                    <input type="email" id="email" name="email" required>
                    <span class="error" id="emailError">Please enter a valid email</span>
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" name="message" rows="4"></textarea>
                </div>
                <button type="submit">Submit</button>
            </form>
        </section>

        <section class="todo-list" id="todo">
            <h2>To-Do List</h2>
            <div class="todo-input">
                <input type="text" id="todoInput" placeholder="Add a new task">
                <button onclick="addTodo()">Add Task</button>
            </div>
            <div id="todoList"></div>
        </section>
    </div>

    <script>
        // Form Validation
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            let isValid = true;

            // Name validation
            const name = document.getElementById('name').value.trim();
            const nameError = document.getElementById('nameError');
            if (!name) {
                nameError.style.display = 'block';
                isValid = false;
            } else {
                nameError.style.display = 'none';
            }

            // Email validation
            const email = document.getElementById('email').value.trim();
            const emailError = document.getElementById('emailError');
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!email || !emailRegex.test(email)) {
                emailError.style.display = 'block';
                isValid = false;
            } else {
                emailError.style.display = 'none';
            }

            if (isValid) {
                alert('Form submitted successfully!');
                this.reset();
            }
        });

        // To-Do List Functionality
        function addTodo() {
            const todoInput = document.getElementById('todoInput');
            const taskText = todoInput.value.trim();

            if (taskText) {
                const todoList = document.getElementById('todoList');
                const todoItem = document.createElement('div');
                todoItem.className = 'todo-item';

                const taskSpan = document.createElement('span');
                taskSpan.textContent = taskText;

                const deleteBtn = document.createElement('button');
                deleteBtn.textContent = 'Delete';
                deleteBtn.onclick = function() {
                    todoList.removeChild(todoItem);
                };

                todoItem.appendChild(taskSpan);
                todoItem.appendChild(deleteBtn);
                todoList.appendChild(todoItem);

                todoInput.value = '';
            }
        }

        // Allow Enter key to add tasks
        document.getElementById('todoInput').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                addTodo();
            }
        });
    </script>
</body>
</html>
