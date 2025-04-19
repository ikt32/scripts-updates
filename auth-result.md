# Authentication result

<h2 id="auth-status">Processing...</h2>
<p id="auth-message" class="info-box"></p>
<p id="explorer-help-container"></p>

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

        const troubleshootLink = '<a href="faq#license-generator-troubleshooting" target="_blank">"License Generator troubleshooting" section of the FAQ</a>'
        const supportLink = '<a href="https://discord.gg/VrrAEV4j4b" target="_blank">Discord</a>';
        const authFiles = `
            <code
                class="language-plaintext highlighter-rouge"
                style="cursor: pointer; text-decoration: underline;"
                onclick="toggleInstructions()"
                title="Click for help"
            >%localappdata%\\ikt\\License</code>
        `;

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
                ${reasonText}<br><br><br>
                Please consult the ${troubleshootLink} before asking for help.<br><br>
                If the issue persists, help is available via ${supportLink}.<br>
                <code>LicenseGenerator.log</code> from ${authFiles} is <b><u>mandatory</u></b>
                when asking for help.
            `;
        }

        statusElement.textContent = statusText;
        statusElement.className = boxClass;
        messageElement.className = `info-box ${boxClass}`;
        messageElement.innerHTML = message;

        const helpContainer = document.getElementById("explorer-help-container");
        helpContainer.innerHTML = ''; // Clear any previous render

        if (status !== "success") {
            const helpBox = document.createElement("div");
            helpBox.id = "explorer-help";
            helpBox.className = "info-subbox";
            helpBox.style.display = "none";
            helpBox.innerHTML = `
                <b>Opening the path:</b><br>
                <ul>
                    <li>Open <i>File Explorer</i></li>
                    <li>Click in the address bar<br></li>
                    <li>Paste <code>%localappdata%\\ikt\\License</code></li>
                    <li>Press <kbd>Enter</kbd></li>
                </ul>
                <code>LicenseGenerator.log</code> is required to receive proper
                support!
            `;
            helpContainer.appendChild(helpBox);
        }
    }

    function toggleInstructions() {
        const helpBox = document.getElementById("explorer-help");
        if (helpBox.style.display === "none") {
            helpBox.style.display = "block";
        } else {
            helpBox.style.display = "none";
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

    .info-subbox {
        background-color: #fff4cc;
        border: 1px solid #e6b800;
        padding: 10px;
        border-radius: 6px;
        font-size: 0.95em;
    }
</style>
