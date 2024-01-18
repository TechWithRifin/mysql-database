**MYSQL DATABASE**

--MASUK KE DALAM MYSQL CLIENT--

1. sebelum kita melakukan DDL (data definition language) ataupun DML (data manipulation language) didalam mysql, kita

--DATABASE--

1. database merupakan tempat untuk kita menyimpan tabel yang sudah kita buat di mysql
2. jika di umpamakan, tabel dimysql itu adalah sebuah file dan database di mysql itu adalah foldernya, dimana kita dapat menyimpan banyak table di dalam sebuah database (sebuah database dapat menampung berapapun tabel tanpa batasan).
3. biasanya 1 database untuk 1 jenis aplikasi, walaupun 1 aplikasi bisa menggunakan lebih dari 1 database, namun umumnya, 1 aplikasi akan menggunakan 1 database saja.
4. Note : sebelum membuat table di mysql, kita wajib untuk membuat databasenya terlebih dahulu

--MELIHAT LIST SEMUA DATABASE--

1. untuk melihat semua database yang ada didalam mysql, kita dapat menggunakan perintah : show databases;

--MEMBUAT DATABASE BARU--

1.untuk membuat database baru di dalam mysql, kita dapat menggunakan perintah : create database nama_database_yang_ingin_dibuat 2. misal : create database belajar_mysql (kita akan membuat database baru bernama belajar_mysql)

--MEMILIH DATABASE YANG INGIN DIGUNAKAN--

1. sebelum melakukan proses DDL ataupun DML, kita wajib untuk memilih database mana yang ingin digunakan untuk melakukan proses tersebut. Untuk memilih database yang ingin kita gunakan, kita dapat menggunakan perintah : use nama_database_yang_ingin_digunakan.
2. Misal : use belajar_mysql (kita akan melakukan proses DDL dan DML di dalam database belajar_mysql);

--MENGHAPUS DATABASE--

1. untuk menghapus database yang sudah dibuat, kita dapat menggukan perintah : drop database nama_database_yang_ingin_dihapus
2. misal : drop database belajar_mysql (database belajar_mysql akan dihapus)
3. perlu diigat : jika kita menghapus sebuah database, maka semua tabel beserta data yang ada didalam database tersebut juga akan ikut dihapus (alangkah baiknya kita melakukan backup tersebuh dahulu sebelum menghapus database (proses backup akan kita bahas di pembahasan selanjutnya)).

--TIPE DATA--

1. saat kita membuat tabel didalam sebuah database mysql, kita dapat menentukan tipe data dari setiap kolom yang akan kita buat didalam tabel tersebut.
2. terdapat banyak sekali tipe data yang tersedia didalam mysql, dari yang sederhana, sampai yang kompleks.
3. biasanya kita akan menggunakan tipe data sesuai dengan kebutuhan kolom yang kita buat. Misal nya kolom id tipe datanya adalah int lalu kolom nama tipe datanya adalah text dan lain sebagainya. Gampangnya kita menentukan tipe data sesuai data apa yang ingin kita masukkan ke dalam kolom tersebut. Misal jika kolom tersebut hanya akan berisi angka maka tipe data int adalah pilihan terbaik, walaupun tipe data text juga dapat menampung angka akan tetapi pilihan tersebut tidak direkomendasikan untuk kolom yang akan berisi angka saja.
4. perlu diingat, 1 kolom hanya dapat menggunakan 1 jenis tipe data saja. Misal jika kolom id memiliki tipe data int , maka kita hanya dapat mengisi kolom id tersebut dengan data bertipe angka saja (jika kolom id tersebut diisi dengan data selain angka, maka akan error).

--TIPE DATA NUMBER--

1. secara garis besar, tipe data number di dalam mysql terbagi menjadi 2 jenis yaitu :
2. tipe data integer yang berisi bilangan bulat
3. tipe data floating point yang berisi bilangan pecahan.

--TIPE DATA INTEGER--

1. tipe data integer juga terbagi menjadi beberapa jenis yaitu :
2. TINYINT = jika signed dapat berisi nilai antara -128 sampai 127 sedangkan jika unsigned dapat berisi antara 0 sampai 255
3. SMALLINT = jika signed dapat berisi nilai antara -32768 sampai 32767 sedangkan jika unsigned dapat berisi antara 0 sampai 65535
4. MEDIUMINT = jika signed dapat berisi nilai antara -8388608 sampai 8388607 sedangkan jika unsigned dapat berisi antara 0 sampai 16777215
5. INT = jika signed dapat berisi nilai antara -2147483648 sampai 2147483647 sedangkan jika unsigned dapat berisi antara 0 sampai 4294967295
6. BIGINT = jika signed dapat berisi nilai antara -9223372036854775808 sampai 9223372036854775807 sedangkan jika unsigned dapat berisi antara 0 sampai 18446744073709551615

--TIPE DATA FLOATING POINT--

1. tipe data floating point juga terbagi menjadi beberapa jenis yaitu :
2. FLOAT = jika signed dapat berisi nilai antara -3.402823466E+38 sampai -1.175494351E-38 sedangkan jika unsigned dapat berisi antara 1.175494351E-38 sampai 3.402823466E+38
3. DOUBLE = jika signed dapat berisi nilai antara -1.7976931348623157E+308 sampai -2.2250738585072014E-308 sedangkan jika unsigned dapat berisi antara 0 sampai 1.7976931348623157E+308

--TIPE DATA DECIMAL--

1. selain integer dan floating point, di mysql juga terdapat tipe data DECIMAL
2. tipe data ini merupakan tipe data number yang bersifat khusus dimana kita dapat menentukan jumlah procision dan scalenya.
3. format tipe data decimal adalah DECIMAL(jumlah_precision, jumlah_scale)
4. precision adalah jumlah angka maksimal sedangkan scale adalah jumlah angka dibelakang koma
5. misal DECIMAL(5,2) maka tipe data ini dapat berisi nilai antara -999,99 sampai 999,99
6. misal DECIMAL(5,0) maka tipe data ini dapat berisi nilai antara -99999 sampai 99999
7. misal DECIMAL(3,1) maka tipe data ini dapat berisi nilai antara -99,9 sampai 99,9
8. misal DECIMAL(3) maka tipe data ini dapat berisi nilai antara -999 sampai 999

--ATTRIBUTE NUMBER--

1. tipe data number juga memiliki beberapa atribute diantaranya adalah :
2. kita dapat menentukan jumlah angka maksimal dari suatu tipe data number menggunakan format type_data(jumlah_procision). Misalnya kita ingin membatasi jumlah angka dari suatu kolom dengan tipe data int berjumlah 5 angka saja, maka kita dapat melakukannya dengan format int(5). format tersebut akan menghasilkan kolom bertipe data int yang dapat diisi angka antara -99999 sampai 99999
3. kita juga dapat menambahkan atribut zerofill untuk mengganti ruang kosong pada suatu data bertipe data number. misalnya saat kita menambahkan zerofill pada kolom bertipe data int(3) lalu kita mengisi kolom tersebut dengan angka 5 maka hasilnya adalah angka 005.

--TIPE DATA STRING--

1. selain number, biasanya kita sering menyimpan data ke dalam tabel dengan bentuk kata atau kalimat (text).
2. tipe data jenis ini bisa di sebut tipe data string atau text
3. terdapat cukup banyak tipe data string di dalam mysql.

--TIPE DATA STRING CHAR DAN VARCHAR--

1. pertama tipe data string yang ada di mysql adalah tipe data char dan varchar
2. pada tipe data char dan varchar kita dapat menentukan jumlah karakter maksimal yang dapat ditampung suatu kolom menggunakan format CHAR(jumlah_maksimal_karakter) untuk tipe data char dan VARCHAR(jumlah_maksimal_karakter) untuk tipe data varchar
3. misal CHAR(10) atau VARCHAR(10) ini artinya kolom tersebut hanya dapat diisi data string dengan jumlah karakter maksimalnya adalah 10 karakter saja
4. untuk jumlah maksimum karakter dari tipe data CHAR dan VARCHAR sendiri jika tidak di atur jumlah maksimumnya adalah berjumlah 65535 karakter

--PERBEDAAN CHAR DAN VARCHAR--

1. walaupun tipe data char dan varchar terkesan sama, tetapi sebenarnya terdapat beberapa perbedaan jelas antara kedua tipe data ini yaitu :
2. jika kita memberi batasan jumlah maksimal karakter suatu kolom adalah 4 maka tipe data char akan selalu memasukkan 4 karakter ke dalam kolom tersebut meskipun kita hanya memasukkan 1 karakter ke kolom tersebut. Tipe data char akan mengisi ruang kosong yang tidak terisi dengan karakter spasi. misal kita membuat kolom nama dengan tipe data char(4) setelah itu kita memasukkan kata 'hi' kedalam kolom tersebut. Maka kolom tersebut akan terisi dengan kata 'hi '
3. sedangkan jika kita memberi batasan jumlah maksimal karakter suatu kolom adalah 4 maka tipe data varchar akan tetap memasukkan jumlah karakter yang sesuai dengan yang kita masukkan. misal kita membuat kolom nama dengan tipe data varchar(4) lalu kita memasukkan kata 'hi' ke dalam tersebut. maka kolom tersebut akan terisi dengan kata 'hi' juga.
4. perlu diingat kita akan mendapat error jika kita memasukkan data dengan jumlah karakter melebihi batas yang sudah ditentukan ke kolom char maupun varchar

--TIPE DATA TEXT--

1. selain CHAR dan VARCHAR, terdapat tipe data string lainnya yaitu tipe data TEXT
2. berbeda dengan CHAR dan VARCHAR yang bisa kita tentukan jumlah maksimum karakternya. kita tidak bisa menentukan jumlah maksimum karakter dari tipe data TEXT karena tipe data text sudah memiliki jumlah maksimum karakter tetap yang tidak bisa diubah.
3. terdapat 4 tipe data TEXT yaitu :
4. TINYTEXT dengan jumlah maksimum 255 karakter
5. TEXT dengan jumlah maksimum 65535 karakter
6. MEDIUMTEXT dengan jumlah maksimum 16777215 karakter
7. LONGTEXT dengan jumlah maksimum 4294967295 karakter

--TIPE DATA ENUM--

1. tipe data ENUM adalah tipe data string yang dapat kita tentukan pilihan data string yang boleh dimasukkan. jadi kita tidak dapat memasukkan sembarang string ke dalam tipe data enum ini.
2. misalnya kita membuat kolom dengan tipe data enum dengan format ENUM('pria','wanita') maka kolom tersebut hanya boleh diisi dengan data string pria atau wanita saja.
3. ENUM('tech','with','rifin') maka kolom ini hanya dapat diisi data string antara tech, with dan rifin saja

--TIPE DATA DATE DAN TIME--

1. selain tipe data number dan string, mysql juga mendukung tipe data datetime yang dapat kita gunakan untuk menyimpan data waktu atau tanggal
2. sebenarnya kita juga dapat menyimpan data tanggal dan waktu didalam kolom dengan tipe data string, namun itu tidak direkomendasikan karena akan menyulitkan kita ketika nanti butuh melakukan manipulasi waktu atau tanggal di mysql.

--JENIS-JENIS TIPE DATA DATE DAN TIME--

1. seperti tipe data number dan string, tipe data date dan time juga memiliki beberapa jenis diantaranya:
2. tipe data DATE yaitu tipe data yang hanya menyimpan data tahun, bulan, dan tanggal saja. format data dari tipe data DATE yaitu : YYYY-MM-DD. misalnya : 2023-01-22
3. tipe data DATETIME yaitu tipe data yang akan menyimpan data tahun, bulan, tanggal , jam , menit dan detik. format data dari tipe data DATETIME yaitu : YYYY-MM-DD HH:MM:SS. misalnya : 2023-01-22 06:30:50
4. tipe data TIMESTAMP yaitu tipe data yang sangat mirip dengan tipe data DATETIME. tipe data ini biasanya digunakan untuk kolom yang memiliki fungsi sebagai informasi tambahan misalnya : kolom created_at, last_updated_at dll
5. tipe data TIME yaitu tipe data yang akan menyimpan data jam, menit dan detik saja. format data dari tipe data TIME yaitu : HH:MM:SS. misalnya : 06:30:50
6. tipe data YEAR yaitu tipe data yang akan menyimpan data tahun saja. format data dari tipe data YEAR yaitu : YYYY. misalnya : 2023

--TIPE DATA BOOLEAN--

1. tipe data boolean merupakan tipe data kebenaran (bersifat pilihan), yang artinya datanya hanya ada dua jenis yaitu benar atau salah
2. benar direpresentasi dengan data TRUE sedangkan salah direpresentasikan dengan data FALSE.

--TIPE DATA LAINNYA--

1. sebenarnya masih banyak jenis tipe data lain yang didukung oleh mysql, namun itu bisa kita pelajari jika memang ada kebutuhan spesifik (tipe data-tipe data ini tidak sering digunakan)
2. seperti contohnya tipe data BLOB, SPATIAL (untuk geolocation), JSON, SET dan lain sebagainya
3. untuk lebih lengkapnya kita dapat membacanya di link : dev.mysql.com/doc/refman/8.0/en/data-types.html

--TABEL--

1. didalam mysql, data biasanya akan disimpan didalam tabel.
2. tipe tabel bisanya hanya menyimpan 1 jenis data. Misalnya ketika kita membuat aplikasi toko online, maka kita akan membuat tabel barang untuk menyimpan data-data barang, tabel pelanggan untuk menyimpan data-data pelanggan, tabel penjualan untuk menyimpan data-data penjualan dan lain lain
3. namun sebelum kita memasukkan data ke dalam sebuah tabel, kita wajib membuat tabelnya terlebih dahulu
4. Kita wajib menentukan kolom kolom beserta tipe data tiap kolom tersebut saat kita membuat sebuah tabel.
5. di mysql kita juga dapat mengubah struktur tabel yang sudah terlanjur dibuat. misalnya menambah kolom baru pada suatu tabel, mengubah kolom yang sudah ada di suatu tabel atau menghapus kolom pada suatu tabel.

--STORAGE ENGINES--

1. sebelum mulai membuat tabel, kita harus tahu dulu apa itu storage engines.
2. mysql memiliki berbagai cara untuk melakukan pengolahan data, hal ini disebut storage engines
3. sampai saat ini storage engines yang paling populer dan sering digunakan di mysql adalah InnoDB
4. jika kita ingin melihat semua storage engines yang ada di mysql, kita bisa menggunakan perintah : SHOW ENGINES;

--MELIHAT SEMUA TABEL--

1. untuk melihat list semua tabel yang ada di dalam sebuah database, kita dapat menggunakan perintah : SHOW TABLES;

--MEMBUAT TABEL BARU--

1. untuk membuat tabel baru di mysql, kita dapat menggunakan perintah : CREATE TABLE nama_tabel_yang_ingin_dibuat(nama_kolom1 tipe_data_kolom1, nama_kolom2 tipe_data_kolom2, dan seterusnya) ENGINE = nama_storage_engine_yang_ingin_digunakan;
2. misalnya : CREATE TABLE barang(id INT, nama VARCHAR(100), harga INT, jumlah INT) ENGINE = InnoDB;

--MELIHAT STRUKTUR TABEL--

1. untuk melihat struktur dari suatu tabel, kita dapat menggunakan perintah : DESCRIBE nama_tabel_yang_ingin_dilihat_strukturnya; atau DESC nama_tabel_yang_ingin_dilihat_strukturnya; . misal DESCRIBE barang atau DESC barang;
2. jika kita ingin melihat sintax sql pembuatan suatu tabel, kita dapat menggunakan perintah SHOW CREATE TABLE nama_tabel_yang_ingin_dilihat_sintax_sqlnya; . misal : SHOW CREATE TABLE barang; maka akan tampil sintax sql dari pembuatan tabel barang. Sederhananya nanti akan tampil perintah sql membuat tabel barang

--MENGUBAH STRUKTUR TABEL--

1. jika kita ingin merubah struktur dari suatu tabel yang sudah terlanjut dibuat (misalnya kita ingin menambah kolom baru, menghapus suatu kolom atau mengganti tipe data dari suatu kolom). kita dapat menggunakan perintah :
   ALTER TABLE nama_tabel_yang_ingin_diubah_strukturnya
   ADD COLUMN nama_kolom_baru tipe_data_dari_kolom_tersebut, <- untuk menambah kolom baru ke dalam tabel
   DROP COLUMN nama_kolom_yang_ingin_dihapus, <- menghapus suatu kolom dari tabel
   RENAME COLUMN nama_kolom_yang_ingin_diubah_namanya TO nama_baru_dari_kolom_tersebut, <- merubah nama dari suatu kolom
   MODIFY nama_kolom_yang_ingin_dipindah_posisinya tipe_data_dari_kolom_tersebut AFTER nama_kolom_sebelum_posisi_baru, <- merubah posisi suatu kolom di dalam tabel
   MODIFY nama_kolom_yang_ingin_dipindah_posisinya tipe_data_dari_kolom_tersebut FIRST, <- merubah posisi kolom ke posisi pertama di dalam tabel
   MODIFY nama_kolom_yang_ingin_diubah_tipe_datanya tipe_data_baru_dari_kolom_tersebut; <- merubah tipe data dari suatu kolom di dalam tabel
