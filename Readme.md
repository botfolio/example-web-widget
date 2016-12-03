
# example-webapp-chatbot
This is an web page that embed a botfolio chatbot.


## Init Botfolio Web Widget using Javascript

```js
 <script>
        window.botfolioSettings = {
            bot_token: "<YOUR_CHATBOT_API_TOKEN>",
            first_name: "<LOGGEDIN_USER_FIRSTNAME>",
            last_name: "<LOGGEDIN_USER_LASTNAME>",
            extra_data: {actorId:5}, //Your custom user data  information as json object variable
            onMessage: function (message) { // Callback event that is triggered when new message is came
                console.log(message);
            },
            unreadCount: function (count) { // Callback event that is triggered on load for unread messages count
                console.log(count);
            }
        };
    </script> 

    <script>
        (function () {
            function botfolio() {
                var s = document.createElement('script');
                s.type = 'text/javascript';
                s.async = true;
                s.src = 'https://developers.botfoli.io/scripts/plugin/embed';
                document.body.appendChild(s);
            }
            if (window.attachEvent)
                window.attachEvent('onload', botfolio);
            else
                window.addEventListener('load', botfolio, false);
        }());
    </script>

    <div id="botfolio_widget" style="height:500px; position:fixed; bottom:0; right: 30px; width: 900px; height: 600px;"></div>
```