# Deque (Head & Tail, Doubly Linked)

Çift uçlu kuyruklar, her iki uçta da genişleme ve daralma özelliğine sahip dizi kaplarıdır. Vektörlere benzerler, ancak elemanların eklenmesi ve silinmesi durumunda daha verimlidirler. Vektörlerin aksine, bitişik depolama tahsisi garanti edilmeyebilir. (Ramde yanyana depolancakalırını garantilemez.)

Çift Uçlu Kuyruklar temel olarak çift uçlu kuyruk veri yapısının bir uygulamasıdır. Bir kuyruk veri yapısı sadece sondan eklemeye ve önden silmeye izin verir. Bu, insanların önden çıkarıldığı ve arkadan eklendiği gerçek hayattaki bir kuyruk gibidir. Çift uçlu kuyruklar, ekleme ve silme işlemlerinin her iki uçta da mümkün olduğu kuyrukların özel bir durumudur.
Deque için işlevler vektör ile aynıdır, hem ön hem de arka için push ve pop işlemleri eklenmiştir.

Dekler üzerinde çeşitli işlemler yapmak için zaman karmaşıklıkları şunlardır

Elemanlara Erişim- O(1)
Eleman ekleme veya çıkarma- O(N)
Başlangıçta veya sonda eleman ekleme veya çıkarma- O(1)

- **front() -**  Deque başında ki elemanın referansını döndürür.
- **back() -**  Deque sonunda ki elemanın referansını döndürür.
- **begin() -** Listenin başını gösteren bir iterator döndürür.
- **end() -** Listenin sonunu gösteren bir iterator döndürür.
- **empty() -** Eğer boşssa True değilse False döndürür.
- **clear() -** Tüm deque içerisini temizler
- **push_back() -** Deque’nin sonuna eleman ekler.
- **push_front() -** Deque’nin başına eleman ekler.
- **pop_front() -** Kuyruk başından eleman siler.
- **pop_back() -** Kuyruk sonundan eleman siler.
- **size() -** Deque’nin boyutunu geri döndürür.
- **erase()** - Listenin belirli bir yerinden belirli başka bir yerine kadar elemanları silmek için kullandığımız üye fonksiyonu. Tek bir pozisyon verirsek sadece o pozisyondaki elemanı silecektir.
- **insert()** – Belirlenen bir yere yeni bir eleman ekler.
- **swap() -** bir deque'in içeriğini aynı tip ve boyuttaki başka bir deque ile değiştirmek için kullanılır.
- **resize()** - Deque boyutunu yeniden belirleyebiliyoruz bu fonksiyon sayesinde.

<aside>
💡 Vectordeki bir çok iterator fonksiyonları burada da çalışır durumdadır. Daha fazlası için [tıklayıp sayfanın altında ki tabloyu inceleyebilirsin.](https://www.geeksforgeeks.org/deque-cpp-stl/)

</aside>

```cpp
#include <deque>
#include <iostream>

using namespace std;

void showdq(deque<int> g)
{
	deque<int>::iterator it;
	for (it = g.begin(); it != g.end(); ++it)
		cout << '\t' << *it;
	cout << '\n';
}

int main()
{
	deque<int> gquiz;
	gquiz.push_back(10);
	gquiz.push_front(20);
	gquiz.push_back(30);
	gquiz.push_front(15);
	cout << "The deque gquiz is : ";
	showdq(gquiz);

	cout << "\ngquiz.size() : " << gquiz.size();
	cout << "\ngquiz.max_size() : " << gquiz.max_size();

	cout << "\ngquiz.at(2) : " << gquiz.at(2);
	cout << "\ngquiz.front() : " << gquiz.front();
	cout << "\ngquiz.back() : " << gquiz.back();

	cout << "\ngquiz.pop_front() : ";
	gquiz.pop_front();
	showdq(gquiz);

	cout << "\ngquiz.pop_back() : ";
	gquiz.pop_back();
	showdq(gquiz);

	return 0;
}
```