2. misalnya : ALTER TABLE barang ADD COLUMN deskripsi TEXT, DROP COLUMN nama, RENAME COLUMN jumlah TO total, MODIFY deskripsi TEXT AFTER id, MODIFY harga INT FIRST, MODIFY deskripsi VARCHAR(200);

--NULL VALUE PADA SUATU KOLOM--

1. null adalah nilai ketika kita tidak mengisi data apapun ke dalam suatu kolom pada sebuah tabel.
2. secara default, saat kita membuat suatu kolom pada suatu tabel, kolom tersebut dapat berisi nilai NULL (kolom tersebut boleh tidak diisi), jika kita tidak ingin menerima nilai NULL (membuat kolom tersebut harus diisi), maka kita dapat menambahkan perintah NOT NULL ketika pembuatan kolom di dalam tabel.
3. format penambahan NOT NULL saat membuat tabel baru : CREATE TABLE nama_tabel_baru (nama_kolom1 tipe_data_kolom1 NOT NULL, nama_kolom2 tipe_data_kolom2 NOT NULL, dan seterusnya) ENGINE = InnoDB;
4. jika kita ingin menambahkan perintah NOT NULL ke dalam kolom pada tabel yang sudah terlanjur dibuat, kita dapat menggunakan perintah : ALTER TABLE nama_tabel_yang_ingin_diubah_strukturnya MODIFY nama_kolom tipe_data_kolom NOT NULL;

--DEFAULT VALUE PADA SUATU KOLOM--

1. saat kita menyimpan data ke dalam sebuah tabel, lalu kita hanya mengisi beberapa kolom saja (tidak mengisi semua kolom), kolom yang tidak diisi, maka secara default akan bernilai NULL (ini hanya berlaku pada kolom2 yang tidak di set NOT NULL)
2. jika kita ingin mengubah default value pada suatu kolom, kita dapat menambahkan perintah DEFAULT nilai_default_yang_diinginkan ketika pembuatan kolom didalam suatu tabel
3. format penambahan default value saat membuat tabel baru : CREATE TABLE nama_tabel_baru (nama_kolom1 tipe_data_kolom1 DEFAULT nilai_default_yang_diinginkan, nama_kolom2 tipe_data_kolom2 DEFAULT nilai_default_yang_diinginkan, dan seterusnya) ENGINE = InnoDB;
4. jika kita ingin menambahkan default value ke dalam kolom pada tabel yang sudah terlanjur dibuat, kita dapat menggunakan perintah : ALTER TABLE nama_tabel_yang_ingin_diubah_strukturnya MODIFY nama_kolom tipe_data_kolom DEFAULT nilai_default_yang_diinginkan;
5. klusus untuk tipe data DATETIME atau TIMESTAMP, jika kita ingin menggunakan default value dari nilai waktu saat ini, kita dapat menggunakan kata kunci CURRENT_TIMESTAMP misal : ALTER TABLE nama_tabel_yang_ingin_diubah_strukturnya MODIFY nama_kolom tipe_data_kolom DEFAULT CURRENT_TIMESTAMP;

--MENGHAPUS SEMUA DATA DIDALAM TABEL--

1. untuk menghapus seluruh data yang ada di dalam suatu tabel, kita dapat menggunakan perintah : TRUNCATE nama_tabel_yang_ingin_dihapus_datanya; . Misalnya TRUNCATE barang; . maka seluruh data didalam tabel barang akan terhapus
2. cara kerja dari truncate ini adalah menghapus tabel lalu secara otomatis membuat tabelnya kembali (cara kerjanya mirip seperti melakukan reset data pada suatu tabel)

--MENGHAPUS TABEL--

1. jika kita ingin menghapus suatu tabel yang ada di dalam sebuah database, kita dapat menggunakan perintah : DROP TABLE nama_tabel_yang_ingin_dihapus;. misalnya : DROP TABLE barang;. maka tabel barang akan terhapus dari database.

--MEMASUKKAN DATA KEDALAM TABEL--

1. saat kita ingin memasukkan ke dalam tabel, pada saat melakukan proses insert data, kita tidak wajib untuk mengisi semua kolom yang ada di dalam suatu tabel, kita bisa mengisi data di kolom2 yang kita inginkan saja dengan cara menyebutkan nama2 kolom yang ingin kita isi. dengan ini, maka kolom2 yang tidak disebutkan akan diisi dengan nilai null atau default value dari kolom tersebut yang sudah kita sebutkan pada saat membuat tabel. Sederhananya jika suatu tabel memiliki 8 kolom dan kita hanya mengisi 5 kolom saja maka 3 kolom sisanya akan diisi dengan nilai NULL atau default value nya
2. untuk memasukkan data ke dalam suatu tabel, kita dapat menggunakan perintah sql yang bernama INSERT

--INSERT DATA--

1. untuk memasukkan data ke dalam tabel, kita dapat menggunakan perintah : INSERT INTO nama_tabel_yang_ingin_diisi_datanya(nama_kolom1, nama_kolom2, nama_kolom3, dan_seterusnya) VALUES(nilai_kolom1, nilai_kolom2, nilai_kolom3, dan_seterusnya);

--INSERT BANYAK DATA SEKALIGUS--

1. untuk memasukkan banyak data sekaligus ke dalam tabel, kita dapat menggunakan perintah : INSERT INTO nama_tabel_yang_ingin_diisi_datanya(nama_kolom1, nama_kolom2, nama_kolom3, dan_seterusnya) VALUES(nilai_ke1_dari_kolom1, nilai_ke1_dari_kolom2, nilai_ke1_dari_kolom3, dan_seterusnya),(nilai_ke2_dari_kolom1, nilai_ke2_dari_kolom2, nilai_ke2_dari_kolom3, dan_seterusnya), (nilai_ke3_dari_kolom1, nilai_ke3_dari_kolom2, nilai_ke3_dari_kolom3, dan_seterusnya), dan seterusnya;

--MENGAMBIL DATA--

1. untuk mengambil data di tabel, kita dapat menggunakan perintah sql SELECT
2. perintah select bisa kita gunakan untuk mengambil seluruh data pada semua kolom yang ada di dalam tabel, atau kita juga dapat mengambil data yang ada di beberapa kolom saja di dalam tabel. Misal suatu tabel memiliki 8 kolom dan kita hanya ingin mengambil data yang ada di 5 kolom saja itu bisa dilakukan menggunakan perintah select
3. jika kita ingin mengambil data di semua kolom yang ada di sebuah tabel, kita dapat menggunakan karakter \* (bintang)
4. sedangkan jika kita hanya ingin mengambil data di beberapa kolom saja, kita bisa menyebutkan nama-nama kolom yang ingin kita ambil datanya.

--SELECT DATA--

1. kita dapat mengambil data yang ada di semua kolom di suatu tabel menggunakan perintah : SELECT _ FROM nama_tabel_yang_ingin_diambil datanya; misal : SELECT _ FROM products;
2. kita dapat mengambil data yang ada di beberapa kolom saja di suatu tabel menggunakan perintah : SELECT nama_kolom1, nama_kolom2, nama_kolom3, dan_seterusnya FROM nama_tabel_yang_ingin_diambil; misalnya : SELECT id,name,price,quantity FROM products;

--PRIMARY KEY--

1. saat kita membuat tabel, idealnya setiap tabel yang kita buat harus memiliki sebuah primary key
2. primary key ialah sebuah kolom yang kita tunjuk sebagai id (identitas) dari suatu tabel
3. primary key juga dapat diartikan sebagai identitas untuk tiap baris data yang ada di dalam suatu tabel
4. primary key harus bersifat unik, jadi tidak boleh ada data dengan primary key yang sama
5. misal kita menunjuk kolom kode sebagai primary key, maka data-data yang ada di kolom kode tidak boleh ada yang sama.

--PRIMARY KEY DI BANYAK KOLOM--

1. sebenarnya kita bisa membuat primary key dengan kombinasi beberapa kolom (menunjuk lebih dari 1 kolom sebagai primary key)
2. namun sangat disarankan untuk tetap membuat primary key hanya di 1 kolom saja pada suatu tabel
3. kecuali ada kasus khusus dimana kita wajib membuat lebih dari 1 primary key di sebuah tabel seperti kasus membuat tabel yang berelasi many to many.

--MENAMBAHKAN PRIMARY KEY--

1. jika kita ingin menambahkan primary key pada saat kita membuat tabel baru, kita dapat menggunakan perintah : CREATE TABLE nama_tabel_baru(nama_kolom1 tipe_data_kolom1,nama_kolom2 tipe_data_kolom2, PRIMARY KEY (nama_kolom_yang_ingin_dijadikan_primary_key)) ENGINE = InnoDB; misalnya : CREATE TABLE product (id INT, name VARCHAR(100), PRIMARY KEY (id)) ENGINE = InnoDB;
2. sedangkan jika kita ingin menambahkan primary key pada tabel yang sudah terlanjur dibuat, kita dapat menggunakan perintah : ALTER TABLE nama_tabel_yang_ingin_ditambahkan_primary_key ADD PRIMARY KEY (nama_kolom_yang_ingin_dijadikan_primary_key); misalnya ALTER TABLE products ADD PRIMARY KEY(id)

--MEMFILTER DATA MENGGUNAKAN WHERE--

1. saat kita ingin mengambil data menggunakan perintah sql select, kadang kita ingin melakukan fiterisasi data apa saja yang ingin kita ambil.
2. misal kita hanya ingin mengambil data barang yang harganya 1 juta saja atau kita hanya ingin mengambil data barang yang quantitynya 0 saja
3. hal ini dapat dilakukan menggunakan WHERE clause setelah perintah SELECT.
4. format penulisah where clause pada perintah select adalah sebagai berikut : SELECT nama_kolom1, nama_kolom2, dan_seterusnya FROM nama_tabel_yang_ingin_diambil_datanya WHERE filternya;
5. misalnya : SELECT id, name, price, quantity FROM products WHERE quantity = 0; . Perintah ini hanya akan mengambil data-data dari tabel products yang memiliki nilai quantity 0 saja;

--UPDATE DATA--

1. untuk mengubah data yang ada di dalam tabel, kita bisa menggunakan perintah sql UPDATE.
2. saat menggunakan perintah sql UPDATE, kita harus memberi tahu mysql, data mana yang ingin kita update. kita dapat menggunakan WHERE clause untuk memberi tahu mysql data mana yang akan kita update.
3. kita juga dapat menentukan kolom mana saja yang ingin di update. misal didalam sebuah tabel terdapat 8 kolom dan kita hanya ingin mengupdate 5 kolom saja itu bisa.
4. format perintah untuk update data adalah sebagai berikut : UPDATE nama_tabel_yang_ingin_diupdate_datanya SET nama_kolom1 = nilai_baru_untuk_kolom1, nama_kolom2 = nilai_baru_untuk_kolom2, dan_seterusnya WHERE filternya;
5. misalnya : UPDATE products SET price = 30000 WHERE id = 'P0004'; maka nilai dari kolom price pada tabel product yang memiliki id P0004 akan di ganti dengan nilai 30000
6. kita juga dapat menambahkan perhitungan matematika sederhana saat melakukan proses update data. Misalnya : UPDATE products SET price = price + 5000 WHERE id = 'P0001'; maka nilai dari kolom price pada tabel product yang memiliki id P0001 akan di tambah dengan nilai 5000. jadi jika kolom price tersebut sebelumnya bernilai 15000 maka sekarang nilainya akan menjadi 20000

--DELETE DATA--

1. setelah kita tahu bagaimana cara menambah data ke dalam tabel, mengubah dan mengambil data yang ada didalam tabel, maka yang perlu kita ketahui selanjutnya adalah cara menghapus data yang ada didalam tabel
2. untuk menghapus data di dalam tabel, kita dapat menggunakan perintah SQL yaitu DELETE
3. sama seperti perintah UPDATE, saat kita ingin menghapus data menggunakan perintah DELETE, maka kita harus memberi tahu mysql data mana yang ingin dihapus. Untuk memberi tahu mysql data mana yang ingin di hapus, kita dapat menggunakan where clause pada perintah DELETE
4. kita harus hati-hati agar tidak salah saat menggunakan where clause pada perintah DELETE, karena jika salah, bisa-bisa kita akan menghapus data yang tidak ingin kita hapus.
5. format perintah untuk menghapus data adalah sebagai berikut: DELETE FROM nama_tabel_yang_ingin_dihapus_datanya WHERE filternya
6. misalnya : DELETE FROM products WHERE id = 'P0009'; maka data pada tabel products yang memiliki id P0009 akan dihapus.

--ALIAS--

1. MySQL memiliki fitur yang bernama alias. Fitur ini berfungsi untuk memberi nama lain pada kolom yang ada di dalam suatu tabel atau untuk memberi nama lain pada tabel yang ada didalam suatu database.
2. Alias berguna ketika kita ingin mengubah nama kolom atau nama tabel saat kita melakukan perintah select
3. Mungkin alias ini terdengar kurang ada gunanya, tapi nanti ketika kita ingin melakukan JOIN, disitulah fitur alias ini akan sangat mempermudah kita.
4. note : alias ini hanya akan merubah nama kolom dari hasil quary saat itu saja. jadi nama kolom yang ada di dalam tabel pada database akan tetap sama seperti sebelumnya.

--ALIAS UNTUK KOLOM--

1. format penulisan alias untuk kolom ada sebagai berikut : SELECT nama_kolom1 as 'nama_lain_untuk_kolom1', nama_kolom2 as 'nama_lain_untuk_kolom2', danseterusnya FROM nama_tabel;
2. misalnya : SELECT id as 'Kode', name as 'Nama', category as 'Kategori', price as 'Harga', quantity as 'Stock' FROM products;
3. note : kita diperbolehkan untuk memberi alias hanya untuk beberapa kolom saja didalam sebuah tabel. Misal : didalam sebuah tabel terdapat 10 kolom maka kita diperbolehkan hanya memberi alias pada 6 kolom saja jadi 4 kolom sisanya akan dinamai dengan nama kolom sebenarnya

--ALIAS UNTUK TABEL--

1. format penulisan alias untuk tabel adalah sebagai berikut : SELECT nama_alias_tabel.nama_kolom1, nama_alias_tabel.nama_kolom2, nama_alias_tabel.nama_kolom3 danseterusnya FROM nama_tabel AS nama_alias_tabel
2. misalnya : SELECT p.id, p.name, p.category, p.price, p.quantity FROM products AS p;

--WHERE OPERATOR--

1. pada pembahasan where clause sebelumnya, sebenarnya kita sudah menggunakan salah satu operator where yaitu "=" (sama dengan)
2. sebenarnya terdapat banyak operator yang dapat kita gunakan ketika menggunakan where clause. Operator tersebut diantaranya adalah :
3. operator perbandingan, operator AND dan OR, operator prioritas menggunakan kurung, operator LIKE, operator NULL, operator BETWEEN, operator IN

--OPERATOR PERBANDINGAN--

