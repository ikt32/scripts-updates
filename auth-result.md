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

        let statusText = "Processing...";
        let boxClass = "";
        let message = "";

        if (status === "success") {
            statusText = "Authentication succeeded!";
            boxClass = "success";
            message = "Congratulations, you're eligible!<br>"+
                "Your license is being generated.<br><br>"+
                "This page may be closed now.";
        }
        else {
            statusText = "Authentication failed";
            boxClass = "failed";

            let reasonText;
            switch (reason) {
                case "authorization":
                    reasonText = "Authorization failed.<br>"+
                    "The application was not authorized and could not retrieve user details from Patreon.";
                    break;
                case "authentication":
                    reasonText = "Authentication failed.<br>"+
                    "The application could not retrieve the required user details from Patreon.";
                    break;
                case "not-eligible":
                    reasonText = "Unfortunately, you do not seem eligible at this time.<br>"+
                    "Please ensure you have an active pledge with the "+
                    "<b>Supporter</b> tier <a href=\"https://patreon.com/ikt\">on Patreon</a>.";
                    break;
                default:
                    statusText = "Invalid status";
                    reasonText = "No or unrecognized status code.";
                    break;
            }

            message = `
                ${reasonText}<br><br>
                Please check the ${faqLink} for tips and information.<br>
                Need help? Reach out on ${supportLink}.<br>
                Please include files from ${authFiles}.
            `;
        }

        statusElement.textContent = statusText;
        statusElement.className = boxClass;
        messageElement.className = `info-box ${boxClass}`;
        messageElement.innerHTML = message;
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
