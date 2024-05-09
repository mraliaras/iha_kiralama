Özellikler
· Üyelik ve Giriş Sistemi
· Yönetici ve Kullanıcı Rollerinin Yönetimi
· Yöneticiler için İHA (İnsansız Hava Aracı) Ekleme, Düzenleme, Silme ve Ajax ile Listeleme
· Yöneticiler için Kullanıcı Ekleme, Düzenleme, Silme ve Ajax ile Listeleme
· Yöneticiler için İHA Kiralamalarını Ajax ile Listeleme
· Çeşitli İHA Özelliklerinin Yönetimi
· Kullanıcılar için İHA Arama, Ajax ile Listeleme ve Kiralama
· Kullanıcılar için Kiralamalarının Arama, Ajax ile Listeleme ve İptal Etme
· İHA'ların tarih ve adet verilerine göre müsaitlik durumunun kontrol edilmesi
· Tüm datatables tablolarında arama, sayfalama, excel, yazdırma ve pdf çıktı alma fonksiyonları
· Birim Testleri
· İşlevsellikler için ek Django kütüphaneleri

Kurulum
Gerekli bağımlılıkların yüklenmesi için bir sanal ortam oluşturun. (virtualenv veya venv kullanarak)
Projeyi klonlayın

git clone https://github.com/mraliaras/iha_kiralama.git
Proje dizine gidin
Proje bağımlılıklarını yükleyin

pip install -r requirements.txt
setting.py dosyasında veritabanı bağlantısı ayarlarınızı yapın.

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'ihadb',  # PostgreSQL veritabanı adı
        'USER': 'postgres',  # PostgreSQL kullanıcı adı
        'PASSWORD': 'postgres',  # PostgreSQL şifre
        'HOST': 'localhost',  # Yerel PostgreSQL sunucusu
        'PORT': '5432',  # PostgreSQL port numarası
    }
}
Çalıştıralım

 python manage.py runserver
Projeyi başlattığınızda, veritabanı tabloları otomatik olarak oluşturulur ve gerekli migration işlemleri uygulanır.

İlk kullanıcıyı oluşturmak için kaydolun ve PostgreSQL veritabanı üzerinden kullanıcının yetkisini belirlemek üzere "is_staff" sütununu kullanarak yönetici olarak tanımlayabilirsiniz. Yönetici olan kullanıcılar, normal kullanıcılardan farklı özelliklere sahiptir. Bu özellikler arasında, kayıtları ekleme, silme, güncelleme gibi temel işlemleri gerçekleştirme yetkisi bulunmaktadır.

Yöneticiler, ayrıca kiralanan ihaleleri takip etme gibi özel yetkilere sahiptir. Bu özellikler sayesinde, projede yer alan kayıtların kontrolünü daha etkili bir şekilde yönetebilirler. Ayrıca, projede yer alan kullanıcıların gerçekleştirdiği ekleme, silme, güncelleme gibi işlemleri görüntüleme yetkisi ile kullanıcı aktivitelerini takip edebilirler.

Bu sayede, yönetici olan kullanıcılar projedeki veri yönetimini etkili bir şekilde gerçekleştirebilir ve güvenliği sağlayabilir.
