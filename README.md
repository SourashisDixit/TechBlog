<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TechBlog - A Learning Platform</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            line-height: 1.6;
            padding: 20px;
            min-height: 100vh;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
            animation: fadeIn 0.6s ease-in;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 60px 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120"><path d="M0,0V46.29c47.79,22.2,103.59,32.17,158,28,70.36-5.37,136.33-33.31,206.8-37.5C438.64,32.43,512.34,53.67,583,72.05c69.27,18,138.3,24.88,209.4,13.08,36.15-6,69.85-17.84,104.45-29.34C989.49,25,1113-14.29,1200,52.47V0Z" opacity=".25" fill="%23ffffff"/><path d="M0,0V15.81C13,36.92,27.64,56.86,47.69,72.05,99.41,111.27,165,111,224.58,91.58c31.15-10.15,60.09-26.07,89.67-39.8,40.92-19,84.73-46,130.83-49.67,36.26-2.85,70.9,9.42,98.6,31.56,31.77,25.39,62.32,62,103.63,73,40.44,10.79,81.35-6.69,119.13-24.28s75.16-39,116.92-43.05c59.73-5.85,113.28,22.88,168.9,38.84,30.2,8.66,59,6.17,87.09-7.5,22.43-10.89,48-26.93,60.65-49.24V0Z" opacity=".5" fill="%23ffffff"/><path d="M0,0V5.63C149.93,59,314.09,71.32,475.83,42.57c43-7.64,84.23-20.12,127.61-26.46,59-8.63,112.48,12.24,165.56,35.4C827.93,77.22,886,95.24,951.2,90c86.53-7,172.46-45.71,248.8-84.81V0Z" fill="%23ffffff"/></svg>') no-repeat bottom;
            background-size: cover;
            opacity: 0.1;
        }

        h1 {
            font-size: 3em;
            margin-bottom: 10px;
            font-weight: 700;
            position: relative;
            z-index: 1;
        }

        .emoji {
            font-size: 1.2em;
            display: inline-block;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .subtitle {
            font-size: 1.2em;
            opacity: 0.95;
            position: relative;
            z-index: 1;
        }

        .content {
            padding: 40px;
        }

        .section {
            margin-bottom: 40px;
        }

        h2 {
            color: #667eea;
            font-size: 1.8em;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 3px solid #667eea;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .feature-item {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 20px;
            border-radius: 12px;
            transition: all 0.3s ease;
            border-left: 4px solid #667eea;
        }

        .feature-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.3);
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        th {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: 600;
        }

        td {
            padding: 15px;
            border-bottom: 1px solid #e0e0e0;
        }

        tr:last-child td {
            border-bottom: none;
        }

        tr:hover {
            background: #f8f9ff;
        }

        .code-block {
            background: #2d3748;
            color: #68d391;
            padding: 20px;
            border-radius: 10px;
            margin: 15px 0;
            overflow-x: auto;
            font-family: 'Courier New', monospace;
            box-shadow: inset 0 2px 10px rgba(0,0,0,0.3);
        }

        .code-block code {
            color: #68d391;
        }

        .steps {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #667eea;
        }

        .steps h3 {
            color: #667eea;
            margin-top: 20px;
            margin-bottom: 10px;
        }

        .steps h3:first-child {
            margin-top: 0;
        }

        .divider {
            height: 2px;
            background: linear-gradient(90deg, transparent, #667eea, transparent);
            margin: 30px 0;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2em;
            }

            .content {
                padding: 20px;
            }

            header {
                padding: 40px 20px;
            }

            .feature-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1><span class="emoji">💻</span> TechBlog</h1>
            <p class="subtitle">A Dynamic Learning Platform</p>
        </header>

        <div class="content">
            <div class="section">
                <h2>📘 About the Project</h2>
                <p><strong>TechBlog</strong> is a web application that allows users to read, write, and share technical articles easily. It's designed to promote knowledge sharing among developers through an interactive, user-friendly interface. The project demonstrates strong backend development skills using <strong>Core Java, Servlets, JSP, and JDBC</strong>.</p>
            </div>

            <div class="divider"></div>

            <div class="section">
                <h2>✨ Features</h2>
                <div class="feature-grid">
                    <div class="feature-item">🔐 User Registration and Login Authentication</div>
                    <div class="feature-item">✍️ Create, Edit, and Delete Blog Posts</div>
                    <div class="feature-item">🧩 View Blogs by Category or Author</div>
                    <div class="feature-item">💬 Comment Section for Readers</div>
                    <div class="feature-item">🎨 Responsive UI with JSP and CSS</div>
                    <div class="feature-item">🗄️ Database Integration using JDBC</div>
                    <div class="feature-item">🕒 Session Management for Logged-in Users</div>
                </div>
            </div>

            <div class="divider"></div>

            <div class="section">
                <h2>🧰 Tech Stack</h2>
                <table>
                    <tr>
                        <th>Category</th>
                        <th>Technology</th>
                    </tr>
                    <tr>
                        <td>Language</td>
                        <td>Java</td>
                    </tr>
                    <tr>
                        <td>Framework</td>
                        <td>Servlet & JSP</td>
                    </tr>
                    <tr>
                        <td>Database</td>
                        <td>PostgreSQL / MySQL</td>
                    </tr>
                    <tr>
                        <td>Server</td>
                        <td>Apache Tomcat 9</td>
                    </tr>
                    <tr>
                        <td>IDE</td>
                        <td>Eclipse</td>
                    </tr>
                    <tr>
                        <td>Frontend</td>
                        <td>HTML, CSS, Bootstrap</td>
                    </tr>
                    <tr>
                        <td>Database Connectivity</td>
                        <td>JDBC</td>
                    </tr>
                </table>
            </div>

            <div class="divider"></div>

            <div class="section">
                <h2>⚙️ How to Run the Project</h2>
                <div class="steps">
                    <h3>1. Clone the Repository</h3>
                    <div class="code-block">
                        <code>git clone https://github.com/&lt;your-username&gt;/TechBlog.git</code>
                    </div>

                    <h3>2. Configure the Database</h3>
                    <p>Update the database configuration in your project files with your credentials.</p>

                    <h3>3. Deploy to Tomcat</h3>
                    <p>Add the project to your Apache Tomcat server and start the server.</p>

                    <h3>4. Access the Application</h3>
                    <div class="code-block">
                        <code>http://localhost:8080/TechBlog</code>
                    </div>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