1. operator ini perfungsi untuk membandingkan nilai dari suatu kolom didalam sebuah tabel dengan nilai yang sudah kita tentukan. Berikut adalah beberapa operator perbandingan yang dapat kita gunakan :
2. operator '=' (sama dengan) artinya hanya data yang nilai kolomnya sama dengan nilai yang sudah kita tentukan saja yang akan diambil. Misalnya : SELECT \* FROM products WHERE category = 'makanan'; perintah ini hanya akan mengambil data-data dengan nilai category makanan saja (data-data yang memiliki nilai category selain makanan misalnya munuman, buah-buahan dan lain lain tidak akan ikut diambil).
3. operator '!=' (tidak sama dengan) artinya hanya data yang nilai kolomnya tidak sama dengan nilai yang sudah kita tentukan saja yang akan diambil. Misalnya : SELECT \* FROM products WHERE category != 'makanan'; perintah ini hanya akan mengambil data-data dengan nilai kategori selain makanan saja (akan mengambil data-data dengan kategori minuman, buah dan lain sebagainya asalkan categorynya tidak bernilai makanan akan diambil).
4. operator '<' (kurang dari) artinya hanya data yang nilai kolomnya kurang dari nilai yang sudah kita tentukan saja yang akan di ambil (ini cocok digunakan pada kolom yang memiliki tipe data number). Misalnya : SELECT \* FROM products WHERE price < 15000; perintah ini hanya akan mengambil data-data dengan nilai price kurang dari 15000 saja (jadi data-data yang nilai pricenya 15000 ke atas tidak akan diambil).
5. operator '<=' (kurang dari sama dengan) artinya hanya data yang nilai kolomnya kurang dari atau sama dengan nilai yang sudah kita tentukan saja yang akan di ambil (ini cocok digunakan pada kolom yang memiliki tipe data number). Misalnya : SELECT \* FROM products WHERE price <= 15000; perintah ini hanya akan mengambil data-data dengan nilai price kurang dari atau sama dengan 15000 saja (jadi data-data yang nilai pricenya diatas 15000 tidak akan diambil).
6. operator '>' (lebih dari) artinya hanya data yang nilai kolomnya lebih dari nilai yang sudah kita tentukan saja yang akan di ambil (ini cocok digunakan pada kolom yang memiliki tipe data number). Misalnya : SELECT \* FROM products WHERE price > 15000; perintah ini hanya akan mengambil data-data dengan nilai price lebih dari 15000 saja (jadi data-data yang nilai pricenya 15000 kebawah tidak akan diambil).
7. operator '>=' (lebih dari sama dengan) artinya hanya data yang nilai kolomnya lebih dari atau sama dengan nilai yang sudah kita tentukan saja yang akan di ambil (ini cocok digunakan pada kolom yang memiliki tipe data number). Misalnya : SELECT \* FROM products WHERE price >= 15000; perintah ini hanya akan mengambil data-data dengan nilai price lebih dari atau sama dengan 15000 saja (jadi data-data yang nilai pricenya dibawah 15000 tidak akan diambil)

--OPERATOR AND DAN OR--

1. kadang kita ingin mencari atau memfilter data dengan lebih dari 1 kondisi (gabungan beberapa kondisi), untuk melakukan hal ini kita dapat menggunakan operator AND dan OR
2. operator AND dan OR digunakan sebagai penggabung beberapa operator
3. operator AND bernilai benar jika seluruh kindisi bernilai benar
4. dan operator OR bernilai benar jika salah satu kondisi bernilai benar
5. format penulisan operator AND adalah sebagai berikut : SELECT \* FROM nama_tabel WHERE kondisi1 AND kondisi2; Misalnya : SELECT \* FROM products WHERE price > 15000 AND quantity < 50; perintah ini hanya akan mengambil data-data yang nilai price nya lebih dari 15000 dan nilai quantitynya kurang dari 50 saja. (jika nilai pricenya tidak sesuai dan nilai quantitynya sesuai maka data tersebut tidak diambil begitu juga sebaliknya)
6. format penulisan operator OR adalah sebagai berikut : SELECT \* FROM nama_tabel kondisi1 OR kondisi2; misalnya : SELECT \* FROM products WHERE price > 15000 OR quantity < 50; perintah ini hanya akan mengambil data-data yang nilai pricenya lebih dari 15000 atau nilai quantitynya kurang dari 50 saja. (jika pricenya tidak sesuai dan quantitynya sesuai maka data tersebut akan ikut diambil begitu juga sebaliknya)
7. perlu diingat jika didalam perintah terdapat operator or dan and, dimanapun posisi and berada maka operator and akan di eksekusi terlebih dahulu setelah itu operator or akan di eksekusi. (jika kita ingin mengeksekusi operator or terlebih dahulu maka kita wajib menambahkan operator prioritas menggunakan tanda kurung ())

--OPERATOR PRIORITAS DENGAN TANDA KURUNG ()--

1. saat kita mencari data dengan lebih dari 1 kondisi, kita dapat menentukan prioritas kondisi mana yang ingin didahulukan menggunakan tanda kurung ()
2. misalnya : SELECT \* FROM products WHERE price > 100000 AND (category = 'Makanan' OR quantity > 500); perintah ini akan menjalankan kondisi 2 (category) dan 3 (quantity) terlebih dahulu kemudian baru menjalankan kondisi 1 (price)

--OPERATOR LIKE--

1. operator LIKE merupakan operator yang dapat digunakan untuk mencari sebagian data saja di dalam suatu string
2. operator ini sangat cocok digunakan ketika kita hanya ingin mencari sebagian kata saja di dalam suatu string. Misalnya : kita ingin mencari kata 'ayam' di dalam string 'mie ayam original' itu bisa dilakukan menggunakan operator LIKE ini.
3. namun perlu diingat, operator like ini sangat lambat karena dia akan melakukan scanning setiap kata dari data pertama sampai data terakhir. Maka dari itu kita tidak disarankan menggunakan operator ini jika data didalam tabel sudah terlalu besar (datanya 1 juta keatas).
4. operator LIKE ini tidak case sensitive. Jadi baik besar ataupun kecil huruf yang kita gunakan itu tidak akan berpengaruh. Misal : kita menggunakan kata 'ayam' pada operator LIKE dan didalam tabel terdapat string 'Mie Ayam Original' maka data tersebut akan ikut diambil

--FORMAT PENULISAN OPERATOR LIKE--

1. SELECT \* FROM nama_tabel WHERE nama_kolom LIKE 'katayangdicari%'; perintah ini akan mencari data didalam nama_kolom yang awalan kalimatnya mengandung kata yang dicari. misal : SELECT \* FROM products WHERE name LIKE 'mi%'; perintah ini akan mencari data didalam kolom name yang mengandung awalan dari kalimatnya adalah 'mi' contohnya 'mie ayam original' (didalam kalimat tersebut awalan katanya adalah mie. Dan kata mie mengandung awalan 'mi').
2. SELECT \* FROM nama_tabel WHERE nama_kolom LIKE '%katayangdicari'; perintah ini akan mencari data didalam nama_kolom yang akhiran kalimatnya mengandung kata yang dicari. Misal : SELECT \* FROM products WHERE name LIKE '%al'; perintah ini akan mencari data didalam kolom name yang mengandung akhiran dari kalimatnya adalah 'al' contohnya 'mie ayam original' (didalam kalimat tersebut akhiran katanya adalah original. Dan kata original mengandung akhiran 'al')
3. SELECT \* FROM nama_tabel WHERE nama_kolom LIKE '%katayangdicari%'; perintah ini akan mencari data didalam nama_kolom yang mengandung kata yang dicari tidak peduli dimanapun tempatnya (bisa diawal, ditengah, maupun diakhir kalimat).misal : SELECT \* FROM products WHERE name LIKE '%ayam%'; perintah ini akan mencari data didalam kolom name yang mengandung kata 'ayam' contohnya 'mie ayam original' (didalam kalimat tersebut ditengahnya ada kata 'ayam' nya)
4. SELECT \* FROM nama_tabel WHERE nama_kolom NOT LIKE '%katayangdicari%'; perintah ini akan mencari data didalam nama_kolom yang tidak mengandung kata yang dicari tidak peduli dimanapun tempatnya (bisa diawal, ditengah, maupun di akhir kalimat). Misal : SELECT \* FROM products WHERE name NOT LIKE '%ayam%'; perintah ini akan mencari data didalam kolom name yang tidak mengandung kata 'ayam' contohnya 'mie bakso ceker' (didalam kalimat tersebut tidak mengandung kata 'ayam' sama sekali baik diawal ditengah maupun di akhir kalimatnya)

--OPERATOR NULL--

1. untuk mencari data yang bernilai null, kita tidak bisa menggunakan operator perbandingan = NULL
2. karena untuk mencari data yang bernilai null, terdapat operator khusus yaitu IS NULL dan IS NOT NULL
3. operator IS NULL berfungsi untuk mencari data yang bernilai null
4. operator IS NOT NULL berfungsi untuk mencari data yang tidak bernilai null
5. format penulisan operator is null adalah SELECT \* FROM nama_tabel WHERE nama_kolom IS NULL; misal : SELECT \* FROM products WHERE description IS NULL; perintah ini hanya akan mengambil data yang descriptionnya bernilai null saja
6. format penulisan operator is not null adalah SELECT \* FROM nama_tabel WHERE nama_kolom IS NOT NULL; misal : SELECT \* FROM products WHERE description IS NOT NULL; perintah ini hanya akan mengambil data yang descriptionnya tidak bernilai null saja

--OPERATOR BETWEEN--

1. kadang ada kasus dimana kita ingin mencari data di sebuah kolom yang kurang dari sama dengan dan lebih dari sama dengan secara bersamaan.
2. misalnya kita ingin mencari products yang harganya antara 10000 sampai 20000
3. untuk menyelesaikan kasus seperti diatas, kita biasanya akan menggunakan kondisi sebagai berikut : WHERE price >= 10000 AND price <= 20000
4. namun cara diatas terkesan ribet dan panjang
5. untungnya di mysql terdapat operator between yang dapat menyelesaikan kasus seperti diatas dengan lebih sederhana
6. format penulisan operator between adalah sebagai berikut : SELECT \* FROM nama_tabel WHERE nama_kolom BETWEEN nilai_batas_bawah AND nilai_batas_atas; Misalnya : SELECT \* FROM products WHERE price BETWEEN 10000 AND 20000; perintah ini hanya akan mengambil data yang harganya antara 10000 sampai 20000 saja
7. untuk mencari data yang nilainya tidak diantara nilai yang kita tentukan, kita dapat menggunakan operator not between
8. format penulisan operator not between adalah sebagai berikut : SELECT _ FROM nama_tabel WHERE nama_kolom NOT BETWEEN nilai_batas_bawah AND nilai_batas_atas; misalnya : SELECT _ FROM products WHERE price NOT BETWEEN 10000 AND 20000; perintah ini hanya akan menampilkan data-data yang nilai harganya tidak diantara 10000 sampai 20000

--OPERATOR IN--

1. kadang ada kasus dimana kita ingin melakukan pencarian di sebuah kolom menggunakan beberapa nilai secara bersamaan
2. misalnya kita ingin mencari data didalam tabel product dengan category makanan atau minuman.
3. untuk menyelesaikan kasus seperti diatas kita biasanya menggunakan kondisi sebagai berikut : WHERE category = 'Makanan' OR category = 'Minuman'
4. namun cara diatas terkesan ribet dan panjang (bikin capek)
5. untungnya di mysql terdapat operator IN yang dapat menyelesaikan kasus seperti diatas dengan lebih sederhana
6. format penulisan operator IN adalah sebagai berikut : SELECT \* FROM nama_tabel WHERE nama_kolom IN ('nilai1','nilai2','nilai3','danseterusnya');
7. misalnya : SELECT \* FROM products WHERE category IN ('Makanan','Minuman'); perintah ini hanya akan mengambil data-data product dengan kategori makanan dan minuman saja
8. untuk mencari data-data yang bukan dari nilai-nilai yang kita sebutkan di operator IN kita dapat menggunakan operator NOT IN.
9. format penulisan operator NOT IN adalah sebagai berikut : SELECT \* FROM nama_tabel WHERE nama_kolom NOT IN ('nilai1','nilai2','nilai3','danseterusnya');
10. misalnya : SELECT \* FROM products WHERE category NOT IN ('Makanan','Minuman'); perintah ini hanya akan mengambil data-data product yang berkategori selain manakan dan minuman saja

--ORDER BY CLAUSE--

1. jika kita ingin mengurutkan data yang kita ambil menggunakan perintah select, kita dapat menambahkan ORDER BY cluse
2. ORDER BY clause biasanya digunakan untuk mengurutkan data berdasarkan kolom yang dipilih. Terdapat 2 jenis metode pengurutan data yang dapat digunakan yaitu ASC (diurutkan dari kecil ke besar) dan DESC (diurutkan dari besar ke kecil)
3. format penulisan ORDER BY clause adalah sebagai berikut : SELECT \* FROM nama_tabel ORDER BY nama_kolom jenis_pengurutan;
4. misalnya : SELECT \* FROM products ORDER BY name ASC; perintah ini akan mengurutkan data-data products yang kita ambil berdasarkan kolom name dengan jenis pengurutan ASC atau dari kecil ke besar (dari a ke z)
5. kita juga dapat melakukan ORDER BY clause menggunakan banyak kolom.
6. format penulisan ORDER BY clause menggunakan banyak kolom adalah sebagai berikut : SELECT \* FROM nama_tabel ORDER BY nama_kolom1 jenis_pengurutan, nama_kolom2 jenis_pengurutan, danseterusnya;
7. misalnya : SELECT \* FROM products ORDER BY category ASC, price DESC; perintah ini akan mengurutkan data-data products yang akan kita ambil berdasarkan kolom category dengan jenis pengurutan ASC terlebih dahulu kemudian mengurutkan data-data product berdasarkan kolom price dengan jenis pengurutan DESC

--LIMIT CLAUSE--

1. Kadang kita ingin membatasi jumlah data yang ingin kita ambil menggunakan perintah select.
2. Kita dapat membatasi jumlah data yang ingin diambil dalam SQL SELECT menggunakan LIMIT clause
3. format penulisan LIMIT clause adalah sebagai berikut : SELECT \* FROM nama_tabel LIMIT jumlahdatayangingindiambil;
4. misalnya : SELECT \* FROM products LIMIT 5; perintah ini hanya akan mengambil data products sebanyak 5 data saja. Jadi jika datanya ada 10 maka data yang akan diambil adalah data ke 1 sampai data ke 5 saja.
5. selain membatasi jumlah data yang ingin diambil, kita juga dapat melompati (meng-skip) sejumlah data yang tidak ingin diambil.
6. format penulisannya adalah sebagai berikut : SELECT \* FROM nama_tabel LIMIT jumlahdatayangingindilompati , jumlahdatayangingindiambil;
7. misal : SELECT \* FROM products LIMIT 5,5; perintah ini akan melompati 5 data product kemudian mengambil 5 data product yang ada didalam tabel product. Jadi jika didalam tabel product terdapat 15 data, maka data yang akan diambil adalah data ke 6 sampai data ke 10 saja.

--SELECT DISTINCT--

1. saat kita melakukan query select, kadang kita akan mendapatkan data-data yang bernilai sama (data duplikat).
2. misalnya : kita ingin mengambil semua data dari kolom category yang ada di dalam tabel products menggunakan query select, maka secara otomatis hasil yang akan kita dapat adalah banyak data kategori yang duplikat. Karena didalam tabel product, terdapat beberapa product dengan kategori yang sama.
3. jika kita ingin menghilangkan data-data duplikat tersebut dan hanya mengambil 1 data untuk tiap data yang bernilai sama (duplikat) didalam tabel product. kita dapat menggunakan query SELECT dengan tambahan DISTINCT sebelum nama kolom.
4. format penulisannya adalah sebagai berikut : SELECT DISTINCT nama_kolom1, nama_kolom2, danseterusnya FROM nama_tabel;
5. misalnya : SELECT DISTINCT category FROM products; perintah ini akan mengambil data category didalam tabel products yang awalnya minuman,minuman,makanan,makanan menjadi minuman,makanan.
6. perlu diingat jika kita melakukan query select distinct di beberapa kolom pada suatu tabel, maka data dikatakan duplikat jika data disemua kolom yang disebutkan memiliki nilai yang sama. Misalnya pada data ke 1 kolom 1 bernilai a dan kolom 2 bernilai b kemudian pada data ke 2 kolom 1 bernilai a dan kolom 2 bernilai b maka data tersebut di hitung sama (duplikat).
7. jika data di salah satu kolom memiliki nilai berbeda maka data tidak dihitung sama (tidak duplikat). Misalnya pada data ke 1 kolom 1 bernilai a dan kolom 2 bernilai b kemudian pada data ke 2 kolom 1 bernilai a dan kolom 2 bernilai c maka data tersebut di hitung tidak sama (tidak duplikat).

--NUMERIC FUNCTION--

1. Mysql memiliki banyak sekali fitur untuk memanipulasi data angka
2. hal ini akan memudahkan kita untuk memanipulasi data-data angka didalam suatu tabel.
3. secara garis besar, fitur ini dapat dibagi menjadi 2 yaitu operator arithmetic dan mathematical function

--OPERATOR ARITHMETIC--

