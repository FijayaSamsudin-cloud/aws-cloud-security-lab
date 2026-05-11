# aws-cloud-security-lab
Repository ini berisi jurnal belajar, konfigurasi infrastruktur, dan implementasi keamanan di AWS.


# Cloud Security Learning Lab

Halo! Saya **Fijaya Samsudin**. Repository ini adalah bukti perjalanan saya mendalami:
* **AWS Cloud Infrastructure**
* **Cloud Security Engineering**
* **DevOps & Automation**

## Progress Saat Ini:
- [x] Setup GitHub & Git Local
- [x] Configure AWS VPC (Completed)
- [x] Security Group Hardening (Completed)
- [x] Deploy EC2 Instance (Completed)
- [x] Advanced System Hardening & User Management (Completed)
- [x] System Auditing & Legal Compliance (Completed)
- [ ] Web Server Deployment & Nginx Hardening (Next Step)

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

![VPC Architecture Success](./img/vpc-success.png)


### 09 Mei 2026: Security Hardening & Firewall Infrastructure
- [x] **Git Identity Fix**: Berhasil mengonfigurasi identitas Git global agar kontribusi tercatat dengan benar.
- [x] **Security Group (Stateful Firewall)**: Membuat `SG-Web-Server-Fijaya` di dalam `proyek-vpc`.
- [x] **Inbound Rules Hardening**: 
    - Membatasi akses port 22 (SSH) hanya dari IP publik pribadi (Admin Only).
    - Membuka port 80 (HTTP) untuk lalu lintas web publik.
- [x] **Outbound Rules Verification**: Memastikan server memiliki akses keluar penuh (default) untuk update sistem.

![Security Group Config](./img/security-group-web-config.png)


### 10 Mei 2026: Compute Provisioning & System Hardening
- [x] **EC2 Instance Launch**: Berhasil mendeploy server menggunakan Amazon Linux 2023 (t3.micro).
- [x] **System Identity**: Mengubah hostname menjadi `web-server-lab`.
- [x] **Timezone Synchronization**: Mengatur timezone ke `Asia/Jakarta` (WIB) untuk akurasi log.
- [x] **Security Update**: Menjalankan `dnf update` untuk patch keamanan terbaru.

![EC2 Running Status](./img/ec2-status-running.png)


### 11 Mei 2026: Advanced System Hardening, User Management & Monitoring
- [x] **User Provisioning & Privilege Management**: Membuat user personal `fijaya` dan mengonfigurasi izin `sudo` via grup `wheel` untuk menggantikan penggunaan `ec2-user` (Standard Operational Procedure).
- [x] **SSH Key Migration & Permission Hardening**: Berhasil memindahkan akses `.pem` ke user personal serta mengatur hak akses folder `.ssh` (700) dan `authorized_keys` (600) guna mencegah *unauthorized access*.
- [x] **System Auditing (CCTV Digital)**: Mengimplementasikan `auditd` untuk memantau aktivitas kritis seperti perubahan konfigurasi SSH, file password, dan setiap eksekusi perintah administratif.
- [x] **Legal Compliance Banner**: Mengonfigurasi `/etc/issue.net` dan SSH Banner untuk menampilkan peringatan hukum "Authorized Use Only" sebagai standar kepatuhan industri.
- [x] **Audit Verification**: Melakukan pengujian log menggunakan `aureport` dan `ausearch` untuk memastikan seluruh jejak digital terekam dengan benar berdasarkan AUID (Audit User ID).

![User Login Success](./img/user-fijaya-login.png)
![SSH Warning Banner](./img/ssh-banner-warning.png)
![Audit Log Success](./img/audit-log-check.png)