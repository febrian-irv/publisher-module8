# Understanding publisher and message broker reflection

1. How many data your publlsher program will send to the message broker in one run? 
Terdapat 5 data yang dikirimkan oleh publisher program. Pengiriman data terlihat dari method 'publish_event' yang dijalankan 5 kali pada fn main untuk 5 user berbeda.

2. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Kesamaan ini mengartikan bahwa untuk program publisher dan program publisher terkoneksi pada instance amqp yang sama. Hal tersebut menunjukkan antara program publisher dan subscriber dapat saling berkomunikasi. Dari fakta tersebut maka dapat terlihat dari source code bahwa ketika program publisher membuat event 'user_created' maka akan dilisten dan mentrigger program subscriber untuk melakukan event handling pada program tersebut.