1. terdapat beberapa arithmetic operator dimysql diantaranya adalah sebagai berikut :
2. % atau MOD ini berfungsi untuk mencari modulo atau hasil sisa bagi
3. - (bintang) ini berfungsi untuk melakukan perkalian
4. - (tambah) ini berfungsi untuk melakukan penambahan
5. - (kurang) ini berfungsi untuk melakukan pengurangan
6. / (bagi) ini berfungsi untuk melakukan pembagian (hasil yang dikeluarkan akan berbentuk floating point atau pecahan) misal : 9 / 2 akan menghasilkan nilai 3,33
7. DIV (bagi) ini berfungsi untuk melakukan pembagian (hasil yang dikeluarkan akan berbentuk integer) misal : 9 DIV 2 akan menghasilkan nilai 3
8. contoh penerapan operator arithmethic yaitu : SELECT id, price DIV 1000 as 'Price in K' FROM products; perintah ini akan membagi 1000 tiap data price yang diambil.
9. selain dengan cara diatas, kita juga dapat menerapkan numeric function di dalam where clause.
10. Misalnya : SELECT id, name, price FROM products WHERE price DIV 1000 > 15;

--MATHEMATICAL FUNCTION--

1. selain operator arithmetic, di mysql juga terdapat mathematical function
2. mathematical function merupakan kumpulan function yang terdapat di mysql yang dapat kita gunakan untuk mempermudah kita melakukan operasi matematika
3. terdapat banyak sekali mathematical function di mysql
4. untuk daftar functionnya bisa dilihat melakui link : dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html
5. format penerapan mathematical function adalah sebagai berikut : SELECT namaMathematicalFunction(nama_kolom1), nama_kolom2 FROM nama_tabel;
6. misalnya : SELECT sin(price), cos(price), tan(price) FROM products;

--AUTO INCREMENT--

1. kadang ada kasus dimana kita ingin kolom primary key yang kita buat berisi data angka berurutan dari kecil ke besar secara otamatis tanpa harus kita masukkan angkanya.
2. untuk mengatasi masalah seperti ini, mysql memiliki fitur yang namanya auto increment, fitur ini bisa kita gunakan untuk menandai bahwa suatu primary key datanya diisi secara otomatis dari angka 1 kemudian setiap ada penambahan data maka data baru tersebut kolom primary keynya akan ditambah 1 dari data kolom primary key terakhir. misalnya kolom primary key dari data terakhir adalah 5 maka data yang baru masuk tersebut kolom primary keynya akan bernilai 6.
3. dengan menggunakan auto increment, kita tidak perlu lagi memasukkan nilai ke kolom primary key secara manual saat melakukan insert data karena kolom tersebut akan secara otomatis diisi oleh si mysql.
4. perlu diingat kolom yang akan ditambahkan auto increment harus bertipe data integer.
5. format menambahan auto increment adalah sebagai berikut : CREATE TABLE nama_tabel (nama_kolom1 INT NOT NULL AUTO_INCREMENT, nama_kolom2 tipe_data_kolom3, nama_kolom3 tipe_data_kolom3, danseterusnya, PRIMARY KEY (nama_kolom1)) ENGINE = InnoDB;
6. Misal : CREATE TABLE admin (id INT NOT NULL AUTO_INCREMENT, first_name VARCHAR(100) NOT NULL, last_name VARCHAR(100) NOT NULL, PRIMARY KEU (id)) ENGINE = InnoDB;
7. dengan ini kita hanya perlu mengisi kolom first_name dan last_name saja saat melakukan proses insert data ke dalam tabel admin karena kolom id akan secara otomatis di isikan oleh mysqlnya.
8. jadi saat insert data ke tabel admin kita hanya perlu menulis perintah : INSERT INTO (fist_name, last_name) VALUES ('nilai_first_name','nilai_last_name');

--MELIHAT ID TERAKHIR--

1. kadang setelah kita melakukan proses insert data ke dalam suatu tabel, kita ingin melihat id terakhir dari tabel yang kita insert tersebut.
2. di mysql ada function yang mendukung kasus tersebut. function tersebut yaitu LAST_INSERT_ID()
3. format penulisannya adalah sebagai berikut : SELECT LAST_INSERT_ID();

--STRING FUNCTION--

1. sama seperti tipe data number, di mysql juga banyak
   menyediakan function untuk tipe data string
2. daftar string function yang dapat kita gunakan bisa dilihat melalui link : dev.mysql.com/refman/8.0/en/string-functions.html
3. format penerapan string function adalah sebagai berikut : SELECT namaStringFunction(nama_kolom1), namaStringFunction(nama_kolom2), nama_kolom3, dan_seterusnya FROM nama_tabel;
4. misalnya : SELECT id, LOWER(name) as 'Name Lower' FROM products; string function lower didalam perintah ini akan merubah nilai dari tiap data pada kolom name menjadi lowercase atau hurufnya menjadi kecil semua
5. SELECT id name, LENGTH(name) as 'Name Length' FROM products; string function length didalam perintah ini akan menhasilkan nilai jumlah karakter dari tiap data pada kolom name.

--DATE AND TIME FUNCTION--

1. Mysql juga menyediakan banyak sekali function yang dapat kita gunakan untuk mengolah data dengan tipe data date and time;
2. daftar date and time function yang dapat kita gunakan bisa dilihat melalui link : dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html
3. format penerapan date and time function adalah sebagai berikut : SELECT namaDateAndTimeFunction(nama_kolom1), namaDateAndTimeFunction(nama_kolom2), nama_kolom3, dan_seterusnya FROM nama_tabel;
4. misalnya : SELECT id,created_at, YEAR(created_at) as 'Year', MONTH(created_at) FROM products; date and time function YEAR didalam perintah ini akan mengambil nilai tahunnya saja dari tiap data pada kolom created_at dan date and time function MONTH didalam perintah ini akan mengambil nilai bulannya saja dari tiap data pada kolom created_at.

--FLOW CONTROL FUNCTION--

1. mysql juga mimiliki fitur yang bernama flow control function
2. fitur ini mirip dengan IF ELSE pada bahasa pemrograman
3. tapi perlu diingat, fitur ini tidak se kompleks IF ELSE yang dimiliki bahasa pemrograman
4. jadi fitur ini hanya dapat digunakan pada kasus-kasus sederhana saja
5. penjelasan lengkap dari fitur flow control function dapat dilihat pada link : dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html
6. contoh penerapan fitur flow control function yaitu CASE adalah sebagai berikut : SELECT id CASE category WHEN 'Makanan' THEN 'Enak' WHEN 'Minuman' THEN 'Segar' ELSE 'Apa itu?' END AS 'Category' FROM products;
7. perintah ini akan menampilkan enak jika kolom category bernilai makanan lalu menampilkan segar jika kolom category bernilai minuman kemudian menampilkan apa itu ? jika kolom category bernilai selain makanan dan minuman.
8. contoh penerapan fitur flow control function yaitu IF adalah sebagai berikut : SELECT id, price, IF(price <= 15000, 'murah', IF(price <= 20000,'Mahal','Mahal Banget')) AS 'Mahal?' from products; perintah ini akan menampilkan murah jika nilai price kurang dari sama dengan 15000. kemudian menampilkan mahal jika lebih dari 15000 dan kurang dari 20000 lalu mahal banget jika lebih dari 20000
9. contoh penerapan fitur flow control function yaitu IFNULL adalah sebagai berikut : SELECT id, name, IFNULL(description,'kosong') as 'description' FROM products; perintah ini akan mengganti nilai dari tiap kolom description menjadi kosong jika terdapat nilai null pada kolom description

--AGGREGATE FUNCTION--

1. mysql juga mendukung function-function untuk melakukan aggreate atau agregasi
2. contoh agregasi misalnya kita ingin melihat harga paling mahal di tabel product (MAX), atau harga paling murah (MIN) atau rata-rata harga product (AVG) atau jumlah seluruh data yang ada di dalam tabel product (COUNT) dan lain sebagainya
3. daftar lengkap function function agregate dapat dilihat pada link : dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html
4. format penerapan agregate function adalah sebagai berikut : SELECT namaAgregateFunction(nama_kolom) FROM nama_tabel;
5. misalnya : SELECT COUNT(id) AS 'Total Product' FROM products; perintah ini akan menghasilkan keluaran jumlah seluruh data di dalam tabel products;
6. perlu diingat, aggregate function tidak bisa digabungkan dengan kolom biasa. Misalnya : SELECT COUNT(id) AS 'Total Product', name FROM products; jika kita menjalankan perintah ini maka kita akan mendapatkan error

--GROUP BY--

1. Kadang saat kita melakukan agregate pada sebuah tabel, kita ingin datanya di grouping berdasarkan kriteria tertentu terlebih dahulu.
2. misalnya : kita ingin melihat total harga product per kategory
3. atau kita ingin melihat harga product termahal per category
4. hal ini dapat kita lakukan menggunakan fitur GROUP BY clause
5. perlu diingat, fitur GROUP BY clause hanya dapat digunakan pada aggregate function saja.
6. penjelasan lengkap dari fitur GROUP BY clause ini dapat dilihat pada link : dev.mysql.com/doc/refman/8.0/en/group-by-modifiers.html
7. format penerapan GROUP BY clause adalah sebagai berikut : SELECT nama_kolom_untuk_grouping, namaagregatefunction(nama_kolom) FROM nama_tabel GROUP BY nama_kolom_untuk_grouping;
8. misalnya : SELECT category, COUNT(id) AS 'Total Product' FROM products GROUP BY category;
9. perintah diatas akan menampilkan total product per category. misalnya : total product dengan category makanan adalah 6 lalu total product dengan category minuman adalah 3.

--HAVING CLAUSE--

1. Kadang ada kasus dimana kita ingin melakukan filter terhadap data yang sudah kita grouping
2. misalnya kita ingin menampilkan total product per category, tapi hanya untuk category yang data productnya diatas 5 saja
3. Perlu diingat kita tidak dapat menggunakan WHERE clause pada aggregate function
4. untuk mengatasi kasus seperti diatas, kita dapat menggunakan fitur yang bernama HAVING clause.
5. HAVING clause ini memeliki cara kerja yang mirip dengan WHERE clause tapi fitur ini hanya dapat digunakan di aggregate function saja.
6. Format penerapan HAVING clause adalah sebagai berikut : SELECT nama_kolom_untuk_grouping, namaagregatefunction(nama_kolom) FROM nama_tabel GROUP BY nama_kolom_untuk_grouping HAVING filternya;
7. misalnya : SELECT category, COUNT(id) as 'total' FROM products GROUP BY category HAVING total > 5;
8. perintah diatas hanya akan menampilkan total product per category yang total productnya diatas 5 saja. Jadi jika sebuah category memiliki total product 5 kebawah, maka category tersebut tidak akan ditampilkan

--CONSTRAINT--

1. di mysql kita dapat menambahkan yang namanya constraint. Constraint digunakan untuk menjaga data di dalam tabel tetap baik.
2. constraint sangat bagus digunakan untuk menjaga data yang masuk ke dalam database. Jika suatu saat terjadi masalah pada validasi yang sudah kita buat di dalam aplikasi atau project kita, maka masih ada constraint yang melakukan proses validasi ke 2.
3. mysql memiliki 2 constraint yaitu unique constraint dan check constraint

--UNIQUE CONSTRAINT--

1. unique constraint adalah constraint yang memastikan bahwa data yang kita masukkan bersifat unique (tidak sama atau tidak duplikat dengan data yang lain)
2. jika kita mencoba mamasukkan data yang duplikat atau data yang sudah ada didalam tabel, maka mysql akan menolak data tersebut
3. kita dapat menambahkan unique contraint ketika membuat tabel baru atau menggunakan fitur ALTER TABLE.
4. format penambahan unique constraint ketika membuat tabel baru adalah sebagi berikut : CREATE TABLE nama_tabel_baru (nama_kolom1 tipe_data,nama_kolom2 tipe_data, danseterusnya, PRIMARY KEY(nama_kolom), UNIQUE KEY nama_unique_constraint(nama_kolom_yang_ingin_ditambahkan_unique_constraint)) ENGINE = InnoDB;
5. catatan : kita dapat memberi nama_unique_constraint dengan nama apapun yang kita inginkan. Tapi kebanyakan orang memberi nama dengan format nama_kolom_unique
6. misalnya : CREATE TABLE costomers(id INT NOT NULL AUTO_INCREMENT, email VARCHAR(100) NOT NULL, first_name VARCHAR(100) NOT NULL, last_name VARCHAR(100) NOT NULL, PRIMARY KEY(id), UNIQUE KEY email_unique(email)) ENGINE = InnoDB;
7. jika tablenya sudah terlanjur dibuat, kita juga dapat menambahkan unique contraint menggunakan perintah : ALTER TABLE nama_tabel ADD CONSTRAINT nama_unique_constraint UNIQUE (nama_kolom_yang_ingin_ditambahkan_unique_key);
8. misalnya : ALTER TABLE customers ADD CONSTRAINT email_unique UNIQUE (email); perintah ini akan menambahkan unique constraint ke dalam kolom email tabel customers
9. jika kita ingin menghapus unique constraint yang sudah kita tambahkan, kita dapat menggunakan perintah : ALTER TABLE nama_tabel DROP CONSTRAINT nama_unique_constraint;
10. misalnya : ALTER TABLE customers DROP CONSTRAINT email_unique; perintah ini akan menghapus unique constraint yang sudah kita tambahkan di kolom email

--CHECK CONSTRAINT--

1. kadang ada kasus dimana saat proses insert data baru, kita ingin memeriksa terlebih dahulu data tersebut sebelum menyimpannya secara permanen didalam database.
2. misalnya : kita ingin memastikan bahwa data product yang akan kita masukkan ke dalam tabel product harus memiliki harga diatas 1000. Jadi jika kita memasukkan data product dengan harga dibawah 1000 maka secara otomatis data tersebut akan ditolak.
3. untuk kasus seperti diatas kita dapat menggunakan check constraint.
4. kita dapat menambahkan check contraint ketika membuat tabel baru atau menggunakan fitur ALTER TABLE.
5. format penambahan check constraint ketika membuat tabel baru adalah sebagai berikut : CREATE TABLE nama_tabel_baru (nama_kolom1 tipe_data,nama_kolom2 tipe_data, dan_seterusnya, PRIMARY KEY(nama_kolom), CONSTRAINT nama_check_constraint CHECK (nama_kolom_yang_ingin_ditambahkan_check_constraint_dan_kondisinya)) ENGINE = InnoDB;
6. catatan : kita dapat memberi nama_check_constraint dengan nama apapun yang kita inginkan. Tapi kebanyakan orang memberi nama dengan format nama_kolom_check
7. misalnya : CREATE TABLE products (id VARCHAR(10) NOT NULL, name VARCHAR(100) NOT NULL, description TEXT, price INT UNSIGNED NOT NULL, quantity INT UNSIGNED NOT NULL DEFAULT 0, created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAP, PRIMARY KEY (id), CONSTRAINT price_check CHECK (price >= 1000));
8. check constraint pada perintah diatas hanya menyetujui kolom price pada tabel product diisi dengan nilai 1000 keatas.
9. jika tablenya sudah terlanjur dibuat, kita juga dapat menambahkan check contraint menggunakan perintah : ALTER TABLE nama_tabel ADD CONSTRAINT nama_check_constraint CHECK (nama_kolom_yang_ingin_ditambahkan_check_constraint_dan_kondisinya);
10. misalnya : ALTER TABLE products ADD CONSTRAINT price_check CHECK (price >= 1000);
11. check constraint pada perintah diatas hanya menyetujui kolom price pada tabel products diisi dengan nilai 1000 keatas
12. jika kita ingin menghapus check constraint yang sudah kita tambahkan, kita dapat menggunakan perintah : ALTER TABLE nama_tabel DROP CONSTRAINT nama_check_constraint;
13. misalnya : ALTER TABLE products DROP CONSTRAINT price_check; perintah ini akan menghapus check constraint yang sudah kita tambahkan di kolom price

--INDEX--

1. secara default, mysql akan menyimpan data di dalam disk seperti layaknya tabel biasa yaitu menyimpan seluruh data dalam bentuk tabular atau baris-perbaris
2. hal ini menyebabkan, ketika kita melakukan pencarian data di sebuah tabel, maka mysql akan melakukan proses pencarian data dari baris pertama sampai baris terakhir. Yang artinya semakin banyak data didalam sebuah tabel, maka akan semakin lambat proses pencarian datanya.
3. untuk mengatasi masalah ini, mysql memiliki fitur yaitu index. berbeda dengan struktur tabular, index akan menyimpan data menggunakan struktur B-Tree (balancing tree): en.wikipidia.org/wiki/B-tree
4. tidak hanya akan mempermudah kita saat melakukan pencarian, index juga akan mempermudah kita ketika melakukan pengurutan data menggunakan order by clause
5. penjelasan lengkap mengenai index di mysql dapat dilihat melalui link : dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html

--CARA KERJA INDEX--

