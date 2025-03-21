## Excel'e Veri Aktarma Yöntemi

Javascript kullanarak tabloları Excel dosyasına aktarmak oldukça basitleşmiştir. Bu yöntem sayesinde gereksiz kod kullanımını önleyebilir ve daha düzenli bir sayfa deneyimi sunabilirsiniz.

### Kullanım Adımları:

1. **Excel.js Dosyasının Dahil Edilmesi:**
   İlk olarak, projenize **excel.js** dosyasını dahil etmeniz gerekmektedir. Bunun için aşağıdaki `<script>` etiketi ile dosyayı projenize dahil edin:
   ```html
   <script src="js/excel.js"></script>

2. Excel Butonunun Oluşturulması: Excel dosyasına veri aktarmak için bir buton oluşturmalısınız. Butonun HTML kodu şu şekilde olabilir:
    ```html
    <button id="download" name="kulla">Excel Olarak İndir</button>

3. JavaScript Kodunun Eklenmesi: Projenizde excel.js dosyasını dahil ettikten sonra, aşağıdaki JavaScript kodunu sayfanın en altına yerleştirin. Bu kod, belirttiğiniz tabloyu Excel dosyasına aktarmak için kullanılır:

        document.getElementById('download').addEventListener('click', function () {
            var table = document.getElementById('myTable');
            var wb = XLSX.utils.table_to_book(table, {sheet: "Sheet1"});
            XLSX.writeFile(wb, 'tablo.xlsx');
        });

4. Tablonun Belirtilmesi: Excel'e aktarmak istediğiniz verilerin bulunduğu tabloyu, id özelliği ile belirtebilirsiniz. Örneğin, Excel'e aktarılacak tabloyu aşağıdaki şekilde belirtmişsiniz:
 
        <table border="1" style="margin-top:20px;" id="myTable">


 Not:
    Bu JavaScript kodu yalnızca görünür olan sayfadaki ilk tablonun verilerini alacaktır. Eğer sayfada çok fazla veri varsa ve farklı sayfalara geçiş yapmanız gerekiyorsa, yalnızca şu an görünen sayfa aktarılacaktır. Yani, yalnızca ekranın ilk bölümündeki veriler Excel'e aktarılacaktır.


