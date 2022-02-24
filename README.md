# best-practies-csharp

Bir liste içerisinde eleman olup olmadığını kontrol etmek için "Count > 0" kullanmak yerine Any methodunu tercih etmeliyiz.Bunun en büyük özelliklerinden biri Any Count methoduna göre daha performaslı çalışmaktadır.Ayrıyeten kelime anlamı olarak zaten Count methodu bir listenin eleman sayısını bulmak için kullanılırken Any methodu bir liste içerisinde anlamında kullanılır.

Unutmamak adına bir list null gelirse exception fırlatır ama boş gelirse exception fırlatmaz.İki değer farklı anlamlara gelmektedir.

```C#
var cities = Enumerable.Empty<string>();

if (cities.Count() > 0)
{

}

if (cities.Any())
{

}
```

IEnumerable tipli bir değişkene değer atarken doğru bir stilde atama yapılması gerekmektedir.

```C#
public class Person
{
    public IEnumerable<PhoneNumber> PhoneNumbersList { get; set; } = new List<PhoneNumber>();
    //instead
    public IEnumerable<PhoneNumber> PhoneNumbersEnumerable { get; set; } = Enumerable.Empty<PhoneNumber>();
    public string Name { get; set; }
    public string Surname { get; set; }
}
```
