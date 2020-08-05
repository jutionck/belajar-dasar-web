### Membuat Website Wisata

Alur :

<pre>
1. Buat Database
2. Membuat koneksi
3. Buat Service (CRUD - Create, Read, Update, Delete)
4. UI
5. Sistem Authentication
6. Testing
7. Production
</pre>

Membuat Database

<pre>
phpmyadmin
</pre>

Membuat Koneksi

<pre>
&lt;?php
$host = "host_server";
$user = "username_server";
$password = "password_server";
$database = "nama_database";

$conn = mysqli_connect($host, $user, $password, $database);

//cek koneksi berhasil atau tidak
if($conn) {
    echo "Koneksi berhasil";
} else {
    echo "Koneksi gagal!!";
}
</pre>

Memanggil Data dari Database dan Ditampilkan di Web

<pre>
&lt;?php
include "config/koneksi.php";

//ini coding selectData
$sql = mysqli_query($conn, "SELECT * FROM tb_lokasi");
$result = mysqli_fetch_assoc($sql)

//menampilkan
echo $result["idlokasi"];

</pre>

Tipe fetching data

<pre>
1. Memakai Fetch Row:
$sql = mysqli_query($conn, "SELECT * FROM tb_lokasi");
$result = mysqli_fetch_row($sql);
$result[0];

2. Memakai Fetch Assoc:
$sql = mysqli_query($conn, "SELECT * FROM tb_lokasi");
$result = mysqli_fetch_assoc($sql);
$result["idlokasi"];

3. Memakai Fetch Array:
$sql = mysqli_query($conn, "SELECT * FROM tb_lokasi");
$result = mysqli_fetch_array($sql);
$result["idlokasi"]; 
$result[0];

4. Memakai Fetch Object:
$sql = mysqli_query($conn, "SELECT * FROM tb_lokasi");
$result = mysqli_fetch_object($sql);
$result->idlokasi;
</pre>

Keterangan: <br>
<code>include</code> dan <code>require</code> : Perintah ini digunakan untuk memanggil file lain kedalam file

<code>mysqli_query</code> : Perintah ini digunakan untuk mengirimkan perintah SQL ke server MySQL untuk melakukan aktivitas CRUD yaitu meliputi CREATE (menambahkan data dengan perintah SQL INSERT), READ (membaca data dengan perintah SQL SELECT), UPDATE(mengubah data dengan perintah SQL UPDATE), DELETE (menghapus data dengan perintah SQL DELETE).

<code>mysqli_fetch...</code> : Perintah ini digunakan untuk mengambil baris hasil query bisa sebagai (array index, array asosiatif, maupun object)

Perulangan:

<pre>
&lt;?php
$sql = mysqli_query($conn, "SELECT * FROM tb_lokasi");
//buat perulangan disini
while($row = mysqli_fetch_assoc(sql)) : ?&gt;
    /* kode html disini */
&lt?php endwhile ?&gt;
</pre>
