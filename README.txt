Railway deployment notes

1. Upload the contents of this folder to a GitHub repository.
2. Deploy the repository on Railway.
3. Ensure the service start command is: php -S 0.0.0.0:$PORT index.php
4. Once Railway assigns a public HTTPS domain, set the Telegram webhook to that domain root:
   https://api.telegram.org/bot<YOUR_BOT_TOKEN>/setWebhook?url=https://<YOUR-RAILWAY-DOMAIN>/
5. Check webhook status:
   https://api.telegram.org/bot<YOUR_BOT_TOKEN>/getWebhookInfo

The bot code was adjusted for the two syntax errors and for initial data-file creation. The code's legacy command behavior has not been exhaustively tested against a live Telegram bot. Railway's ephemeral filesystem can reset local text data after redeploy/restart; use a persistent volume or database if the bot's settings must survive those events.
