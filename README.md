Özellikler
1) Üyelik ve Giriş Özelliği
2) Admin ve Kullanıcı Rolü
3) Adminler için IHA Ekleme, Düzenleme, Silme, Ajax Listeleme
4) Adminler için Kullanıcı Ekleme, Düzenleme, Silme, Ajax Listeleme
5) Adminler için IHA Kiralamarını Ajax ile Listeleme
6) Çeşitli IHA Özellikleri
7) Kullanıcılar için IHA Arama, Ajax Listeleme, Kiralama
8) Kullanıcılar için Kiralamalarını Arama, Ajax Listeleme, İptal Etme
9) IHAları tarih ve adet verisine göre müsaitlik durumu kontrol etme
11) Tüm datatable tablolarda arama, pagination, excel, print, pdf çıktı alma fonksiyonları
12) Birim testleri
13) İşlevsellikler için ekstra Django kütüphaneleri

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

Örnek Kullanıcılar:
Yönetici: admin@local.com - password: admin
Kullanıcı user@local.com - password: user

İlk kullanıcıyı oluşturmak için kaydolun ve PostgreSQL veritabanı üzerinden kullanıcının yetkisini belirlemek üzere "is_staff" sütununu kullanarak yönetici olarak tanımlayabilirsiniz. Yönetici olan kullanıcılar, normal kullanıcılardan farklı özelliklere sahiptir. Bu özellikler arasında, kayıtları ekleme, silme, güncelleme gibi temel işlemleri gerçekleştirme yetkisi bulunmaktadır.

Yöneticiler, ayrıca kiralanan ihaleleri takip etme gibi özel yetkilere sahiptir. Bu özellikler sayesinde, projede yer alan kayıtların kontrolünü daha etkili bir şekilde yönetebilirler. Ayrıca, projede yer alan kullanıcıların gerçekleştirdiği ekleme, silme, güncelleme gibi işlemleri görüntüleme yetkisi ile kullanıcı aktivitelerini takip edebilirler.

Bu sayede, yönetici olan kullanıcılar projedeki veri yönetimini etkili bir şekilde gerçekleştirebilir ve güvenliği sağlayabilir.
