#LogiTalk — Чат-Клієнт

##📝Це легкий графічний чат-клієнт, створений на базі customtkinter і socket, 
який дозволяє підключатися до віддаленого сервера через TCP та обмінюватися повідомленнями в реальному часі.

##🛠Що тут використано?
###Python — мова, якою це все написано.

###customtkinter — для створення красивого вікна.

###socket — щоб відправляти і приймати повідомлення через інтернет.

###threading — щоб отримання повідомлень не зависало програму.

###ngrok — щоб підключитись до сервера через інтернет (адресу можна змінювати).


#🧩 Маленький шматочок коду, пояснений просто
##🔌 Підключення до сервера

###self.sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
###self.sock.connect(("7.tcp.eu.ngrok.io", 19348))
###Створюється з’єднання з сервером.

##💌 Надсилання повідомлення

###message = self.message_input.get().strip()
###formatted_message = f"TEXT@{self.username}@{message}\n"
###self.sock.send(formatted_message.encode("utf-8"))
###Коли ти щось пишеш — воно упаковується в текст з ім’ям і надсилається на сервер. Інші учасники бачать це в себе.

##🎧 Отримання повідомлень

###self.receive_thred = threading.Thread(target=self.receive_massage, daemon=True)
###self.receive_thred.start()
###Окремий потік постійно слухає нові повідомлення.

