# pratkum3-bhs-pemograma
class Barang:
    def __init__(self, nama, harga, jumlah=1):
        self.nama = nama
        self.harga = harga
        self.jumlah = jumlah

    def total_harga(self):
        return self.harga * self.jumlah


class KeranjangBelanjaanda:
    def __init__(self):
        self.barang = []

    def tambah_barang(self, barang):
        self.barang.append(barang)

    def tampilkan_barang(self):
        if not self.barang:
            print("Keranjang kosong.")
            return
        print("Daftar Barang di Keranjang Anda :")
        for i, item in enumerate(self.barang, start=1):
            print(f"{i}. {item.nama} - {item.jumlah} x {item.harga} = {item.total_harga()} ")

    def hitung_total(self):
        return sum(item.total_harga() for item in self.barang)

    def cetak_struk(self):
        self.tampilkan_barang()
        total = self.hitung_total()
        print("\nTotal Harga belanja anda: Rp", total)
        print("Terima kasih sudah berbelanja!")


# Contoh penggunaan
# Menambahkan barang ke keranjang Anda
keranjang = KeranjangBelanjaanda()
keranjang.tambah_barang(Barang("minyak 2 liter",         20000, 2))
keranjang.tambah_barang(Barang("beras 2 kg",              34000, ))
keranjang.tambah_barang(Barang("tepung 2 kg",             15000, ))
keranjang.tambah_barang(Barang("sabun ",                 10000, 3))
keranjang.tambah_barang(Barang("pewangi soklin",         44000, 1))
keranjang.tambah_barang(Barang("Shampoo",                15000, 1))
keranjang.tambah_barang(Barang("Pasta Gigi",              7000, 3))

# Menampilkan daftar barang
keranjang.tampilkan_barang()

# Menghitung total harga
print("\nTotal Harga: Rp", keranjang.hitung_total())

# Mencetak struk
print("\nStruk Belanja:")
keranjang.cetak_struk()