1. kita dapat membuat lebih dari satu index didalam sebuah tabel. Dan kita juga dapat membuat 1 index untuk beberapa kolom sekaligus
2. misalnya kita ingin membuat index di sebuah tabel dengan gabungan kolom1, kolom2, dan kolom3.
3. itu artinya index ini hanya bekerja pada kasus pencarian dengan kombinasi query where (kolom1 saja), (kolom1 dan kolom2 saja) dan (kolom1, kolom2, dan kolom3)
4. akan tetapi index ini tidak akan bekerja pada kombinasi query where (kolom2 saja), (kolom2 dan kolom3), dan (kolom3 saja)

--EFEK SAMPING PENGGUNAAN INDEX--

1. index mungkin akan mempercepat proses pencarian dan query data
2. namun saat membuat index, itu artinya mysql akan melakukan proses update data di index setiap kali kita menambah, mengubah dan menghapus data di dalam tabel tersebut.
3. jadi sederhananya index akan membuat proses pencarian dan query data lebih cepat, tapi index akan memperlambat proses manipulasi data (insert,update,delete)
4. oleh karena itu, kita harus lebih bijak saat menggunakan index ini.

--TIDAK PERLU INDEX--

1. saat suatu kolom sudah memiliki PRIMARY KEY dan UNIQUE constraint, maka kita tidak perlu lagi untuk menambahkan index ke kolom tersebut
2. hal ini dikarenakan MySQL akan secara otomatis menambahkan index pada kolom PRIMARY KEY dan UNIQUE constraint

--MENAMBAHKAN INDEX KE KOLOM--

1. untuk menambahkan index ke kolom di dalam sebuah tabel, kita dapat melakukannya saat membuat tabel baru
2. format penambahan index saat membuat tabel baru adalah sebagai berikut : CREATE TABLE nama_tabel_baru (nama_kolom1 tipe_data, nama_kolom2 tipe_data, dan_seterusnya, INDEX nama_index (nama_kolom1,nama_kolom2,dan_seterusnya)) ENGINE = InnoDB;
3. catatan : kita dapat memberi nama_index dengan nama apapun yang kita inginkan.
4. misalnya : CREATE TABLE sellers (id INT NOT NULL, AUTO_INCREMENT, name VARCHAR(100) NOT NULL, name2 VARCHAR(100) NOT NULL, name3 VARCHAR(100) NOT NULL, email VARCHAR(100) NOT NULL, PRIMARY KEY(id), UNIQUE KEY email_unique(email), INDEX name_index(name), INDEX name2_index(name2),INDEX name1_name2_name3_index (name,name2,name3)) ENGINE = InnoDB;
5. pada perintah diatas, kita akan menambahkan 3 buah index yaitu index untuk kolom name, lalu index untuk kolom name2, dan terakhir index untuk gabungan kolom name, name2 dan name3
6. jadi jika kita menjalankan perintah SELECT _ from sellers WHERE name = 'apa itu'; maka index yang dipakai adalah name_index. jika kita menjalankan perintah SELECT _ from sellers WHERE name2 = 'apa itu'; maka index yang dipakai adalah name2*index. jika kita menjalankan perintah SELECT * from sellers WHERE name = 'apa itu' AND name2 = 'apa itu'; atau SELECT \_ from sellers WHERE name = 'apa itu' AND name2 = 'apa itu' OR name3 = 'apa itu'; maka index yang dipakai adalah name1_name2_name3_index.
7. jika kita ingin menambahkan index ke tabel yang sudah terlanjur dibuat, maka kita dapat menggunakan perintah : ALTER TABLE nama_tabel ADD INDEX nama_index (kolom_yang_ingin_dijadikan_index);
8. misalnya : ALTER TABLE sellers ADD INDEX name_index(name); perintah ini akan menambah index untuk kolom name yang ada didalam tabel sellers
9. jika kita ingin menghapus index yang sudah dibuat, maka kita bisa menggunakan perintah : ALTER TABLE nama_tabel DROP INDEX nama_index
10. misalnya : ALTER TABLE sellers DROP INDEX name_index; perintah ini akan menghapus index yang bernama name_index yang ada di dalam tabel sellers

--FULL-TEXT SEARCH--

1. kadang saat kita ingin mencari sebuah kata didalam suatu tabel, biasanya kita akan menggunakan LIKE operator
2. akan tetapi pencarian kata menggunakan LIKE operator ini sangat lambat. Karena operasi yang dilakukan LIKE operator ini adalah dengan cara mencari seluruh data di dalam tabel dari kata pertama pada baris data pertama sampai kata terakhir pada baris data terakhir.
3. walaupun kita menambah index pada tabel tersebut, itu juga tidak akan membantu karena LIKE operator tidak akan menggunakan index tersebut.
4. untuk mengatasi masalah pencarian data yang lambat, untungnya mysql memiliki fitur yang namanya full-text search
5. full-text search memungkinkan kita untuk mencari sebagian kata di dalam kolom dengan tipe data string
6. ini sangat cocok digunakan ketika menghadapi kasus pencarian kata didalam suatu kalimat
7. penjelasan lebih lengkapnya dapat dilihat pada : dev.mysql.com/doc/refman/8.0/fulltext-search.html
8. tapi perlu di ingat, fitur full-text search ini tidak se bagus database yang memang difokuskan untuk melakukan proses pencarian data seperti : elastic search dan apache solr

--MEMBUAT TABEL DENGAN FULL-TEXT SEARCH--

1. sebelum menggunakan fitur full-text search, pertama-tama kita harus mendaftarkan kolom-kolom apa saja yang akan diberi fitur full-text search ini
2. untuk mendaftarkan kolom-kolom tersebut, kita dapat melakukannya pada saat membuat tabel dan saat kita melakukan alter tabel
3. format penambahan fulltext search pada saat membuat tabel baru adalah sebagai berikut : CREATE TABLE nama_tabel (nama_kolom1 tipe_data, nama_kolom2 tipe_data, danseterusnya, FULLTEXT nama_fulltext (nama_kolom_kolom_yang_ingin_ditambahkan_fitur_fulltext_search)) ENGINE=InnoDB;
4. kita dapat memberi nama_fulltext dengan nama apapun yang kita inginkan.
5. misalnya : CREATE TABLE products (id VARCHAR(10) NOT NULL, name VARCHAR(100) NOT NULL, description TEXT, price INT UNSIGNED NOT NULL, quantity INT UNSIGNED NOT NULL, created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP, PRIMARY KEY(id), FULLTEXT product_search (name, description)) ENGINE = InnoDB;
6. FULLTEXT pada perintah diatas, akan menambahkan fulltext search pada kolom name dan description dengan nama product_search.
7. jika kita sudah terlanjur membuat tabel dan tetap ingin mendaftarkan fulltext search pada kolom kolom ditabel tersebut, kita dapat menggunakan perintah : ALTER TABLE nama_tabel ADD FULLTEXT nama_fulltext (nama_kolom_kolom_yang_ingin_ditambahkan_fitur_fulltext_search);
8. misalnya : ALTER TABLE products ADD FULLTEXT product_search (name,description);
9. jika kita ingin menghapus fulltext search yang sudah tambahkan pada suatu tabel, kita dapat menggunakan perintah : ALTER TABLE nama_tabel DROP INDEX nama_fulltext; (walaupun yang kita tambahkan adalah FULLTEXT tetapi jika ingin menghapusnya kita akan menggunakan INDEX)
10. misalnya : ALTER TABLE products DROP INDEX product_search;
11. catatan : cara kerja dari FULLTEXT ini mirip seperti INDEX, tetapi FULLTEXT ini hanya dikususkan untuk pencarian sebagian kata didalam data bertipe string.

--MODE-MODE SAAT MELAKUKAN PENCARIAN MENGGUNAKAN FULLTEXT SEARCH--

1. mysql menyediakan beberapa mode untuk melakukan pencarian menggunakan full-text search, kita dapat memilihnya sesuai kebutuhan kita. Beberapa mode tersebut adalah sebagai berikut :
2. Natural language, yaitu model pencarian per-kata. misalnya: kata ayam pada kalimat mie ayam bakso, kata original pada kalimat mie ayam original, dan lain sebagainya. Untuk lebih lengkapnya kita dapat melihatnya pada link dev.mysql.com/doc/refman/8.0/en/fulltext-natural-language.html
3. Boolean, yaitu model pencarian yang memiliki kemampuan mengandung kata (+) atau tidak mengandung kata (-). Misalnya mie pada kalimat mie ayam bakso (kata mie pada kalimat disamping mengandung kata mie), original pada kalimat mie ayam original (kata original pada kalimat disamping mengandung kata original). untuk lebih lengkapnya kita dapat melihatnya pada link : dev.mysql.com/doc/refman/8.0/en/fulltext-boolean.html
4. quary expansion, yaitu model pencarian yang mirip dengan natural language, namun mode ini akan melakukan 2 kali pencarian. pencarian pertama akan menggunakan mode natural language,kemudian pencarian kedua akan melakukan pencarian menggunakan kedekatan dari hasil yang didapat dari pencarian pertama. misalnya : kita mencari kata bakso, lalu ternyata didalam kata bakso terdapat kata mie, maka kemungkinan hasil pencarian kedua akan mencari kata mie. untuk lebih lengkapnya dapat dilihat pada link : dev.mysql.com/doc/refman/8.0/en/fulltext-query-expansion.com.html

--MENCARI MENGGUNAKAN MODE NATURAL LANGUAGE--

1. untuk melakukan pencarian mengguankan mode natural language, kita dapat menggunakan perintah dengan format : SELECT \* FROM nama_tabel WHERE MATCH (nama_kolom_kolom_yang_sebelumnya_sudah_ditambahkan_fulltext) AGAINST ('katayangdicari' IN NATURAL LANGUAGE MODE);
2. misalnya SELECT \* FROM products WHERE MATCH(name, description) AGAINST('ayam' IN NATURAL LANGUAGE MODE);
3. perintah diatas akan mencari data-data yang didalamnya terdapat kata ayam menggunakan mode natural language

--MENCARI DENGAN MODE BOOLEAN--

1. untuk melakukan pencarian menggunakan mode boolean, kita dapat menggunakan perintah dengan format : SELECT \* FROM nama_tabel WHERE MATCH(nama_kolom_kolom_yang_sebelumnya_sudah_ditambahkan_fulltext) AGAINST('+mengandungkata -tidakmengandungkata' IN BOOLEAN MODE);
2. tanda + pada format diatas menandakan bahwa data yang ditampilkan harus mengandung kata yang dimasukkan
3. tanda - pada format diatas menandakan bahwa data yang ditampilkan harus tidak mengandung kata yang dimasukkan
4. catatan kita dapat menambahkan +mengandungkata dan -tidakmengandungkata sebanyak yang kita inginkan. Tetapi ingat semakin banyak yang kita tambahkan, maka semakin lambat proses querynya. Jadi kita harus bijak dalam menggunakannya
5. misalnya : SELECT \* FROM products WHERE MATCH(name, description) AGAINST('+mie -bakso' IN BOOLEAN MODE);
6. perintah diatas akan mencari data-data yang didalamnya mengandung kata mie tapi tidak mengandung kata bakso

--MENCARI DENGAN MODE QUERY EXPANSION--

1. untuk melakukan pencarian menggunakan mode query expansion, kita dapat menggunakan perintah dengan format : SELECT \* FROM nama_tabel WHERE MATCH(nama_kolom_kolom_yang_sebelumnya_sudah_ditambahkan_fulltext) AGAINST('katayangdicari' WITH QUERY EXPANSION);
2. misalnya : SELECT \* FROM products WHERE MATCH(name,description) AGAINST('bakso' WITH QUERY EXPANSION);
3. perintah diatas akan mencari data data yang didalamnya terdapat kata bakso dan mendekati kata bakso

--RELASI ANTAR TABEL (TABLE RELATIONSHIP)--

1. dalam relational DBMS, salah satu fitur andalannya adalah table relationship atau relasi antar tabel
2. dengan ini, kita dapat melakukan relasi antara tabel satu dengan tabel yang lainnya dengan mudah
3. dalam kehidupan nyatapun kita sering menghadapi kasus dimana kita harus melakukan relasi antar tabel.
4. misalnya : pada aplikasi penjualan online kita ingin membuat laporan penjualan, maka kita harus melakukan relasi antara tabel barang dan tabel penjualan.
5. misalnya : di dalam aplikasi kampus, tabel mahasiswa akan berelasi dengan tabel mata kuliah dan tabel dosen
6. dan lain sebagainya

--FOREIGN KEY--

1. saat membuat relasi antar tabel, bisanya kita akan membuat sebuah kolom yang berfungsi sebagai referensi ke tabel lainnya (tabel yang ingin direlasi)
2. misalnya saat kita membuat tabel penjualan, maka di dalam tabel penjualan, kita akan menambahkan sebuah kolom yang bernama id_produk sebagai referensi ke tabel produk, kolom ini nantinya akan diisi dengan id-id dari tabel produk
3. kolom referensi ini di mysql dinamakan foreign key (kunci asing)
4. kita dapat menambahkan lebih dari satu foreign key ke dalam sebuah tabel
5. pembuatan kolom untuk foreign key sama seperti pembuatan kolom biasa, hanya saja kita perlu memberi tahu mysql bahwa kolom tersebut adalah foreign key ke tabel lain
6. catatan : biasanya referensi dari kolom foreign key akan menggunakan kolom primary key dari tabel yang ingin direlasikan.
7. misalnya : tabel wishwist akan berelasi dengan tabel produk maka didalam tabel wistlist, kita akan membuat sebuah kolom yang bernama id_produk. Kolom ini akan menggunakan kolom id dari tabel produk sebagai referensinya. (Kolom id yang ada di tabel produk merupakan sebuah primary key)
8. tipe data dari kolom yang akan dijadikan foreign key harus sama dengan tipe data kolom yang akan dijadikan referensi. jadi jika kolom id pada tabel produk memiliki tipe data INT maka kolom id_produk pada tabel wishlist harus memiliki tipe data INT juga.

--MENAMBAHKAN FOREIGN KEY KE DALAM TABEL--

1. terdapat 2 cara untuk menambahkan foreign key ke dalam sebuah tabel, yaitu menambahkan foreign key pada saat membuat tabel dan menambahkan foreign key menggunakan perintah ALTER TABLE.
2. format penambahan foreign key pada saat membuat tabel adalah sebagai berikut : CREATE TABLE nama_tabel(nama_kolom1 tipe_data, nama_kolom2 tipe_data, danseterusnya, PRIMARY KEY (nama_kolom), CONSTRAINT nama_foreign_key FOREIGN KEY(nama_kolom_yang_ingin_dijadikan_foreign_key) REFERENCES nama_tabel_yang_akan_direlasi_dengan_tabel_ini(nama_kolom_yang_akan_dibuat_referensi)) ENGINE = InnoDB;
3. catatan : kita dapat memberi nama_foreign_key dengan nama apapun yang kita inginkan. tapi kebanyakan orang menggunakan format : fk_namatabelsaatini_namatabelyangdirelasi
4. misalnya : CREATE TABLE wishlist (id INT NOT NULL AUTO_INCREMENT, id_product VARCHAR(10) NOT NULL, description TEXT, PRIMARY KEY (id), CONSTRAINT fk_wishlist_product FOREIGN KEY (id_product) REFERENCES products (id)) ENGINE = InnoDB;
5. pada perintah diatas kita menambahkan foreign key ke tabel wishlist (id_product) menggunakan referensi dari tabel products (id)
6. jika kita ingin menambahkan foreign key ke dalam tabel yang sudah terlanjut di buat, kita dapat menggunakan perintah dengan format : ALTER TABLE nama_tabel ADD CONSTRAINT nama_foreign_key FOREIGN KEY (nama_kolom_yang_ingin_dijadikan_foreign_key) REFERENCES nama_tabel_yang_akan_direlasi_dengan_tabel_ini (nama_kolom_yang_akan_dibuat_referensi);
7. misalnya : ALTER TABLE wishlist ADD CONSTRAINT fk_wishlist_product FOREIGN KEY (id_product) REFERENCES products (id);
8. jika kita ingin menghapus foreign key yang sudah dibuat didalam suatu tabel, kita dapat menggunakan perintah dengan format : ALTER TABLE nama_tabel DROP CONSTRAINT nama_foreign_key;
9. perlu diingat perintah diatas hanya menghapus foreign keynya saja. Jadi kolom yang dijadikan foreign key tidak akan ikut terhapus.
10. misalnya : ALTER TABLE wistlist DROP CONSTRAINT fk_wishlist_product;

--KEUNTUNGAN MENGGUNAKAN FOREIGN KEY--

