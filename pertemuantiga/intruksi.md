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
