IHA Kiralama Sistemi
Bu proje, İnsansız Hava Araçları (İHA) kiralama işlemlerini yönetmek için bir Django web uygulamasıdır. Aşağıda, projenin temel özellikleri ve kurulum adımları bulunmaktadır:

Özellikler
Üyelik ve giriş sistemi
Admin ve kullanıcı rolleri
Adminler için İHA ekleme, düzenleme, silme ve Ajax ile listeleme
Adminler için kullanıcı ekleme, düzenleme, silme ve Ajax ile listeleme
Adminler için İHA kiralama işlemlerini Ajax ile listeleme
Çeşitli İHA özellikleri
Kullanıcılar için İHA arama, Ajax ile listeleme ve kiralama
Kullanıcılar için kiralama işlemlerini arama, Ajax ile listeleme ve iptal etme
İHA'ların müsaitlik durumunu tarih ve adet verisine göre kontrol etme
Tüm tablolarda arama, sayfalama, Excel, yazdırma ve PDF çıktısı alma işlevleri
Birim testleri
İşlevsellikler için ek Django kütüphaneleri

Kurulum
1. Gerekli bağımlılıkların yüklenmesi için bir sanal ortam oluşturun (örneğin, virtualenv veya venv kullanarak).

2. Projeyi klonlayın:
git clone https://github.com/mraliaras/iha_kiralama.git

3. Proje dizinine gidin ve proje bağımlılıklarını yükleyin:
cd iha_kiralama
pip install -r requirements.txt

4. settings.py dosyasında veritabanı bağlantısı ayarlarınızı yapın:
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'ihadb',       # PostgreSQL veritabanı adı
        'USER': 'postgres',    # PostgreSQL kullanıcı adı
        'PASSWORD': 'postgres',# PostgreSQL şifre
        'HOST': 'localhost',   # Yerel PostgreSQL sunucusu
        'PORT': '5432',        # PostgreSQL port numarası
    }
}

5. Uygulamayı çalıştırın:
python manage.py runserver

Projeyi başlattığınızda, veritabanı tabloları otomatik olarak oluşturulur ve gerekli migration işlemleri uygulanır.


Örnek Kullanıcılar

1. Yönetici: admin@local.com - Şifre: admin

2. Kullanıcı: user@local.com - Şifre: user


İlk kullanıcıyı oluşturduktan sonra, PostgreSQL veritabanı üzerinden kullanıcının "is_staff" sütununu kullanarak yönetici olarak tanımlayabilirsiniz. Yönetici olan kullanıcılar, normal kullanıcılardan farklı yetkilere sahiptir. Bu yetkiler arasında, kayıtları ekleme, silme, güncelleme gibi temel işlemler bulunmaktadır. Ayrıca, yöneticiler İHA kiralama işlemlerini takip etme gibi özel yetkilere sahiptir.

Bu sayede, yönetici olan kullanıcılar projedeki veri yönetimini etkili bir şekilde gerçekleştirebilir ve güvenliği sağlayabilir.

Docker ile Çalıştırma
Bu projeyi Docker kullanarak çalıştırmak için aşağıdaki adımları izleyebilirsiniz:

1. İlk olarak, Docker'ın bilgisayarınızda yüklü olduğundan emin olun. Docker'ı resmi web sitesinden indirebilirsiniz.

2. Proje dizinine gidin ve Docker container'ınızı oluşturun:
docker-compose up -d --build

3. Docker container'ı başlatıldıktan sonra, web uygulamasına tarayıcınızdan http://localhost:8000 adresinden erişebilirsiniz.

4. Docker container'ını durdurmak ve kaldırmak için aşağıdaki komutu kullanabilirsiniz:
docker-compose down


