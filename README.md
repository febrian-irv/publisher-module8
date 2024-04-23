# Understanding publisher and message broker reflection

1. How many data your publlsher program will send to the message broker in one run? 
Terdapat 5 data yang dikirimkan oleh publisher program. Pengiriman data terlihat dari method 'publish_event' yang dijalankan 5 kali pada fn main untuk 5 user berbeda.

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Kesamaan ini mengartikan bahwa untuk program publisher dan program publisher terkoneksi pada instance amqp yang sama. Hal tersebut menunjukkan antara program publisher dan subscriber dapat saling berkomunikasi. Dari fakta tersebut maka dapat terlihat dari source code bahwa ketika program publisher membuat event 'user_created' maka akan dilisten dan mentrigger program subscriber untuk melakukan event handling pada program tersebut.

# Preparing message broker (RabbitMQ)
#### Screen of running rabbit:
![](msc/running_rabbit.png)

#### Sending and Processing Event
1. Publisher console:
![](msc/publisher.png)
2. Subscriber console:
![](msc/subscriber.png)
Pada gambar diatas publisher melakukan run program dengan mempublish event pada url dan port yang telah ditentukan pada source code dengan nama user_created berisi message mengenai user yang dibuat. Setelah itu, pada subscriber yang telah di run terlebih dahulu telah melakukan listening pada url dan port sehingga ketika terdapat kiriman data pada port tersebut maka subscriber melakukan event handling. Dalam kasus ini, subscriber melakukan event handling pada user_created dengan melakukan print message yang telah dikirimkan.