# UTS_PBO2_23552011133
1. Inheritance 
- Civitas 
Inheritance memungkinkan kita untuk membuat suatu hierarki kelas sehingga kode yang sifatnya umum nggak perlu ditulis berulang-ulang. Misalnya, kita punya abstract class Sivitas sebagai fondasi, lalu kelas Civitas yang punya atribut seperti universitas dan fakultas, dan akhirnya kelas Mahasiswa yang mewarisi dari Civitas dan nambah atribut khusus seperti nama dan NIM. Jadi, kalau ada perubahan di atribut dasar, tinggal ubah di satu tempat aja, bikin kodenya lebih gampang di-maintain dan strukturnya jadi jelas, mirip kayak di dunia nyata.
Kode dalam Program :

public class Civitas extends Sivitas {
    private String universitas;
    private String fakultas;
    // Getter dan setter ...
}

public class Mahasiswa extends Civitas {
    private String nama;
    private String nim;
    // Getter dan setter ...
}

2. Polymorphism

Polymorphism itu bikin program kita jadi fleksibel dalam hal eksekusi fungsi, karena kita bisa bikin method dengan nama yang sama tapi isi yang berbeda. Di sini, kita punya abstract class Pembayaran dengan method hitungTagihan(int semester), dan kelas PembayaranAdministrasi yang mengimplementasikan method tersebut dengan rumus tertentu (fee per semester). Jadi, kalau nanti ada perhitungan tagihan lain, tinggal bikin subclass baru yang override method-nya tanpa harus mengubah cara pemanggilan, memudahkan perubahan di masa depan.

Kode dalam Program :
public abstract class Pembayaran {
    public abstract double hitungTagihan(int semester);
}

public class PembayaranAdministrasi extends Pembayaran {
    private final double feePerSemester = 300000; // Contoh biaya per semester

    @Override
    public double hitungTagihan(int semester) {
        return semester * feePerSemester;
    }
}

3. Encapsulation

Encapsulation memastikan data penting dalam kelas terlindungi dan nggak bisa sembarangan diubah dari luar. Pada kelas Mahasiswa, misalnya, atribut seperti nama dan NIM di-declare sebagai private sehingga akses dan modifikasinya harus dilakukan lewat getter dan setter. Hal ini bikin data tetap terjaga konsistensinya dan memberikan kontrol penuh terhadap bagaimana data itu dipakai, sehingga lebih aman dan mudah untuk debugging atau pengembangan lebih lanjut.

Kode dalam Program :
public class Mahasiswa extends Civitas {
    private String nama;
    private String nim;

    // Konstruktor, getter, dan setter
}

4. Abstract

Abstract class dipake sebagai cetak biru (blueprint) untuk kelas-kelas lain yang harus punya struktur atau perilaku tertentu. Dengan mendeklarasikan Sivitas sebagai abstract class, kita nge-tekenin bahwa kelas ini nggak boleh di-instantiate langsung, tapi harus diturunkan ke kelas lain seperti Civitas dan Mahasiswa yang kemudian bisa menambahkan detail spesifik mereka. Jadi, semua entitas yang tergolong dalam sivitas mengikuti standar dasar yang sama, membuat kode kita jadi konsisten dan terstruktur.

Kode dalam Program :
public abstract class Sivitas {

}
