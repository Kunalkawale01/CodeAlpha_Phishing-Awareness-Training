# CodeAlpha_Phishing-Awareness-Training

# Build a full phishing awareness online module and zip it

    import os
    import zipfile
    from textwrap import dedent

    base_dir = "/mnt/data/phishing_awareness_training"
    os.makedirs(base_dir, exist_ok=True)

    files = {
    "index.html": dedent("""
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Phishing Awareness Training</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Phishing Awareness Training</h1>
        <section>
            <h2>What is Phishing?</h2>
            <p>Phishing is a cyber attack where attackers trick users into revealing sensitive information.</p>
        </section>

        <section>
            <h2>How to Recognize Phishing Emails & Fake Websites</h2>
            <ul>
                <li>Urgent or threatening language</li>
                <li>Suspicious sender addresses</li>
                <li>Spelling and grammar mistakes</li>
                <li>Fake login pages</li>
            </ul>
        </section>

        <section>
            <h2>Social Engineering Tactics</h2>
            <ul>
                <li>Fear and urgency</li>
                <li>Authority impersonation</li>
                <li>Too-good-to-be-true offers</li>
            </ul>
        </section>

        <section>
            <h2>Best Practices to Stay Safe</h2>
            <ul>
                <li>Verify links before clicking</li>
                <li>Do not share OTPs or passwords</li>
                <li>Enable two-factor authentication</li>
            </ul>
        </section>

        <section>
            <h2>Real-World Example</h2>
            <p>An email pretending to be from a bank asks you to verify your account via a fake link.</p>
        </section>

        <section>
            <h2>Interactive Puzzle</h2>
            <p>Is this email phishing?</p>
            <button onclick="checkAnswer(true)">Yes</button>
            <button onclick="checkAnswer(false)">No</button>
            <p id="result"></p>
        </section>

        <script src="script.js"></script>
    </body>
    </html>
    """),

    "style.css": dedent("""
    body {
        font-family: Arial, sans-serif;
        margin: 40px;
        background: #f4f6f8;
    }
    h1 {
        color: #2c3e50;
    }
    section {
        background: white;
        padding: 20px;
        margin-bottom: 20px;
        border-radius: 8px;
    }
    button {
        padding: 10px 15px;
        margin: 5px;
        cursor: pointer;
    }
    """),

    "script.js": dedent("""
    function checkAnswer(isPhishing) {
        const result = document.getElementById("result");
        if (isPhishing) {
            result.innerText = "Correct! This is a phishing attempt.";
            result.style.color = "green";
        } else {
            result.innerText = "Incorrect. Look for warning signs like urgency and fake links.";
            result.style.color = "red";
        }
    }
    """),

    "README.md": dedent("""
    # Phishing Awareness Training Module

    ## How to Run
    1. Unzip the folder
    2. Open index.html in a browser

    ## Features
    - Phishing awareness content
    - Social engineering explanation
    - Real-world example
    - Interactive puzzle
    """)
}

# files
for name, content in files.items():
    with open(os.path.join(base_dir, name), "w") as f:
        f.write(content)

## Run the Project on Linux

step 1: Go Inside the Project Folder

    cd phishing_awareness_training

step 2: Using Python 3

    python3 -m http.server 8000

step 3: Then open in browser:

    http://localhost:8000
