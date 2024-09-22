# Containers in C++ STL (Standard Template Library)

<aside>
💡 Buraya başlamadan önce Big O Notations nedir bilmiyorsanız okumanızı tavsiye ederim. Sadece bir fikriniz olsun. (Low Level konusu biraz daha ama aşinalığınızın olması bu dökümantasyonu okurken anlamnızda kolaylık sağlıcaktır.) 

Küçük bir dip not daha : Dökümantasyon boyunca belirli noktada elimden geldiğimce örnekler vermeye çalıştım ancak daha detay bilgi isteyebileceğiniz noktalarda geekforgeeks linki bıraktım 😊. (Bunun nedeni her biri için örnek yazabilecek kadar müsait değilim.)

</aside>

Containerlar bir depolayıcıdıdır. STL içerisinde bulundunğundan anlıcağınız gibi template bazlı sınıflardan oluşan bir tutucudur. İstediğimiz tipte istedeğimiz verileri burada depolayabiliriz.

Normal bir array(dizi) kullanmaktan daha iyi olmasının nedeni ekleme çıkarma vb. yapabilir ve iteratorsler( işaretçilere benzer özelliklere sahip referans nesneleri) aracılığıyla erişmek için üye fonksiyonlarını bize sunar.

<aside>
💡 Hala kafan karışıksa devam etmeden önce dostum şimdilik şu şekilde düşünebilirsin:

Bir array düşün int ve içerisine veri depoladığını düşün ve kendin bunun içerisinde istediğin elemana ulaşmak için yazdığın fonksiyonların olduğunu ve onları kullanıyormuş gibi düşün.

</aside>

Containerlar farklı farklı türleri bulunmaktadır sıralı/sırasız/ilişkisel vb. şimdi bunlardan bahsederek devam edelim.

- **Sequence Containers (Sıra Containers)**
    
    Sırayla depolanan index mantığında sırayla verilere erişebildiğimiz container türleridir.
    
    - [**array](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1/Array%2085de6a3bcb6948a4914df74a659f84b1.md): Statik bitişik dizi (sınıf şablonu)**
    - [**vector](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1/Vector%20b577d501d42b4bfbb6b49a8990723469.md): Dinamik bitişik dizi (sınıf şablonu)**
    - [**list](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1/List%20fb66f15aaf314c5b945b03a79180046a.md):** Doubly-linked list (class template)
    - [**deque](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1/Deque%20(Head%20&%20Tail,%20Doubly%20Linked)%202742aab4601141f2b8a6a6152b1f9573.md):** Double-ended queue (class template)
- **Associative Containers (İlişkisel Containers)**
    
         Burada indexleme mantığı yoktur. İlişkisel containerlarda key-value mantığı vardır(Sadece set benzersiz keylerin saklandığı bir containerdır.).
    
         Her bir key bir value’yü işaret eder ve keyler benzersiz olmak zorundadır. O(log n) karmaşıklığına sahiptir. Bu karmaşıklık şunu anlatır. N kadar eleman varsa arama ona göre logoritmik olarak artar veya azalır. Verinin büyüklüğünün önemi yoktur kaç adet veri olduğunun önemi işlemin hızını etkiler.
    
    - [**Set:**](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1/Set%20(Ku%CC%88me)%20c19b9a49aed24d459148cb3ba580e316.md) Collection of unique keys, sorted by keys (class template)
    - [**multiset](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1/MultiSet%200ed6ea9ba393468bb068989aecabad4d.md):** Collection of keys, sorted by keys (class template)
    - [**Map](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1/Map%2012dc39db180a4b87ae978b52092c4205.md): Keylere göre sıralanmış key-value koleksiyonu** (class template).
    - [**multimap](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1/MultiMap%20e0442230764f4946acb32b99f62c1173.md):** Collection of key-value pairs, sorted by keys (class template)
- **Container adapters (Container Adaptörleri)**
    
    Konteyner adaptörleri sıralı konteynerler için farklı bir arayüz sağlar.
    
    <aside>
    💡 Şunu unutma adaptörler **container değildir ve** bu yüzden **iterator** sunmazlar.
    Bu nedenle STL sınıfına ait algoritmaları doğrudan containers adaptorleri çağıramaz/kullanamaz. Containers adaptorleri yalnızca sunulan arayüz ile kullanabiliyoruz. Stack içerisinde zaten bunu daha detaylı bir şekilde görüceksin. Ne demek istediğimi.
    
    </aside>
    
    - [**stack:**](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1/Stack%20785686561bd34e49ae4f21408b34bb98.md) Adapts a container to provide stack (LIFO data structure) (class template).
    - [**queue:**](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1/Queue%20b6c0cb2494924679971d0f20ff710b78.md) Adapts a container to provide queue (FIFO data structure) (class template).

[Containers DB](Containers%20in%20C++%20STL%20(Standard%20Template%20Library)%203e3aacce093c43249a0261f0f60d06e5/Containers%20DB%20f70598367c944bb9a229de5c2e3affe1.md)