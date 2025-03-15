# Authentication result

<h2 id="auth-status">Processing...</h2>
<p id="auth-message" class="info-box"></p>

<script>
    function getQueryParams() {
        const params = new URLSearchParams(window.location.search);
        return {
            status: params.get("status"),
            reason: params.get("reason")
        };
    }

    function displayMessage() {
        const { status, reason } = getQueryParams();
        const statusElement = document.getElementById("auth-status");
        const messageElement = document.getElementById("auth-message");

        const faqLink = '<a href="faq" target="_blank">FAQ</a>';
        const supportLink = '<a href="https://discord.gg/VrrAEV4j4b" target="_blank">Discord</a>';
        const authFiles = '<code class="language-plaintext highlighter-rouge">%localappdata%\\ikt\\License</code>'

        if (status === "success") {
            statusElement.textContent = "Authentication succeeded!";
            statusElement.className = "success";
            messageElement.className = "info-box success";
            messageElement.innerHTML = "Your license is being generated. You may close this page.";
        } else if (status === "failure") {
            statusElement.textContent = "Authentication failed";
            statusElement.className = "failed";
            messageElement.className = "info-box failed";

            let reasonText = "An unknown error occurred.";
            if (reason === "authorization") {
                reasonText = "Authorization failed.<br>"+
                    "The application was not authorized and could not retrieve user details from Patreon.";
            } else if (reason === "authentication") {
                reasonText = "Authentication failed.<br>"+
                    "The application could not retrieve the required user details from Patreon.";
            } else if (reason === "not-eligible") {
                reasonText = "Unfortunately you do not seem eligible at this time.<br>"+
                    "Please ensure you have an active pledge on Patreon.";
            }

            messageElement.innerHTML = `
                ${reasonText}<br><br>
                Please check the ${faqLink} for tips and information.<br>
                Need help? Reach out on ${supportLink}.<br>
                Please include files from ${authFiles}.
            `;
        }
        else {
            statusElement.textContent = "Invalid status";
            statusElement.className = "failed";
            messageElement.className = "info-box failed";

            let reasonText = "No or unrecognized status code.";
            messageElement.innerHTML = `
                ${reasonText}<br><br>
                Make sure your browser does not strip links.<br>
                Need help? Reach out on ${supportLink}.<br>
                Please include files from ${authFiles}.
            `;
        }
    }

    displayMessage();
</script>

<style>
    .success {
        color: green;
    }
    .failed {
        color: red;
    }
    .info-box {
        margin-top: 20px;
        padding: 15px;
        border-radius: 8px;
        display: inline-block;
    }
    .info-box.failed {
        background-color: #ffe6e6;
        border: 1px solid red;
    }
    .info-box.success {
        background-color: #e6ffe6;
        border: 1px solid green;
    }
    .info-box a {
        color: blue;
        text-decoration: none;
    }
    .info-box a:hover {
        text-decoration: underline;
    }
</style>
