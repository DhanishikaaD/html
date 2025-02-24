<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Feedback Form</title>
    <style>
        body { font-family: Arial, sans-serif; max-width: 400px; margin: auto; padding: 20px; text-align: center; }
        input, textarea { width: 100%; padding: 10px; margin: 10px 0; border: 1px solid #ccc; }
        button { padding: 10px; background: green; color: white; border: none; cursor: pointer; }
        .success { color: green; display: none; margin-top: 10px; }
    </style>
</head>
<body>

    <h2>Feedback Form</h2>
    <input type="text" id="name" placeholder="Your Name">
    <input type="email" id="email" placeholder="Your Email">
    <textarea id="feedback" placeholder="Your Feedback" rows="4"></textarea>
    <button onclick="submitFeedback()">Submit</button>
    <p class="success">Thank you for your feedback! ✅</p>

    <script>
        function submitFeedback() {
            let name = document.getElementById("name").value.trim();
            let email = document.getElementById("email").value.trim();
            let feedback = document.getElementById("feedback").value.trim();
            let successMessage = document.querySelector(".success");

            if (name === "" || email === "" || feedback === "") {
                alert("Please fill in all fields.");
                return;
            }

            if (!email.includes("@") || !email.includes(".")) {
                alert("Enter a valid email.");
                return;
            }

            successMessage.style.display = "block";
            document.getElementById("name").value = "";
            document.getElementById("email").value = "";
            document.getElementById("feedback").value = "";
        }
    </script>

</body>
</html>
