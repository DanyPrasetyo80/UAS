// Deklarasi dan Inisialisasi

import java.util.Scanner;
- Kode ini mengimpor Scanner, yang digunakan untuk membaca input dari pengguna.


public class Cafebromo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
- Kode di atas mendefinisikan kelas Cafebromo dan metode main(), yang merupakan titik awal eksekusi program. Scanner dibuat untuk menerima input dari pengguna.

//Deklarasi Array untuk Menyimpan Pesanan
String[] orders = new String[100];
int[] prices = new int[100];
int[] quantities = new int[100]; 
int orderCount = 0;
orders → Menyimpan nama menu yang dipesan
prices → Menyimpan harga masing-masing menu yang dipesan
quantities → Menyimpan jumlah dari menu yang dipesan
orderCount → Menghitung jumlah pesanan yang telah dibuat
// Menampilkan Menu Kafe

System.out.println("===== Selamat Datang di Kafe Bromo Hills =====");
System.out.println("\n==== Daftar Menu ====");
System.out.println("1. Espresso    - Rp20000");
System.out.println("2. Amricano    - Rp25000");
System.out.println("3. Bromo Coffe - Rp30000");
System.out.println("4. Kentang Goreng - Rp30000");
System.out.println("5. Roti Bakar     - Rp20000");
System.out.println("6. Cappuccino     - Rp20000");
System.out.println("7. Creame Brule   - Rp25000");
- Bagian ini mencetak daftar menu beserta harganya.

//Menampilkan Menu Opsi untuk Pengguna

while (true) {
    System.out.println("\nPilih opsi berikut:");
    System.out.println("1. Tambah Pesanan");
    System.out.println("2. Lihat Daftar Pesanan");
    System.out.println("3. Hitung Total Biaya");
    System.out.println("4. Lakukan Pembayaran");
    System.out.println("5. Selesai");
    System.out.print("Masukkan pilihan Anda: ");
    int choice = scanner.nextInt();
Perulangan while (true) → Program akan terus berjalan sampai pengguna memilih opsi 5 (Selesai).
choice = scanner.nextInt(); → Membaca pilihan pengguna untuk menentukan tindakan selanjutnya.
// Menangani Pilihan Pengguna
- (a) Menambahkan Pesanan

if (choice == 1) {
    System.out.print("Masukkan nomor menu yang ingin dipesan: ");
    int menuNumber = scanner.nextInt();
    System.out.print("Masukkan jumlah pesanan: ");
    int quantity = scanner.nextInt();
//Meminta pengguna memasukkan nomor menu dan jumlah pesanan.

String orderName = "";
int price = 0;
switch (menuNumber) {
    case 1:
        orderName = "Espresso";
        price = 20000;
        break;
    case 2:
        orderName = "Americano";
        price = 25000;
        break;
    case 3:
        orderName = "Bromo Coffe";
        price = 30000;
        break;
    case 4:
        orderName = "Kentang Goreng";
        price = 30000;
        break;
    case 5:
        orderName = "Roti Bakar";
        price = 20000;
        break;
    case 6:
        orderName = "Cappuccino";
        price = 30000;
        break;
    case 7:
        orderName = "Cream brule";
        price = 25000;
        break;
    default:
        System.out.println("Menu tidak valid. Silakan coba lagi.");
        continue;
}
//Menggunakan switch-case untuk menentukan nama menu dan harga berdasarkan nomor menu yang dipilih.
//Jika nomor menu tidak valid, program akan meminta input ulang.

orders[orderCount] = orderName;
prices[orderCount] = price;
quantities[orderCount] = quantity;
orderCount++;
System.out.println(orderName + " berhasil ditambahkan ke pesanan.");
//Menyimpan data pesanan ke dalam array dan menambahkan jumlah pesanan (orderCount).
- (b) Melihat Daftar Pesanan

} else if (choice == 2) {
    System.out.println("\n=== Daftar Pesanan ===");
    int totalCost = 0;
    for (int i = 0; i < orderCount; i++) {
        int subtotal = prices[i] * quantities[i];
        System.out.println(orders[i] + " x" + quantities[i] + " - Rp" + subtotal);
        totalCost += subtotal;
    }
    System.out.println("Total Biaya: Rp" + totalCost);
}
//Menampilkan semua pesanan yang telah ditambahkan beserta total biaya.
- (c) Menghitung Total Biaya

} else if (choice == 3) {
    int totalCost = 0;
    for (int i = 0; i < orderCount; i++) {
        totalCost += prices[i] * quantities[i];
    }
    System.out.println("\nTotal Biaya dari Semua Pesanan: Rp" + totalCost);
}
//Menghitung dan menampilkan total harga semua pesanan.
- (d) Melakukan Pembayaran

} else if (choice == 4) {
    int totalCost = 0;
    for (int i = 0; i < orderCount; i++) {
        totalCost += prices[i] * quantities[i];
    }
    System.out.println("\n=== Pembayaran ===");
    System.out.println("Total Biaya: Rp" + totalCost);
    System.out.print("Masukkan jumlah uang yang dibayarkan: ");
    int payment = scanner.nextInt();
//Menghitung total biaya dan meminta pengguna memasukkan uang pembayaran.

while (payment < totalCost) {
    System.out.println("Uang tidak mencukupi. Masukkan jumlah yang sesuai.");
    System.out.print("Masukkan jumlah uang yang dibayarkan: ");
    payment = scanner.nextInt();
}
//Jika uang kurang, pengguna diminta memasukkan ulang jumlah yang benar.


int change = payment - totalCost;
System.out.println("Pembayaran berhasil. Kembalian Anda: Rp" + change);
System.out.println("Terima kasih telah memesan. Sampai jumpa!");
break;
Menghitung kembalian dan mengakhiri program setelah pembayaran berhasil.
- (e) Keluar dari Program

} else if (choice == 5) {
    System.out.println("Terima kasih telah memesan. Sampai jumpa!");
    break;
} else {
    System.out.println("Pilihan tidak valid. Silakan coba lagi.");
}
//Jika pengguna memilih opsi 5 (Selesai), program akan berhenti.