1. foreign key memastikan bahwa data yang kita masukkan ke kolom yang dijadikan foreign key harus tersedia di tabel referencenya. Jadi jika kita memasukkan nilai yang tidak ada di kolom reference nya maka nilai tersebut akan ditolak. Misal kita memasukkan nilai pxxx ke dalam kolom id_produk dan ternyata nilai pxxx tidak ada didalam kolom id tabel products, maka nilai pxxx akan ditolok oleh mysql.
2. selain itu, saat kita menghapus data di tabel yang dijadikan reference, maka mysql akan mengecek terlebih dahulu apakah nilai kolom yang dijadikan reference tersebut masih digunakan di foreign key tabel lain atau tidak. Jika ternyata masih digunakan, maka mysql akan secara otomatis menolak proses delete data di tabel reference tersebut.
3. misalnya kita ingin menghapus data di tabel products yang memiliki id P0001 dan ternyata id P0001 masih digunakan oleh tabel wishlist (dengan kata lain terdapat nilai P0001 didalam kolom id_product tabel wishlist), maka mysql akan menolak untuk menghapus data di tabel products yang memiliki id P0001 tersebut.

--KETIKA MENGHAPUS DATA BERELASI--

1. seperti yang kita bahas diatas, ketika kita menghapus data yang berelasi (nilai kolom referencenya masih digunakan tabel lain), maka secara otomatis mysql akan menolak operasi delete data tersebut.
2. sebenarnya kita bisa saja mengubah behavior ini jika kita mau, ada banyak hal yang bisa dilakukan ketika data berelasi dihapus, dan pengaturan defaultnya memang akan ditolak (RESTRICT) jika data yang masih berelasi itu dihapus.

--PILIHAN BEHAVIOR PADA FOREIGN KEY--

1. berikut ini adalah beberapa pilihan behavior yang dapat kita gunakan :
2. RESTRICT : jika kita mengatur foreign key dengan behavior ini, maka saat menghapus data pada tabel reference yang masih berelasi, mysql akan menolaknya. Begitu juga saat merubah nilai dari kolom yang menjadi reference yang masih berelasi maka mysql akan menolaknya juga. Misalnya kita ingin merubah nilai dari kolom id tabel products dari P0001 ke PXXXX dan ternyata nilai P0001 masih digunakan di tabel wishlist, maka proses update data tersebut akan ditolak (behavior ini adalah behavior default pada foreign key. Jadi jika kita tidak mengatur behaviornya maka secara otomatis behaviornya akan di setting restrict)
3. CASCADE : jika kita mengatur foreign key dengan behavior ini, maka saat menghapus data pada tabel reference yang masih berelasi, maka mysql juga akan menghapus data di tabel lain yang memiliki relasi dengan data tersebut. Misalnya : kita ingin menghapus data products yang memiliki id P0001, maka semua data wishlist yang memiliki id_produk P0001 juga akan ikut terhapus. Dan jika kita merubah nilai dari kolom yang menjadi reference yang masih berelasi maka mysql juga akan ikut merubah nilai kolom foreign key di tabel lain yang memiliki relasi dengan nilai yang diubah tersebut. Misalnya : kita merubah nilai dari kolom id tabel products dari P0001 ke PXXXX, maka semua nilai pada kolom id_produk tabel wishlist yang bernilai P0001 akan diganti dengan nilai PXXXX
4. NO ACTION : jika kita mengatur foreign key dengan behavior ini, maka saat menghapus data pada tabel reference yang masih berelasi, maka mysql tidak akan menolak proses deletenya dan data-data yang berelasi dengan data yang dihapus akan di biarkan (data tersebut tidak akan ikut dihapus (data tersebut tetap akan seperti semula)). Gampangnya hanya menghapus data yang ingin dihapus (tidak mempengaruhi data data relasinya). misalnya : kita menghapus data products yang memiliki id P0001, maka hanya data itu saja yang dihapus dan data-data wishlist yang memiliki id_produk P0001 tidak akan ikut dihapus (data-data tersebut tetap ada di tabel wishlist). jika kita merubah nilai dari kolom yang menjadi reference yang masih berelasi, maka mysql juga akan membiarkan nilai kolom foreign key di tabel lain yang memiliki relasi dengan nilai yang diubah tersebut. Misalnya : kita merubah data products dari yang semula idnya bernilai P0001 menjadi PXXXX maka hanya data di tabel products aja yang akan berubah dan data-data di tabel wishlist yang memiliki id_produk P0001 akan tetap bernilai P0001.
5. SET NULL : jika kita mengatur foreign key dengan behavior ini, maka saat menghapus data pada tabel reference yang masih berelasi, maka mysql akan merubah nilai-nilai kolom foreign key tabel lain yang berelasi dengan data tersebut menjadi NULL. misalnya : kita menghapus data products yang memiliki id P0001 maka data-data wishlist yang memiliki nilai id_produk P0001 akan diganti nilai id_produknya menjadi NULL. begitu pula jika kita merubah nilai dari kolom yang menjadi reference yang masih berelasi maka mysql juga akan merubah nilai-nilai kolom foreign key tabel yang berelasi dengan data tersebut menjadi NULL. Misalnya kita merubah data products yang semula nilai kolom id nya P0001 menjadi PXXXX, maka data-data wishlist yang memiliki id_produk bernilai P0001 akan dirubah nilai id_produknya menjadi NULL.

--MERUBAH BEHAVIOR FOREIGN KEY--

1. untuk merubah behavior dari sebuah foreign key, kita dapat melakukan menggunakan format : ALTER TABLE nama_tabel ADD CONSTRAINT nama_foreign_key FOREIGN KEY (nama_kolom_yang_akan_dijadikan_foreign_key) REFERENCES nama_tabel_yang_akan_direlasi(nama_kolom_yang_akan_dijadikan_reference) ON DELETE jenis_behavior_yang_diinginkan ON UPDATE jenis_behavior_yang_diinginkan;
2. misalnya : ALTER TABLE wishlist ADD CONSTRAINT fk_wishlist_product FOREIGN KEY (id_product) REFERENCES products (id) ON DELETE CASCADE ON UPDATE CASCADE;
3. pada perintah diatas, kita merubah behavior dari foreign key menjadi CASCADE saat di hapus dan juga CASCADE saat di update.

--JOIN--

1. kadang, ada kasus dimana kita harus melakukan query SELECT ke beberapa tabel secara bersamaan.
2. untungnya mysql mendukung untuk melakukan proses tersebut. Untuk melakukan hal tersebut, kita dapat menambah perintah JOIN pada perintah SELECT.
3. tapi sebelum itu, untuk melakukan proses JOIN, kita perlu menentukan tabel mana yang merupakan referensi ke tabel lain (gampangnya harus ada kolom yang menjadi penghubung antara tabel a dan tabel b).
4. maka dari itu, foreign key sangat cocok jika dipadukan dengan join. Walaupun di mysql tidak ada aturan kalau JOIN harus dipadukan dengan foreign key.
5. di mysql, join dapat dilakukan pada lebih dari 2 tabel
6. tapi perlu diingat, semakin banyak tabel yang kita JOIN, maka proses querynya akan semakin berat dan juga lambat. Jadi harap bijak ketika melakukan JOIN.
7. idealnya kita melakukan JOIN paling banyak adalah 5 tabel saja, karena jika kita melakukan join lebih dari 5 tabel bisa berdampak ke performa query yang lambat.

--MELAKUKAN JOIN TABLE--

1. untuk melakukan proses join tabel, kita dapat menggunakan perintah dengan format : SELECT \* FROM nama_tabel1 JOIN nama_tabel2 ON (nama_tabel1.kolom_penghubung_ditabel1 = nama_tabel2.kolom_penghubung_ditabel2);
2. misalnya : SELECT \* FROM wishlist JOIN products ON (wishlist.id_product = products.id);
3. pada perintah diatas, kita melakukan join antara tabel wishlist dan tabel products. Penghubung antara tabel wishlist dan tabel products adalah kolom id_product tabel wishlist (merupakan kolom foreign key tabel wishlist) dan kolom id tabel product (merupakan reference dari foreign key id_product tabel wishlist)
4. saat kita melakukan join menggunakan perintah diatas, maka data-data di semua kolom tabel1 maupun tabel2 akan ditampilkan. Kadang kita hanya ingin menampilkan data-data pada kolom-kolom tertentu saja (tidak menampilkan semua kolomnya dan hanya menampilkan beberapa kolom saja).
5. untuk masalah seperti ini, kita dapat melakukan JOIN menggunakan perintah dengan format : SELECT nama_tabel1.nama_kolom1, nama_tabel1.nama_kolom2, nama_tabel2.nama_kolom1, nama_tabel12.nama_kolom2,danseterusnya FROM nama_tabel1 JOIN nama_tabel2 ON (nama_tabel1.kolom_penghubung_ditabel1 = nama_tabel2.kolom_penghubung_ditabel2);
6. misalnya : SELECT products.id, products.name, wishlist.description FROM wishlist JOIN products ON (products.id = wishlist.id_product);
7. perintah diatas hanya akan menampilkan data-data kolom id dan kolom name yang ada ditabel products dan data-data kolom description yang ada di tabel wishlist
8. jika terdapat nama kolom yang sama dikedua tabel atau nama tabel terlalu panjang, kita dapat merubah nama kolom dengan alias dan menyingkat nama tabel tersebut dengan alias juga
9. misalnya : SELECT w.id AS id_wishlist, p.id AS id_product, p.name AS product_name, w.description AS wishlist_description FROM wishlist AS w JOIN products AS p ON (w.id_product = p.id);
10. pada perintah diatas, kita merubah nama kolom id pada tabel wishlist menjadi id_wishlist dan merubah nama kolom id pada tabel products menjadi id_product . Kemudian kita juga merubah nama tabel wishlist menjadi w dan merubah nama tabel products menjadi p supaya lebih singkat dan ringkas.

--MELAKUKAN JOIN MULTIPLE TABLE--

1. kadang ada kasus dimana kita perlu melakukan JOIN lebih dari 2 tabel.
2. untuk kasus seperti ini, kita dapat melakukan join dengan format : SELECT \* FROM nama_tabel1 JOIN nama_tabel2 ON (nama_tabel1.kolom_penghubung_ditabel1 = nama_tabel2.kolom_penghubung_ditabel2) JOIN nama_tabel3 ON (nama_tabel1.kolom_penghubung_ditabel1 = nama_tabel3.kolom_penghubung_ditabel3);
3. misalnya : SELECT customers.email, products.id, products.name, wishlist.description FROM wishlist JOIN products ON (products.id = wishlist.id_product) JOIN customers ON (customers.id = wishlist.id_customer);
4. note : sebelum menjalankan perintah diatas, kita perlu untuk membuat foreign key ke 2 untuk tabel wishlist yang bernama id_customer. foreign key ini akan references ke kolom id pada tabel customers.
5. pada point no 3 diatas, kita melakukan join ke 3 tabel yaitu tabel wishlist, tabel products dan tabel customers.

--JENIS-JENIS RELASI TABEL--

1. sekarang kita sudah tau untuk melakukan relasi antar tabel, kita dapat menggunakan FOREIGN KEY sebagai penghubungnya.
2. dan untuk melakukan query SELECT ke beberapa tabel sekaligusm kita dapat menggunakan JOIN.
3. dalam konsep relasi, sebenarnya terdapat banyak jenis relasi antar tabel.
4. diantaranya adalah one to one relationship, one to many relationship dan many to many relationship

--ONE TO ONE RELATIONSHIP--

1. one to one relationship merupakan relasi antar tabel yang paling sederhana
2. itu artinya setiap data di sebuah tabel hanya boleh berelasi ke maksimal 1 data saja di tabel lainnya (tabel relasinya)
3. one to one relationship tidak memperbolehkan sebuah data memiliki lebih dari 1 relasi
4. contoh kasusnya adalah saat kita membuat aplikasi toko online yang tedapat fitur walletnya, maka 1 customer cuma boleh memiliki 1 wallet (dompet) saja.

--MEMBUAT ONE TO ONE RELATIONSHIP--

1. cara membuat one to one relationship cukup mudah
2. kita dapat membuat kolom foreign key, lalu set kolom tersebut menggunakan UNIQUE KEY, hal ini dilakukan untuk mencegah terjadinya data duplikat (data sama) pada kolom tersebut
3. format pembuatan tabel untuk one to one relationship adalah sebagai berikut : CREATE TABLE nama_tabel (nama_kolom1 tipe_data, nama_kolom2 tipe_data, danseterusnya, PRIMARY KEY(nama_kolom), UNIQUE KEY nama_unique_key(nama_kolom_yang_ingin_dijadikan_foreign_key), CONSTRAINT nama_foreign_key FOREIGN KEY (nama_kolom_yang_ingin_dijadikan_foreign_key) REFERENCES nama_tabel_yang_ingin_direlasi(nama_kolom_yang_ingin_digunakan_referensi)) INGINE = InnoDB;
4. misalnya : CREATE TABLE wallet (id INT NOT NULL AUTO_INCREMENT, id_customer INT NOT NULL, balance INT NOT NULL DEFAULT 0, PRIMARY KEY (id), UNIQUE KEY id_customer_unique(id_customer), CONSTRAINT fk_wallet_customer FOREIGN KEY (id_customer) REFERENCES customers (id)) ENGINE = InnoDB;
5. pada perintah diatas, kita membuat foreign key dan unique key menggunakan kolom id_customer. Ini dimaksudkan supaya foreign key id_customer tidak dapat di isi dengan nilai duplikat supaya memenuhi syarat dari one to one relationship.
6. cara join nya mirip dengan cara join yang sudah di jelaskan pada materi sebelumnya

--ONE TO MANY RELATIONSHIP--

1. one to many relationship adalah relasi antar tabel dimana sebuah data dapat berelasi dengan banyak data di tabel lain (tabel relasinya)
2. berbeda dengan one to one yang cuma dapat digunakan maksimal 1 kali ditabel relasinya, pada one to many tidak ada batasan berapa banyak sebuah data itu digunakan.
3. contoh relasi one to many adalah relasi antara tabel categories dan tabel products, dimana sebuah data dari tabel categories dapat digunakan oleh banyak data dari tabel products (one category to many products)
4. pembuatan relasi one to many sebenarnya mirip dengan one to one, yang membedakan adalah kita tidak perlu menambahkan UNIQUE KEY kedalam kolom foreign key, karena kolom foreign keynya memang dapat berisi nilai duplikat (1 nilai dari kolom reference dapat berkali-kali ditambahkan ke dalam kolom foreign key tabel relasinya).

--MEMBUAT ONE TO MANY RELATIONSHIP--

1. format pembuatan tabel untuk one to many relationship adalah sebagai berikut : CREATE TABLE nama_tabel (nama_kolom1 tipe_data, nama_kolom2 tipe_data, danseterusnya, PRIMARY KEY(nama_kolom), CONSTRAINT nama_foreign_key FOREIGN KEY (nama_kolom_yang_ingin_dijadikan_foreign_key) REFERENCES nama_tabel_yang_ingin_direlasi(nama_kolom_yang_ingin_digunakan_referensi)) INGINE = InnoDB;
2. cara join nya mirip dengan cara join yang sudah di jelaskan pada materi sebelumnya

--MANY TO MANY RELATIONSHIP--

1. many to many merupakan relasi tabel yang paling kompleks dan kadang membingungkan untuk pemula
2. definisi many to many adalah relasi antara 2 tabel dimana tabel pertama dapat punya banyak relasi ditabel kedua, dan tabel kedua pun dapat punya banyak relasi di tabel pertama (sederhanya kolom yang digunakan sebagai penghubung antara tabel a dan tabel b dapat berisi nilai duplikat)
3. ini memang sedikit membingungkan, bagaimana caranya kita bisa membuat relasi kebanyak data secara bolak balik sedangkan kita hanya masing masing 1 kolom saja sebagai penghubung antara 2 tabel ?
4. contoh relasi many to many adalah relasi antara tabel produk dan tabel order, dimana setiap data produk dapat diorder berkali kali (1 data produk dapat memiliki banyak data order) dan setiap data order dapat berisi lebih dari 1 produk (1 data order dapat memiliki banyak data produk)

--IMPLEMENTASI RELASI MANY TO MANY--

1. untuk membuat relasi many to many antara 2 buah tabel, mula mula kita perlu menambahkan sebuah tabel yang berfungsi sebagai jembatan untuk menggabungkan tabel pertama dan tabel tabel kedua
2. isi dari tabel tambahan ini adalah id dari tabel pertama dan id dari tabel kedua, dalam kasus ini adalah id_product dan id_order
3. dengan demikian, kita dapat menambahkan beberapa data ke dalam tabel relasi ini, sehingga akan tercipta 1 product bisa dijual beberapa kali dan 1 order bisa membeli lebih dari 1 product.

--CONTOH PEMBUATAN TABEL UNTUK RELASE MANY TO MANY--

