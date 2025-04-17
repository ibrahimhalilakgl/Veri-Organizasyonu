# İlişkisel Cebir Sorguları

Her bir kitabın başlığını ve yılını listeleyiniz:
π(Başlık, yıl)(kitap)

Bölümü IIS olan öğrencilerin tüm bilgilerini listeleyiniz:
σ(bolum = 'IIS')(öğrenci)

Tüm öğrencileri ödünç aldıkları kitapların başlıklarıyla birlikte listeleyiniz:
π(ogrADI, Başlık)(öğrenci ⨝ odunc ⨝ kitap)

SAÜ tarafından 1990 yılından önce yayınlanan tüm kitapları listeleyiniz:
π(Başlık, yıl)(σ(yayıncı = 'SAÜ' ∧ yıl < 1990)(kitap))

Sakarya’da yaşayan yazarların isimlerini listeleyiniz:
π(yAdi)(σ(adres = 'Sakarya')(yazar))

30 yaşından büyük ve IIS bölümünde olmayan öğrencilerin adlarını listeleyiniz:
π(ogrADI)(σ(yas > 30 ∧ bolum ≠ 'IIS')(öğrenci))

YAdi alanını Adi olarak değiştiriniz:
ρ(Adi/yAdi)(yazar)

IIS’de okuyan ve bir kitap ödünç almış öğrencileri listeleyiniz:
π(ogrADI)(σ(bolum = 'IIS')(öğrenci ⨝ odunc))

‘Ali’ tarafından yazılan kitapların başlıklarını listeleyiniz (kartezyen çarpım ile):
π(Başlık)(σ(yAdi = 'Ali')(yazar ⨝ yazılmıs ⨝ kitap))

Ali tarafından yazılmış olup veritabanı anahtarını içermeyen kitapları listeleyiniz:
π(Başlık)(
  σ(yAdi = 'Ali')(yazar ⨝ yazılmıs ⨝ kitap)
  
  π(Başlık)(σ(Anahtar = 'veritabanı')(acıklama ⨝ kitap)))

Her bir kitabı, yalnızca anahtarlarıyla birlikte listeleyiniz (anahtarı olmayan kitaplar hariç):
π(Başlık, Anahtar)(kitap ⨝ acıklama)

Her öğrenciyi ödünç aldığı kitaplarla birlikte listeleyiniz:
π(ogrADI, Başlık)(öğrenci ⨝ odunc ⨝ kitap)

‘YASİN’ isimli yazarlar tarafından yazılmış kitapların başlıklarını listeleyiniz:
π(Başlık)(σ(yAdi = 'YASİN')(yazar ⨝ yazılmıs ⨝ kitap))

‘Veli’ isimli öğrencinin ödünç aldığı kitapların yazarlarını listeleyiniz:
π(yAdi)(σ(ogrADI = 'Veli')(öğrenci ⨝ odunc ⨝ kitap ⨝ yazılmıs ⨝ yazar))

Hem ‘veritabanı’ hem de ‘programlama’ anahtarlarına sahip kitapları listeleyiniz:
π(Başlık)(
  σ(Anahtar = 'veritabanı')(acıklama ⨝ kitap)
)
∩
π(Başlık)(
  σ(Anahtar = 'programlama')(acıklama ⨝ kitap)
)
