TCP'nin çalışma esası üç faz altında incelenebilir: 1) Öncelikle hedefle bir bağlantı gerçekleşir. 2) Bağlantı gerçekleştikten sonra veri transferi yapılır. 3) Veri transferi yapıldıktan sonra da bağlantı sona erdirilir.

TCP'de bu üç fazın gerçekleşmesi için bazı ara durumlar (state) tanımlanmıştır. Bu durumlar aşağıdaki gibidir:[6][7][8]

LISTEN

(sunucu) İstemci tarafından bir TCP bağlantı isteğinin beklenildiği durum

SYN-SENT

(istemci) Karşı tarafa TCP bağlantısı isteği gönderildikten sonra karşı taraftan bağlantı isteğine cevap beklenilen durum

SYN-RECEIVED

(sunucu) İstemci tarafından SYN bayrağı ile yapılan bağlantı isteğine sunucunun SYN-ACK bayrağı ile cevap vermesinden sonraki bekleme durum

ESTABLISHED

(sunucu ve istemci) Bağlantı kurulduktan sonraki veri transferinin yapıldığı durum

FIN-WAIT-1

(sunucu ve istemci)

FIN-WAIT-2

(sunucu ve istemci) karşı taraftan TCP bağlantısının bitirilme isteğinin beklendiği durum

CLOSE-WAIT

(sunucu ve istemci)

CLOSING

(sunucu ve istemci) Karşı tarafa bağlantının bitirilmesine dair bir ACK bayrağı gönderildikten sonra bağlantının bitmesini bekleme durumu

LAST-ACK

(sunucu ve istemci)

TIME-WAIT

(sunucu ve istemci)

CLOSED

(sunucu ve istemci) TCP bağlantısının tamamen bittiği durum
TCP bağlantısı nasıl kurulur?

A bilgisayarı B bilgisayarına TCP yoluyla bağlanmak istediğinde şu yol izlenir:

    A bilgisayarı B bilgisayarına TCP SYNchronize mesajı yollar
    B bilgisayarı A bilgisayarının isteğini aldığına dair bir TCP SYN+ACKnowledgement mesajı yollar
    A bilgisayarı B bilgisayarına TCP ACK mesajı yollar
    B bilgisayarı bir ACK "TCP connection is ESTABLISHED" mesajı alır

Üç zamanlı el sıkışma adı verilen bu yöntem sonucunda TCP bağlantısı açılmış olur.[9]
Veri iletimi

TCP'de veri iletimi çift yönlüdür. Yani her iki taraf da birbirlerine aynı bağlantı içerisinde veri gönderebilmektedir.[10]

Bağlantı oluşturulduktan sonra, B bilgisayarı A bilgisayarından paketler almaya başlar. B, her aldığı paketten sonra bir süre bekledikten sonra en son düzgün olarak aldığı paket grubunu A'ya bildirir. Gelen bildirimlere göre A, daha sonra hangi paketleri yollaması gerektiğine karar verir ve yollar.
TCP bağlantısının sona erdirilmesi

Veri iletişimi bitince bilgisayarlardan herhangi biri diğerine TCP kapatma mesajı yollar. Diğer bilgisayar, kapatmayı teyit etme paketi ve kapatma isteği yollar. Son olarak, diğer bilgisayar da kapatma teyidini yollar ve bağlantı kapatılmış olur.

Bu işlemin adımları tam olarak şöyledir:

    A bilgisayarı B bilgisayarına bağlantıyı sonlandırmak istediğine dair TCP FIN mesajı yollar.
    B bilgisayarı A bilgisayarına bağlantı sonlandırma isteğini aldığına dair TCP ACK mesajı yollar.
    B bilgisayarı A bilgisayarına bağlantıyı sonlandırmak istediğine dair TCP FIN mesajı yollar.
    A bilgisayarı B bilgisayarına bağlantı sonlandırma isteğini aldığına dair TCP ACK mesajı yollar.

Bu işlemlerin sonunda TCP bağlantısı sonlandırılmış olur. Buna 4 zamanlı el sıkışma denir.[11]

Görüldüğü üzere, bağlantının kurulmasından farklı olarak bağlantı her cihaz için ayrıca kapatılmaktadır. Bunun nedeni, istenildiğinde bağlantının tek yönlü olarak açık tutulabilmesini sağlamaktır. Bunun için tek tarafın bağlantı kapama adımlarını gerçekleştirmesi gerekir.
TCP Segmenti

TCP bağlantı tabanlı (connection-oriented) bir protokoldür.[12] TCP bağlantı tabanlı bir protokol olduğu için iki bilgisayar, üçlü el sıkışma (3-way handshaking)[13][14] yaptıktan sonra veri alışverişi yapmaya başlar.

TCP, taşıma katmanında alt katmandan gelen verilere bir başlık bilgisi ekler. Başlık bilgisiyle birlikte bu veriye 'TCP Segmenti' denir. 