1. pertama-tama kita membuat 1 buah tabel order dengan format : CREATE TABLE orders (id INT NOT NULL AUTO_INCREMENT, total INT NOT NULL, order_date DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP, PRIMARY KEY (id)) ENGINE = InnoDB;
2. karena tabel products sudah di buat pada pembahasan sebelumnya, maka selanjutnya kita akan membuat tabel order_detail (tabel ini berfungsi sebagai jembatan penghubung antara tabel orders dan tabel products) dengan format : CREATE TABLE orders_detail (id_product VARCHAR(10) NOT NULL, id_order INT NOT NULL, price INT NOT NULL, quantity INT NOT NULL, PRIMARY KEY (id_product, id_order), CONSTRAINT fk_orders_detail_order FOREIGN KEY (id_order) REFERENCES orders (id), CONSTRAINT fk_orders_detail_product FOREIGN KEY (id_product) REFERENCES products (id));
3. setelah membuat tabelnya, maka kita dapat melakukan select join many to many antara tabel products dan tabel orders
4. perintah select join many to many antara tabel orders dan tabel products adalah sebagai berikut : SELECT \* FROM orders JOIN orders_detail ON (orders_detail.id_order = orders.id) JOIN products ON (products.id = orders_detail.id_product);
5. catatan: pada pembuatan tabel orders_detail, kita menambahkan kolom price supaya harga product yang diorder tidak ikut berubah ketika price pada data product diubah. Ini dilakukan supaya biaya pada product yang diorder tetap konsisten (tidak ikut berubah mengikuti biaya product saat ini).

--JENIS-JENIS JOIN--

1. pada pembahasan sebelumnya, kita sudah banyak membahas tentang JOIN table, tapi sebenarnya join sendiri memiliki banyak jenis, diantaranya adalah INNER JOIN, LEFT JOIN, RIGHT JOIN dan CROSS JOIN

--INNER JOIN--

1. INNER JOIN merupakan mekanisme join, dimana terdapat relasi antara tabel pertama dan tabel kedua
2. konsep dari inner join adalah jika ada data di tabel pertama yang tidak memiliki relasi di tabel kedua ataupun sebaliknya, maka INNER JOIN tidak akan menampilkannya (sederhananya hanya menampilkan data-data yang memiliki relasi saja).
3. INNER JOIN merupakan default join di mysql, jadi jika kita menggunakan JOIN saja seperti yang sudah di praktekan pada pembahasan sebelumnya, maka sebenarnya itu akan melakukan proses INNER JOIN.
4. format perintah INNER JOIN adalah SELECT \* FROM nama_tabel_pertama INNER JOIN nama_tabel_kedua ON (nama_tabel_kedua.nama_kolom_penghubung = nama_tabel_pertama.nama_kolom_penghubung);
5. misalnya : SELECT \* FROM categories INNER JOIN products ON (Products.id_category = categories.id);
6. perintah diatas akan melakukan proses inner join antara tabel categories dan tabel products kemudian akan menampilkan data-data pada tabel categories dan tabel products yang saling berelasi

--LEFT JOIN--

1. LEFT JOIN merupakan mekanisme JOIN yang mirip dengan INNER JOIN, namun bedanya, pada LEFT JOIN semua data ditabel pertama yang tidak memiliki relasi di tabel kedua akan ikut di tampilkan juga
2. konsep dari LEFT JOIN adalah jika terdapat data di tabel pertama yang tidak memiliki relasi di tabel kedua, maka data tersebut akan ikut ditampilkan juga (sederhananya selain menampilkan semua data yang memiliki relasi, left join juga tetap menampilkan semua data di tabel pertama walaupun data tersebut tidak memiliki relasi di tabel kedua).
3. jika ada data ditabel pertama yang tidak memiliki relasi ditabel kedua, maka relasi di tabel kedua dari data tersebut akan diisi nilai null.
4. format perintah untuk LEFT JOIN adalah sebagai berikut : SELECT \* FROM nama_tabel_pertama LEFT JOIN nama_tabel_kedua ON (nama_tabel_kedua.nama_kolom_penghubung = nama_tabel_pertama.nama_kolom_penghubung);
5. misalnya : SELECT \* FROM categories LEFT JOIN products ON (products.id_category = categories.id);
6. perintah diatas akan melakukan proses left join antara tabel categories dan tabel products kemudian akan menampilkan data-data pada tabel categories dan tabel products yang saling berelasi dan juga menampilkan seluruh data categories yang tidak memiliki relasi di tabel products.

--RIGHT JOIN--

1. RIGHT JOIN merupakan mekanisme JOIN yang mirip dengan INNER JOIN, namun bedanya, pada RIGHT JOIN semua data ditabel kedua yang tidak memiliki relasi di tabel pertama akan ikut di tampilkan juga
2. konsep dari RIGHT JOIN adalah jika terdapat data di tabel kedua yang tidak memiliki relasi di tabel pertama, maka data tersebut akan ikut ditampilkan juga (sederhananya selain menampilkan data-data yang memiliki relasi, right join juga tetap akan menampilkan semua data di tabel kedua walaupun data tersebut tidak memiliki relasi di tabel pertama).
3. jika ada data ditabel kedua yang tidak memiliki relasi ditabel pertama, maka relasi di tabel pertama dari data tersebut akan diisi nilai null.
4. format perintah untuk RIGHT JOIN adalah sebagai berikut : SELECT \* FROM nama_tabel_pertama RIGHT JOIN nama_tabel_kedua ON (nama_tabel_kedua.nama_kolom_penghubung = nama_tabel_pertama.nama_kolom_penghubung);
5. misalnya : SELECT \* FROM categories RIGHT JOIN products ON (products.id_category = categories.id);
6. perintah diatas akan melakukan proses right join antara tabel categories dan tabel products kemudian akan menampilkan data-data pada tabel categories dan tabel products yang saling berelasi dan juga menampilkan seluruh data products yang tidak memiliki relasi di tabel categories.

--CROSS JOIN--

1. CROSS JOIN merupakan salah satu jenis JOIN yang sangat jarang sekali digunakan.
2. konsep dari CROSS JOIN adalah melakukan join menggunakan cara mengkalikan data di tabel pertama dengan data ditabel kedua
3. itu artinya, jika terdapat 5 data di tabel pertama dan 5 data di tabel kedua, maka akan menghasilkan 25 kombinasi data-data yang berbeda (5 X 5)
4. format perintah untuk CROSS JOIN adalah sebagai berikut : SELECT \* FROM nama_tabel_pertama CROSS JOIN nama_tabel_kedua; (untuk cross join, kita tidak perlu untuk memberi kolom penghubung antar tabel seperti join-join lain karena cross join tidak membutuhkan penghubung untuk melakukan proses join)
5. misalnya : SELECT \* FROM categories CROSS JOIN products;
6. perintah diatas akan melakukan proses cross join antara tabel categories dan tabel products kemudian akan menampilkan kombinasi data dari hasil perkalian data-data di tabel categories dengan data-data di tabel products
7. note : CROSS JOIN sangat jarang sekali digunakan.

--SUBQUERY--

1. di mysql, kita dapat melakukan query select di dalam query select (query bersarang)
2. fitur ini dinamakan subquery.
3. contohnya kita ingin mencari products yang harganya diatas harga rata-rata, itu artinya, kita akan melakukan SELECT dengan WHERE price > harga rata-ratanya, dimana harga rata-rata tersebut perlu kita hitung menggunakan query SELECT lainnya mengguanakan aggregate function
4. dengan kata lain contoh diatas, kita akan melakukan proses query sebanyak 2 kali didalam 1 perintah sql.
5. implementasi perintah sql untuk mengatasi kasus seperti diatas adalah sebagai berikut : SELECT \* FROM products WHERE price > (SELECT AVG(price) FROM products);
6. SELECT AVG(price) FROM products pada perintah diatas, dapat disebut subquery karena query select tersebut berapa di dalam query select lainnya.
7. selain menaruh subquery diwhere clause seperti contoh diatas, kita juga dapat menaruh subquery di FROM clause.
8. misalnya ada kasus dimana kita ingin mencari harga termahal pada tabel product, namun hanya untuk data-data products yang mempunyai relasi di tabel categories saja.
9. untuk mengatasi kasus diatas, kita dapat menjalankan perintah seperti berikut : SELECT MAX(cp.price) FROM (SELECT price FROM categories JOIN products ON (products.id_category = categories.id)) as cp;
10. note: saat kita ingin menempatkan subquery pada FROM clause maka kita wajib menambahkan alias setelah subquery.
11. penjelasan pada perintah diatas adalah kita melakukan JOIN antara tabel categories dengan tabel products didalam subquery. ini berfungsi untuk mendapatkan data-data products yang memiliki relasi dengan tabel categories. Setelah data-data tersebut didapatkan, maka query utama akan melakukan agregate function MAX untuk mencari price maksimal dari data-data yang sudah didapatkan oleh subquery.

--SET OPERATOR--

1. mysql mendukung operator set, dimana operator ini merupakan operasi gabungan antara hasil dari dua query SELECT.
2. terdapat banyak jenis operator set, diantaranya adalah UNION, UNION ALL, INTERSECT dan MINUS.

--UNION--

1. UNION merupakan operasi penggabungan dua buah query SELECT, dimana jika dari hasil penggabungan query select tersebut ternyata terdapat data yang duplikat, maka data duplikatnya tersebut akan dihapus dari hasil query.
2. contohnya kita melakukan union dengan melakukan select tabel customers dan tabel guestbook lalu ternyata di tabel customers dan guestbook terdapat data dengan email yang sama maka email yang sama tersebut hanya akan di tampilkan 1 kali saja. (konsepnya hampir mirip dengan select distict, namun bedanya jika distict itu hanya berlaku di 1 query select, sedangkan di union berlaku di kedua query select).
3. misalnya : SELECT DISTINCT email FROM customers UNION SELECT DISTINCT email FROM guestbooks;
4. saat kita menjalankan perintah diatas dan ternyata di tabel customers terdapat 1 buah data dengan email arif@gmail.com dan di tabel guestbook terdapat 3 data dengan email arif@gmail.com, maka yang akan ditampilkan hanya 1 data saja. sedangkan 3 data duplikat lainnya tidak akan di tampilkan.
5. note : jika kita menghilangkan distinct di query select pertama da kedua, maka hasilnya tidak akan berubah karena sebenarnya union ini memiliki fungsi yang mirip dengan distinct itu sendiri. Bedanya cuma union dapat menghingkan data duplikat di kedua query select sedangkan distinct hanya dapat menghilangkan data duplikat di satu query select saja. Jadi union ini dapat dikatakan versi expert dari distinct itu sendiri.

--UNION ALL--

1. UNION ALL adalah operasi yang mirip dengan UNION, namun data duplikat akan tetap ditampilkan di hasil querynya.
2. contohnya kita melakukan union dengan melakukan select tabel customers dan tabel guestbook lalu ternyata di tabel customers dan guestbook terdapat data dengan email yang sama maka semua email yang sama tersebut akan tetap ditampilkan.
3. misalnya : SELECT DISTINCT email FROM customers UNION ALL SELECT DISTINCT email FROM guestbooks;
4. saat kita menjalankan perintah diatas dan ternyata di tabel customers terdapat 1 buah data dengan email arif@gmail.com dan di tabel guestbook terdapat 3 data dengan email arif@gmail.com, maka yang akan ditampilkan hanya 2 data saja (1 data di tabel customers dan 1 data di tabel questbook). sedangkan 2 data duplikat di tabel guestbook tidak akan di tampilkan. Ini dikarenakan terdapat DISTINCT di kedua query SELECT. Jika kita menghilangkan kata DISTINCT di kedua query SELECT pada perintah diatas maka 2 data duplikat yang ada di tabel guestbook yang sebelumnya tidak ikut ditampilkan, akan ikut ditampilkan.

--INTERSECT--

1. INTERSECT adalah operasi penggabungan dua query select, dimana yang diambil hanya data yang terdapat pada hasil query pertam dan query kedua saja (sederhananya data yang ditampilkan hanya data yang memiliki kesamaan di tabel pertama dan tabel kedua).
2. jika data hanya ada di salah satu query select saja, maka data tersebut tidak akan ditampilkan.
3. walaupun yang ditampilkan hanyalah data yang memiliki kesamaan di kedua hasil query, namun data yang ditampilkan tidak dalam keadaan duplikat. Jadi jika di query pertama terdapat 2 data dengan email arif@gmail.com dan diquery kedua juga terdapat 3 data dengan email arif@gmail.com, maka data yang ditampilkan hanyalah 1 data yang ada di query pertama saja. (INTERSECT ini mirip dengan union namun bedanya INTERSECT ini juga ikut tidak menampilkan data yang tidak memiliki kesamaan di kedua query).
4. sayangnya, mysql tidak memilki operator INTERSECT ini, maka dari itu, untuk melakukan operasi INTERSECT, kita harus melakukannya secara manual menggunakan INNER JOIN atau SUBQUERY.
5. misalnya jika kita menggunakan SUBQUERY, maka perintahnya akan menjadi seperti ini : SELECT DISTINCT email FROM customers WHERE email IN (SELECT DISTINCT email FROM guestbooks);
6. sedangkan jika kita menggunakan INNER JOIN, maka perintahnya akan menjadi seperti ini : SELECT DISTINCT customers.email FROM customers INNER JOIN guestbooks ON (guestbooks.email = customers.email);

--MINUS--

1. minus merupakan operasi dimana query pertama akan dihilangkan oleh hasil query kedua jika pada hasil query pertama terdapat data yang sama dengan data yang ada di query kedua. (sederhananya operasi minus ini hanya akan menampilkan data-data query dari query pertama yang tidak memiliki kesamaan dengan query kedua).
2. note : hasil dari query kedua tidak akan ditampilkan karena query kedua hanya digunakan sebagai filter untuk hasil query pertama
3. namun sayangnya, di mysql juga tidak menyediakan operator MINUS ini, maka dari itu, untuk melakukan operasi MINUS, kita harus melakukannya secara manual menggunakan LEFT JOIN.
4. misalnya kita ada kasus dimana kita ingin menampilkan data customers yang emailnya tidak terdaftar di tabel guestbook, maka kita dapat menjalankan perintah : SELECT DISTINCT customers.email, guestbooks.email FROM customers LEFT JOIN guestbooks ON (guestbooks.email = customers.email) WHERE guestbooks.email IS NULL;
5. pada perintah diatas, kita melakukan left join antara tabel customers (tabel pertama) dengan tabel guestbooks (tabel kedua), kemudian kita melakukan filter dengan hanya menampilkan data-data yang email guestbooknya memiliki nilai null. (seperti yang dibahas pada materi left join sebelumnya, disitu sudah dijelaskan jika data pada tabel pertama memiliki relasi dengan nilai null maka data ditabel pertama tersebut tidak memiliki relasi ditabel kedua).

--TRANSACTION--

1. saat membuat aplikasi berbasis database, sering kali kita mendapatkan kasus dimana suatu aksi membutuhkan lebih dari satu perintah sql.
2. misalnya ketika customer menekan tombol pesan barang pada aplikasi ecommerce, maka sebenarnya disitu terdapat banyak sekali perintah sql yang di eksekusi diantaranya adalah : perintah insert data pesanan ke tabel order, perintag insert data detail pesanan ke tabel order detail, perintah update quantity dari data yang di pesan di tabel products, dan lain sebagainya.
3. artinya bisa saja di dalam sebuah aksi, kita akan melakukan beberapa perintah sekaligus.
4. saat menggunakan transaction, kemudian terjadi kesalahan di salah satu perintah, maka perintah-perintah sebelumnya akan dibatalkan, supaya data tetap konsisten.

--DATABASE TRANSACTION--

1. database transaction merupakan fitur di RDBMS dimana kita bisa memungkinkan beberapa perintah dianggap sebagai sebuah kesatuan perintah yang kita sebut transaction.
2. jadi jika terdapat satu saja perintah yang ada di dalam transaction tersebut gagal, maka secara otomatis perintah perintah yang sebelumnya sudah dieksekusi akan di batalkan kemudian perintah-perintah setelahnya juga tidak akan dieksekusi.
3. misalnya di dalam sebuah transaction terdapat 5 perintah perintah sql, kemudian saat perintah2 tersebut dieksekusi, ternyata terjadi error pada perintah ke 3, maka sql akan membatalkan perintah ke 1 dan ke 2 kemudian menghentikan eksekusi sql di perintah ke 3 atau dengan kata lain perintah ke 4 dan ke 5 tidak akan di eksekusi
4. sebuah transaction di anggap sukses jika semua perintah sql didalamnya tidak ada yang gagal (semua perintah sql sukses dijalankan).
5. note : kita dapat menjalankan berapapun perintah sql di dalam transaction tanpa batasan.

