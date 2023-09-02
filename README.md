- 👋 Hi, I’m @dibakane
- i👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
dibakane/dibakane is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
mport requests
import json

def send_message(message):
    params = {
        'access_token': '<your_page_access_token>',
        'message': message
    }
    response = requests.post('https://graph.facebook.com/v12.0/me/messages', params=params)
    if response.status_code == 200:
        print("Message sent successfully!")
    else:
        print("Failed to send message.")

def receive_message():
    data = request.get_json()
    if data['object'] == 'page':
        for entry in data['entry']:
            for messaging_event in entry['messaging']:
                if messaging_event.get('message'):
                    sender_id = messaging_event['sender']['id']
                    message_text = messaging_event['message']['text']
                    # Process the received message
                    process_message(sender_id, message_text)

def process_message(sender_id, message_text):
    # Your custom logic goes here
    response_message = "I received your message: " + message_text
    send_message(sender_id, response_message)

if __name__ == '__main__':
    # Set up a webhook to receive messages
    # More details on setting up webhook: https://developers.facebook.com/docs/messenger-platform/getting-started/webhook-setup/
    # Ensure that your webhook URL points to your server running this script
    # You will also need a valid Page Access Token
    app.run(debug=True)
