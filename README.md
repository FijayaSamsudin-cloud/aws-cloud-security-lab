# aws-cloud-security-lab
Repository ini berisi jurnal belajar, konfigurasi infrastruktur, dan implementasi keamanan di AWS.


# Cloud Security Learning Lab

Halo! Saya **Fijaya Samsudin**. Repository ini adalah bukti perjalanan saya mendalami:
* **AWS Cloud Infrastructure**
* **Cloud Security Engineering**
* **DevOps & Automation**

## Progress Saat Ini:
- [x] Setup GitHub & Git Local
- [x] Configure AWS VPC (Next Step)


### 08 Mei 2026: Identity and Access Management (IAM) & Security
- [x] Mengecek Billing Dashboard (Memastikan Free Tier aktif).
- [x] Mendapatkan AWS Credits sebesar US$119.97 (Valid until Nov 2026).
- [x] Membuat IAM User Admin untuk menghindari penggunaan Root Account (Best Practice).
- [x] Berhasil login menggunakan user `fijaya-admin` dengan akses Administrator.
- [x] Mengaktifkan MFA (Multi-Factor Authentication) untuk keamanan ekstra pada akun Admin.
### 08 Mei 2026: Networking (VPC) - COMPLETED
- [x] **VPC Deployment**: Berhasil membangun VPC khusus (`proyek-vpc`) menggunakan wizard "VPC and more" untuk memastikan konfigurasi yang rapi.
- [x] **Multi-AZ Architecture**: Menggunakan 2 Availability Zones untuk standar High Availability (Ketersediaan Tinggi).
- [x] **Tiered Subnets**: 
    - 2 Public Subnets (untuk resource yang butuh akses internet langsung).
    - 2 Private Subnets (untuk resource internal/database agar lebih aman).
- [x] **Cost Optimization**: Memilih untuk tidak menggunakan NAT Gateway guna menghemat biaya operasional selama fase belajar.
- [x] **Security Enhancement**: Mengaktifkan **S3 Gateway Endpoint**, memungkinkan akses ke layanan S3 secara privat tanpa melalui internet publik.


### 09 Mei 2026: Security Groups (Firewall)
- [x] Membuat Security Group `SG-Web-Server-Fijaya` di dalam VPC Proyek.
- [x] Konfigurasi Inbound: Membatasi SSH hanya untuk IP pribadi (Security Hardening).
- [x] Konfigurasi Inbound: Membuka akses HTTP untuk publik.
- [x] Memahami filosofi Stateful Firewall pada AWS Security Groups.