--TRANSACTION DI MYSQL--

1. terdapat 3 perintah transaction di mysql. diantaranya adalah :
2. START TRANSACTION yang berfungsi untuk memulai proses transaction. Saat perintah tersebut di eksekusi, maka perintah-perintah sql yang kita eksekusi setelah perintah tersebut akan di anggap transaction sampai kita menjalankan perintah COMMIT atau ROLLBACK.
3. COMMIT yang berfungsi untuk menyelesaikan proses transaction yang sudah dimulai kemudian menyimpan semua manipulasi data yang sudah kita lakukan di dalam transaction tersebut secara permanen ke dalam database mysql. Jadi jika kita melakukan proses INSERT, UPDATE dan DELETE di dalam transaction tersebut, maka data-data yang sudah di INSERT dan di UPDATE akan di simpan secara permanen ke dalam database kemudian data-data yang sudah di DELETE juga akan dihapus secara permanen dari database.
4. ROLLBACK yang berfungsi untuk membatalkan semua perintah sql yang sudah kita jalankan dari dieksekusinya perintah START TRANSACTION sampai dieksekusinya perintah ROLLBACK. sederhananya perintah ini akan membatalkan semua manipulasi data yang sudah kita eksekusi didalam transaction.
5. note : semua manipulasi data yang sudah kita lakukan di dalam transaction tidak dapat dilihat oleh user lain sebelum kita menjalankan perintah COMMIT.

--PERINTAH YANG TIDAK DAPAT DILAKUKAN MENGGUNAKAN TRANSACTION--

1. kita tidak dapat menggunakan transaction pada semua perintag DDL (data definition language) karena transaction hanya dikhususkan untuk perintah2 DML (data manipulation language) saja.

--LOCKING--

1. locking merupakan proses mengunci data di RDBMS.
2. proses mengunci data sangatlah penting untuk dilakukan. Salah satu alasannya adalah supaya data yang ada di dalam database benar-benar terjamin konsistensinya.
3. karena pada kenyataannya, aplikasi yang kita buat pasti akan digunakan oleh banyak pengguna. Dan pasti ada saat dimana banyak pengguna memodifikasi data yang sama di waktu yang sama pula. Jika kita tidak menggunakan locking, maka dapat dipastikan akan terjadi RACE CONDITION, yaitu proses balapan ketika memodifikasi data yang sama.
4. misalnya, terdapat 100 orang ingin membeli produk yang sama di waktu yang sama, akan tetapi, produk tersebut hanya berjumlah 10 unit, jika data tidak terjaga (tidak melakukan locking), maka bisa saja 100 orang tersebut mendapat produk tersebut, ini terjadi karena 100 orang tersebut melakukan proses update jumlah stok produk tersebut diwaktu yang sama, yang menimbulkan kesalahan dalam proses mengupdate jumlah stock produk tersebut.

--LOCKING RECORD--

1. saat kita melakukan proses TRANSACTION, kemudian kita melakukan proses update data, data yang kita update tersebut akan secara otomatis di LOCK.
2. hal ini membuat proses TRANSACTION sangat aman.
3. oleh karena itu, sangat disarankan untuk selalu menggunakan fitur TRANSACTION ketika ingin memanipulasi data didalam database. terutama ketika perintah manipulasinya lebih dari satu kali.
4. secara sederhana, cara kerja locking ini mirip seperti antrian eksekusi perintah sql dari setiap user. Jadi ketika kita sedang melakukan proses modifikasi suatu data, maka perintah eksekusi modifikasi data yang dilakukan pihak lain akan diminta menunggu sampai kita mengeksekusi perintah COMMIT ataupun ROLLBACK.
5. misalnya user a melakukan update jumlah stok dari produk dengan id 1 namun user a belum menjalankan perintah SUBMIT ataupun ROLLBACK, kemudian user b juga melakukan update jumlah stok di data yang sama, maka perintah sql dari user b akan dieksekusi setelah user a mengeksekusi perintah SUBMIT atau ROLLBACK.

--LOCKING RECORD MANUAL--

1. selain locking data secara otomatis menggunakan TRANSACTION, kita juga dapat melakukan locking data secara manual menggunakan perintah FOR UPDATE.
2. kadang saat kita membuat aplikasi, ada kalanya kita harus melakukan SELECT query terlebih dahulu sebelum melakukan proses UPDATE data.
3. misalnya kita melakukan select data produk dengan id 1 kemudian ada user lain merubah jumlah stok produk dengan id 1, jika kita tidak menggunakan locking, maka data yang kita dapatkan tadi sudah tidak konsisten karena jumlah stoknya sudah dirubah oleh user lain.
4. untuk menghindari masalah data tidak konsiten seperti contoh diatas, maka kita wajib melakukan locking record pada saat melakukan SELECT data.
5. untuk melakukan proses locking record secara manual, kita bisa tambahkan perintah FOR UPDATE di belakang query SELECT.
6. saat data yang kita select di lock, maka jika ada user lain ingin melakukan UPDATE, DELETE atau SELECT FOR UPDATE lagi, maka user lain tersebut akan diminta menunggu dulu sampai kita selesai melakukan COMMIT atau ROLLBACK.
7. note : walaupun ini adalah proses locking secara manual, kita tetap harus menjalankan perintah START TRANSACTION terlebih dahulu sebelum melakukan SELECT FOR UPDATE.

--DEADLOCK--

1. saat kita terlalu banyak melakukan proses locking pada sebuah database, maka kita akan menghadapi masalah yang bernama DEADLOCK.
2. DEADLOCK adalah situasi dimana ada 2 proses yang saling menunggu satu sama lain, namun data yang ditunggu dua-duanya di lock oleh proses lainnya. sehingga proses menunggunya ini tidak akan pernah selesai.
3. misalnya : user a melakukan SELECT FOR UPDATE untuk data 001, user b melakukan SELECT FOR UPDATE untuk data 001, user a melakukan SELECT FOR UPDATE untuk data 002, user a diminta menunggu karena data 002 sedang di lock oleh user b, user b melakukan SELECT FOR UPDATE untuk data 001, user b diminta menunggu karena data 001 sedang di lock oleh user a, akhirnya user a dan user b akan saling menunggu dan deadlock pun terjadi.

--LOCKING TABLE--

1. selain locking record, MYSQL juga mendukung proses locking terhadap sebuah tabel
2. berbeda dengan locking record yang melakukan locking terhadap data atau record tertentu didalam sebuah tabel, locking tabel akan melakukan locking pada seluruh data yang ada di dalam sebuah tabel.
3. jadi jika kita melakukan lock pada sebuah tabel, itu artinya seluruh data di dalam tabel tersebut akan di lock.
4. ada 2 jenis lock table yaitu READ dan WRITE
5. format perintah untuk melakukan lock table adalah sebagai berikut :
6. untuk jenis READ lock format perintahnya adalah LOCK TABLES nama_tabel_yang_ingin_dilock READ;
7. untuk jenis WRITE lock format perintahnya adalah LOCK TABLES nama_tabel_yang_ingin_dilock WRITE;
8. jika kita ingin melakukan unlock pada tabel yang sudah kita lock, kita dapat menjalankan perintah : UNLOCK TABLES;
9. proses LOCKING TABLE biasanya di gunakan ketika kita ingin melakukan generate data report dari suatu tabel tertentu.
10. note : kita tidak perlu menjalankan START TRANSACTION ataupun COMMIT untuk melakukan proses LOCKING TABLE

--PERBEDAAN READ LOCK DAN WRITE LOCK--

1. jika kita melakukan READ lock, maka kita dan user lain hanya dapat melakukan query SELECT saja dan tidak bisa melakukan query untuk modifikasi data seperti INSERT,UPDATE dan DELETE terhadap tabel yang sudah kita lock sampai kita menjalankan perintah UNLOCK TABLES;.
2. jika kita melakukakan WRITE lock, maka kita dapat melakukan query SELECT dan juga proses modifikasi data (INSERT, UPDATE, DELETE) pada tabel yang dilock, sedangkan user lain tidak bisa melakukan query SELECT maupun query untuk modifikasi data seperti INSERT,UPDATE dan DELETE terhadap tabel yang sudah kita lock sampai kita menjalankan perintah UNLOCK TABLES;.

--LOCKING INSTANCE--

1. salah satu fitu lock lainnya di mysql adalah lock instance
2. lock instance adalah perintah locking yang akan membuat perintah DDL (data definition language) akan dimintah menunggu sampai proses unlock instance dijalankan (ini hanya berlaku untuk user lain saja jadi kita masih dapat menjalankan perintah DDL meskipun kita sudah menjalankan perintah lock instance)
3. locking instance biasanya dilakukan ketika kita ingin melakukan proses backup data yang ada didalam sebuah database, supaya tidak terjadi perubahan terhadap struktur tabel yang ada didalam database tersebut.
4. setelah proses backup selesai, baru kita unlock instance nya
5. untuk melakukan locking instance, kita dapat menggunakan perintah : LOCK INSTANCE FOR BACKUP;
6. dan untuk melakukan unlock instance, kita dapat menggunakan perintah : UNLOCK INSTANCE;

--USER MANAGEMENT--

1. secara default saat kita menginstall mysql, mysql akan secara otomatis membuat sebuah user baru yang bernama root. user root ini akan bertindak sebagai super administrator (user ini dapat melakukan proses ddl dan dml di database manapun).
2. namun best practice nya, saat kita menjalankan mysql dengan aplikasi lain yang kita buat, sangat disarankan tidak menggunakan user root ini. Karena jika kita menggunakan user root, maka aplikasi tersebut nantinya akan dapat mengakses semua database yang ada di dalam aplikasi mysql.
3. lebih baik kita membuat user khusus untuk tiap aplikasi yang kita buat. Bahkan kita dapat membatasi hak akses dari user tersebut. Seperto hanya bisa melakukan query SELECT saja dan tidak boleh melakukan query INSERT, UPDATE atau DELETE.

--DAFTAR HAK AKSES USER DI MYSQL--

1. ada banyak sekali hak akses user yang ada di mysql.
2. kita dapat melihatnya pada daftar tabel yang terdapat pada link berikut : dev.mysql.com/doc/refman/8.0/en/grant.html

--MEMBUAT USER BARU DI MYSQL--

1. untuk membuat user baru di mysql, kita dapat menggunakan perintah dengan format sebagai berikut : CREATE USER 'nama_user'@'lokasi_usernya_boleh_mengakses_mysql';
2. misalnya : CREATE USER 'arif'@'localhost'; maka user arif ini hanya dapat mengakses mysql dari notebook atau pc tempat menginstall aplikasi mysql tersebut saja.
3. misalnya : CREATE USER 'ahmad'@'%'; maka user ahmad ini dapat mengakses mysql dari ip address apapun (cara ini sangat tidak disarankan karena orang lain yang mengetahui user tersebut dapat melakukan hacking pada mysql kita).

--MENGHAPUS USER--

1. untuk menghapus user yang sudah di buat, kita dapat menggunakan perintah : DROP USER 'nama_user'@'lokasi_usernya_boleh_mengakses_mysql';
2. misalnya : DROP USER 'arif'@'localhost'

--MENAMBAH HAK AKSES KE USER--

1. untuk menambah hak akses ke dalam sebuah user, kita dapat menggunakan perintah dengan format: GRANT hak_akses1,hak_akses2,hak_akses3,dan_seterusnya ON nama_database.\* TO 'nama_user'@'lokasi_usernya_boleh_mengakses_mysql';
2. misalnya : GRANT SELECT,INSERT,UPDATE,DELETE ON belajar_mysql.\* TO 'arif'@'localhost';
3. perintah diatas akan menambahkan hak akses SELECT, INSERT,UPDATE dan DELETE kepada user arif.

--MELIHAT LIST HAK AKSES YANG DIMILIKI SUATU USER--

1. untuk melihat semu hak akses yang dimiliki oleh suatu user, kita dapat menjalankan perintah dengan format : SHOW GRANTS FOR 'nama_user'@'lokasi_usernya_boleh_mengakses_mysql';
2. misalnya : SHOW GRANTS FOR 'arif'@'localhost';
3. perintah diatas akan menampilkan semua hak akses yang dimiliki oleh user arif.

--MENGHAPUS HAK AKSES DARI SUATU USER--

1. untuk menghapus hak akses yang sudah terlanjur ditambahkan ke dalam suatu user, kita dapat menjalankan perintah dengan format : REVOKE hak_akses1,hak_akses2,hak_akses3, dan_seterusnya ON nama_database.\* FROM 'nama_user'@'lokasi_usernya_boleh_mengakses_mysql';
2. misalnya : REVOKE UPDATE, DELETE ON belajar_mysql.\* FROM 'arif'@'localhost';
3. perintah diatas akan menghapus hak akses UPDATE dan DELETE pada user arif. Jadi user arif tidak lagi dapat melakukan query update dan delete data-data yang ada di dalam database belajar_mysql.

--MENGUBAH ATAU MENAMBAH PASSWORD PADA SUATU USER--

1. untuk menambah atau mengubah password pada suatu user, kita dapat menjalankan perintah dengan format : SET PASSWORD FOR 'nama_user'@'lokasi_usernya_boleh_mengakses_mysql' = 'password_barunya';
2. misalnya : SET PASSWORD FOR 'arif'@'localhost' = 'rahasia';
3. dengan ini maka user arif akan memiliki password 'rahasia'

--BACKUP DATABASE--

1. saat membuat aplikasi menggunakan database mysql, ada baiknya kita selalu melakukan backup data secara reguler supaya jika terjadi masalah pada aplikasi mysqlnya maka data-data yang ada didalam database akan tetap aman
2. untuk malakukan backup pada sebuah database, kita tidak akan menggunakan peritah sql, malainkan mysql sudah menyediakan aplikasi khusus untuk melakukan backup database, nama aplikasinya adalah mysqldump
3. note : kita tidak perlu melakukan install mysqldump secara manual untuk menggunakan aplikasi mysqldump karena aplikasi tersebut sudah ikut terinstall bersamaan dengan kita menginstall aplikasi mysql.
4. penjelasan lebih lengkapnya dapat dilihat pada link : dev.mysql.com/doc/refman/8.0/en/mysqldump.html
5. format perintah backup database menggunakan mysqldump adalah sebagai berikut : mysqldump nama_database_yang_ingin_dibackup --user nama_user --password --result-file=nama_direktori_tempat_hasil_backup_akan_disimpan
6. misalnya : mysqldump belajar_mysql --user root --password --result-file=/home/arifin/project/mysql/belajar_mysql.sql
7. perintah diatas akan melakukan backup pada database belajar_mysql ke dalam forder /home/arifin/project/mysql dengan nama file belajar_mysql.sql
8. untuk menjalankan perintah backup database ini, kita harus berada diterminal biasa (tidak berada di dalam mysql -uroot -p)

--RESTORE DATABASE--

1. selain melakukan backup database, kita juga dapat melajukan proses restore data dari file hasil backup ke dalam aplikasi mysql.
2. untuk melakukan restore database, kita dapat menggunakan aplikasi client atau menggunakan perintah SOURCE di mysql.

--RESTORE DATABASE MENGGUNAKAN APLIKASI CLIENT--

1. sebelum melakukan restore database, hal pertama yang harus kita lakukan adalah membuat database baru serlebih dahulu, database ini akan berfungsi sebagai wadah dari database yang akan kita restore
2. setelah membuat database baru, barulah kita dapat melakukan restore database menggunakan perintah dengan format : mysql --user=nama_user --password nama_database_yang_baru_dibuat < nama_direktori_tempat_kita_menyimpan_hasil_backup_database/nama_file_hasil_backupnya.sql
3. misalnya :mysql --user=root --password belajar_mysql_import < /home/arifin/project/mysql/belajar_mysql.sql
4. untuk menjalankan perintah restore database ini, kita harus berada diterminal biasa (tidak berada di dalam mysql -uroot -p)

--RESTORE DATABASE MENGGUNAKAN SOURCE--

1. sebelum melakukan restore database, hal pertama yang harus kita lakukan adalah membuat database baru serlebih dahulu, database ini akan berfungsi sebagai wadah dari database yang akan kita restore
2. kemudian kita menjalankan perintah use database_yang_baru_dibuat
3. lalu menjalankan perintah RESTORE DATABASE dengan format : SOURCE nama_direktori_tempat_kita_menyimpan_hasil_backup_database/nama_file_hasil_backupnya.sql
4. misalnya : SOURCE /home/arifin/project/mysql/belajar_mysql.sql
5. untuk menjalankan perintah restore database ini, mula-mula kita harus berada didalam mysql -uroot -p
