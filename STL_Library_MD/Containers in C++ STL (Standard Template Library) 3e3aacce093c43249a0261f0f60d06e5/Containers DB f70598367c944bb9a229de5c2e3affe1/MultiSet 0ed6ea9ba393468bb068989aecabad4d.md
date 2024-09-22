# MultiSet

Multi set ile normal set arasında ki çok bir fark yoktur. Aralarında ki sadece işleyiş şekli farklı. Fonksiyon kullanımlarında bir kaç fonksiyon dışında normal setle aralarında çok bir fark bulunmamakta.

multiset kullanmak için yine <set> header file’ını kullanıyoruz.

Syntax:

> multiset<dataType> setName;
> 

Normal set unique key mantığında çalışırken mutli set’te unique mantığı bulunmamakta. 

örneğin normal bir set’e 1 2 3 1 4 5 elemanlarını eklerseniz, set içerisinde “1 2 3 4 5” elemanlarının olduğunu görürsünüz. unique özelliğinden kaynaklı. 

multi set’te ise bu durum bu şekilde değil. “1 2 3 1 4 5” elemanlarnı eklediğinizde multi set içerisinde “1 2 3 1 4 5” elemanlarını görürsünüz. Yukarıda da dediğim gibi multi set’te unique key özelliği bulunmuyor.

Fonksiyon kullanımları genellikle normla set ile aynı şekilde. (equeals_range ve pair gösterdim multi set üzerinde.)

```cpp
#include <iostream>
#include <iterator>
#include <set>
using namespace std;

int main()
{
	//Boş set define
	multiset<int, greater<int> > s1;
	//burada greater azalan sıraya göre demek
	// bu yüzden eklenen elemanlar büyükten küçüğe sıralanır.

	// Random bir şekilde değer ataması
	s1.insert(40);
	s1.insert(30);
	s1.insert(60);
	s1.insert(20);
	s1.insert(20);
	s1.insert(20);
	s1.insert(20);
	s1.insert(20);
	s1.insert(50);

	// Burada ki 50 ekleme işlemi yapılmıcak
	// Çünkü set'e bir değer bir kere eklenebilir.
	s1.insert(50);
	s1.insert(10);

	multiset<int>::iterator itr;
	for (itr = s1.begin(); itr != s1.end(); itr++) {
		cout << *itr << " ";
	}cout << endl;

	//pair<multiset<int>::iterator, multiset<int>::iterator> aralık =  s1.equal_range(20); // burada ki pair kullanımı çok uzun
	//c++'ın verdiği güzel bir özellik var.
	pair<decltype(itr) , decltype(itr)> aralık = s1.equal_range(20); // 20 değerinin set içerisinde hangi aralıklarda olduğunu gösteren bir iterator döndürücek.
	s1.erase(aralık.first, aralık.second);
	//aralıkların olduğu yeri iterator cinsinden bildiğimiz için direk aralığı silebiliyoruz.
	for (itr = s1.begin(); itr != s1.end(); itr++) {
		cout << *itr << " ";
	}cout << endl;
	//decltype burada bize tipi belirtir c++ özelliğidir.
	//burada daha önce tanımadığımız itr iteratorünü vererek
	//uzun bir satırdan kurtulmuş oluyoruz.
	return 0;
}
```