# simple-web-page2
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Web Page</title>
    <link rel="stylesheet" href="styles.css">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Welcome to My Simple Web Page</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <main>
        <section id="home">
            <h2>Home</h2>
            <p>This is the home section of the page.</p>
        </section>
        
        <section id="about">
            <h2>About</h2>
            <p>This section contains information about the web page.</p>
        </section>
        
        <section id="contact">
            <h2>Contact</h2>
            <p>Feel free to contact us through this section.</p>
            
            <h3>Leave a Comment</h3>
            <form id="comment-form">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required>

                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>

                <label for="comment">Comment:</label>
                <textarea id="comment" name="comment" rows="4" required></textarea>

                <button type="submit">Submit</button>
            </form>
            
            <div id="comments-section">
                <h3>Comments</h3>
                <div id="comments-list"></div>
            </div>
        </section>
    </main>
    
    <footer>
        <p>&copy; 2024 My Simple Web Page</p>
    </footer>
    
    <script src="script.js"></script>
</body>
</html>


/* Basic reset to remove default browser styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Body styling */
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    background-color: #f4f4f4;
    color: #333;
    padding: 20px;
}

/* Header styling */
header {
    background: #50b3a2;
    color: #fff;
    padding: 20px 0;
    text-align: center;
    margin-bottom: 20px;
}

header h1 {
    margin-bottom: 10px;
}

/* Navigation menu styling */
nav ul {
    list-style: none;
    padding: 0;
    text-align: center; /* Center the navigation links */
}

nav ul li {
    display: inline-block;
    margin: 0 10px;
}

nav ul li a {
    color: #fff;
    text-decoration: none;
}

nav ul li a:hover {
    text-decoration: underline;
}

/* Main content styling */
main {
    background: #fff;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

section {
    margin-bottom: 20px;
}

section h2 {
    margin-bottom: 10px;
}

/* Contact form styling */
form {
    margin-top: 20px;
    display: flex;
    flex-direction: column;
}

form label {
    margin-top: 10px;
}

form input, form textarea {
    margin-top: 5px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

form button {
    margin-top: 10px;
    padding: 10px;
    border: none;
    border-radius: 5px;
    background: #50b3a2;
    color: #fff;
    cursor: pointer;
}

form button:hover {
    background: #3e8c80;
}

/* Comments section styling */
#comments-section {
    margin-top: 20px;
}

#comments-list {
    margin-top: 10px;
    padding: 10px;
    background: #f4f4f4;
    border-radius: 5px;
}

.comment {
    margin-bottom: 10px;
    padding: 10px;
    background: #fff;
    border: 1px solid #ccc;
    border-radius: 5px;
}

/* Footer styling */
footer {
    text-align: center;
    padding: 10px 0;
    background: #333;
    color: #fff;
    border-radius: 5px;
}

/* Responsive design */
@media (max-width: 768px) {
    body {
        padding: 10px;
    }

    header, main, footer {
        padding: 10px;
    }

    nav ul {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    nav ul li {
        margin: 5px 0;
    }
}

@media (max-width: 480px) {
    header h1 {
        font-size: 1.5em;
    }

    nav ul li {
        display: block;
        margin: 5px 0;
    }

    main {
        padding: 10px;
    }

    section {
        margin-bottom: 15px;
    }

    footer {
        padding: 5px 0;
    }
}


 //javaScript
document.addEventListener('DOMContentLoaded', function () {
    const commentForm = document.getElementById('comment-form');
    const commentsList = document.getElementById('comments-list');

    commentForm.addEventListener('submit', function (event) {
        event.preventDefault();

        
        const name = document.getElementById('name').value.trim();
        const email = document.getElementById('email').value.trim();
        const comment = document.getElementById('comment').value.trim();


        if (name === '' || email === '' || comment === '') {
            alert('All fields are required.');
            return;
        }


        const commentElement = document.createElement('div');
        commentElement.classList.add('comment');
        commentElement.innerHTML = `<p><strong>${name}</strong> (${email})</p><p>${comment}</p>`;

    
        commentsList.appendChild(commentElement);

     
        commentForm.reset();
    });
});
