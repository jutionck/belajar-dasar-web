### Membuat Website Wisata

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
