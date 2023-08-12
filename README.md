# Python_Bot

Python sanal ortamı oluşturmak için aşağıdaki adımları izleyebilirsiniz:

```
sudo apt update
sudo apt install python3
python3 --version
```

Sanal ortamı oluşturmak için venv modülünü yükleyin:

```
sudo apt install python3-venv

```


Çalışma dizininize gidin (örneğin, ~/Documents/bot_dizini):
cd ~/Documents/bot_dizini

Sanal ortamı oluşturun:

```
python3 -m venv bot-env

```

Sanal ortamı etkinleştirin:

```

source bot-env/bin/activate

```


Artık sanal ortam etkinleştirilmiş durumda ve sanal ortamda çalışıyorsunuz. Şimdi gerekli Python paketlerini yükleyebilirsiniz, örneğin:


```
pip install discord.py

```


Artık Python sanal ortamı etkinleştirilmiş durumda ve gerekli paketleri yükleyebilirsiniz. Bu, proje bağımlılıklarınızı izole etmek ve çakışmaları önlemek için iyi bir uygulamadır.

Python scriptini çalıştırmak için python3 bot.py komutunu kullanıyorsunuz. Scriptin çalışmasını durdurmak için CTRL+C tuş kombinasyonunu kullanabilirsiniz. Bu kombinasyonu kullanarak çalışan bir Python scriptini durdurabilir ve programın çalışmasını sonlandırabilirsiniz.


```
mkdir python3 bot.py      
cd python3 bot.py      
nano python3 bot.py      
```

```
import requests
import random
import time

def send_message():
    payload = {
        'content': "message"
    }

    headers = {
        'authorization': 'OTQzMDk5MTM5ODUwMzc5Mjfgwekufwıfhfhelkgejglehgeıghekgeelklefh'
    }

    response = requests.post('https://discord.com/api/v9/channels/1..........', json=payload, headers=headers)
    if response.status_code == 200:
        print("Message sent successfully")
    else:
        print("Failed to send message")

def reply_to_random_user():
    headers = {
        'authorization': 'OTQzMDk5MTM5ODUwMzc5MjY1.Gs2A27.Ko_Y5pdWbcFa699AE1fdjfbkjglejgpeog'
    }

    response = requests.get('https://discord.com/api/v9/channels/........', headers=headers)
    if response.status_code == 200:
        messages = response.json()
        if messages:
            random_message = random.choice(messages)
            user_id = random_message['author']['id']
            reply_content = f"Hi <@{user_id}>!"
            payload = {
                'content': reply_content
            }
            reply_response = requests.post('https://discord.com/api/v9/channels/1092781743066591252/messages', json=payload, headers=headers)
            if reply_response.status_code == 200:
                print(f"Replied to user {user_id} with message: {reply_content}")
            else:
                print(f"Failed to reply to user {user_id}")
        else:
            print("No messages found in the channel")
    else:
        print("Failed to fetch messages from the channel")

while True:
    send_message()
    reply_to_random_user()
    time.sleep(7200)  # 2 saatlik bekleme süresi (7200 saniye)
  ```
başlatmak için

```

python3 bot.py  

```
