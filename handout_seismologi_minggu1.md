# Handout Kuliah: Seismologi Kuantitatif (S2 Geofisika)
## Minggu 1: Dasar Elastodinamika dan Teorema Representasi

Handout ini disusun sebagai panduan akademis tingkat pascasarjana untuk memahami dasar-dasar mekanika kontinum, hubungan konstitutif, teorema resiprositas, fungsi Green, hingga teorema representasi elastodinamika yang menjadi fondasi utama dalam seismologi kuantitatif.

---

## 1. FONDASI FORMULASI ELASTODINAMIKA

### 1.1 Deskripsi Lagrangian vs. Eulerian dalam Seismologi
Dalam mekanika kontinum, terdapat dua cara utama untuk mendeskripsikan medan deformasi:
1. **Deskripsi Lagrangian (Material)**: Mengikuti pergerakan partikel individual seiring berjalannya waktu. Posisi partikel diidentifikasi menggunakan koordinat referensi awal $\mathbf{x}$ pada waktu $t = 0$. Perpindahan partikel dinyatakan sebagai $\mathbf{u}(\mathbf{x}, t)$.
2. **Deskripsi Eulerian (Spasial)**: Mengamati perubahan properti fisik pada titik koordinat ruang tetap $\mathbf{r}$ seiring waktu.

> **Penting untuk Seismologi**: Seismometer yang tertanam di stasiun perekam bergerak bersama dengan medium batuan tempat ia berdiri. Oleh karena itu, data seismogram yang direkam adalah representsi langsung dari gerakan **Lagrangian**. Karena amplitudo gelombang seismik umumnya sangat kecil dibandingkan dimensi medium bumi, perbedaan koordinat antara kondisi referensi dan terdeformasi dapat diabaikan (asumsi deformasi infinitesimal).

### 1.2 Tensor Regangan Infinitesimal
Ketika medium kontinu mengalami deformasi, jarak antar-partikel di dalamnya berubah. Misalkan dua partikel tetangga yang awalnya berjarak infinitesimal $\delta\mathbf{x}$ mengalami perpindahan masing-masing sebesar $\mathbf{u}(\mathbf{x}, t)$ dan $\mathbf{u}(\mathbf{x} + \delta\mathbf{x}, t)$. Perubahan perpindahan relatif $\delta u_i$ di antara kedua partikel tersebut dapat didekati dengan ekspansi Taylor orde pertama:

$$
\delta u_i = \frac{\partial u_i}{\partial x_j} \delta x_j = u_{i,j} \delta x_j
$$

Di sini, $u_{i,j}$ adalah **tensor gradien perpindahan** orde dua. Tensor ini dapat didekomposisi secara matematis menjadi bagian simetris dan anti-simetris:

$$
u_{i,j} = \frac{1}{2}(u_{i,j} + u_{j,i}) + \frac{1}{2}(u_{i,j} - u_{j,i})
$$

Sehingga perpindahan relatif dapat ditulis sebagai:

$$
\delta u_i = e_{ij} \delta x_j + \omega_{ij} \delta x_j
$$

Di mana:
- **$e_{ij}$ adalah Tensor Regangan Infinitesimal (Simetris)**:
  $$
  e_{ij} = \frac{1}{2}(u_{i,j} + u_{j,i}) = \frac{1}{2}\left(\frac{\partial u_i}{\partial x_j} + \frac{\partial u_j}{\partial x_i}\right)
  $$
  Tensor ini merepresentasikan deformasi elastis murni (perubahan panjang dan sudut). Karena simetris ($e_{ij} = e_{ji}$), ia memiliki **6 komponen independen**.
- **$\omega_{ij}$ adalah Tensor Rotasi Infinitesimal (Anti-Simetris)**:
  $$
  \omega_{ij} = \frac{1}{2}(u_{i,j} - u_{j,i})
  $$
  Komponen ini merepresentasikan rotasi benda tegar infinitesimal lokasl, yang dapat juga dinyatakan sebagai produk silang:
  $$
  \omega_{ij}\delta x_j = \frac{1}{2}(\nabla \times \mathbf{u} \times \delta\mathbf{x})_i
  $$
  Rotasi ini tidak mengubah jarak antar-partikel, sehingga tidak menimbulkan tegangan elastis.

### 1.3 Konsep Traksi dan Tensor Tegangan Cauchy
Gaya-gaya yang bekerja di dalam medium elastis diwakili oleh vektor **traksi** $\mathbf{T}(\mathbf{n})$, yang didefinisikan sebagai batas gaya kontak $\Delta\mathbf{F}$ per satuan luas $\Delta A$ pada permukaan dengan vektor normal satuan $\mathbf{n}$:

$$
\mathbf{T}(\mathbf{n}) = \lim_{\Delta A \to 0} \frac{\Delta\mathbf{F}}{\Delta A}
$$

Hubungan antara traksi $\mathbf{T}$ pada bidang dengan orientasi sembarang $\mathbf{n}$ dan keadaan tegangan di dalam medium dijelaskan melalui **Hukum Kesetimbangan Momentum pada Tetrahedron Infinitesimal** (Tetrahedron Cauchy). Dengan menyeimbangkan gaya-gaya pada elemen volume berbentuk tetrahedron, diperoleh hubungan linier:

$$
T_i(\mathbf{n}) = \tau_{ji} n_j
$$

Di mana $\tau_{ji}$ adalah **Tensor Tegangan Cauchy** berorde dua.

### 1.4 Penurunan Persamaan Gerak Elastodinamika
Untuk elemen volume $V$ sebarang yang dibatasi oleh permukaan $S$ dengan densitas medium $\rho$, hukum kesetimbangan momentum linier (Hukum II Newton) menyatakan bahwa laju perubahan momentum linier sama dengan total gaya volume $\mathbf{f}$ (gaya per satuan volume) dan gaya permukaan (traksi):

$$
\iiint_V \rho \ddot{u}_i \, dV = \iiint_V f_i \, dV + \iint_S T_i(\mathbf{n}) \, dS
$$

Substitusi hubungan traksi $T_i = \tau_{ji} n_j$ ke dalam integral permukaan:

$$
\iiint_V \rho \ddot{u}_i \, dV = \iiint_V f_i \, dV + \iint_S \tau_{ji} n_j \, dS
$$

Dengan menerapkan **Teorema Divergensi Gauss** pada integral permukaan:

$$
\iint_S \tau_{ji} n_j \, dS = \iiint_V \tau_{ji,j} \, dV
$$

Sehingga persamaan menjadi:

$$
\iiint_V \left( \rho \ddot{u}_i - f_i - \tau_{ji,j} \right) dV = 0
$$

Karena persamaan ini berlaku untuk volume $V$ sebarang, maka integran di dalamnya harus bernilai nol di setiap titik. Hal ini menghasilkan **Persamaan Gerak Elastodinamika**:

$$
\rho \ddot{u}_i = f_i + \tau_{ji,j}
$$

### 1.5 Pembuktian Kesimetrisan Tensor Tegangan
Kesimetrisan tensor tegangan ($\tau_{ji} = \tau_{ij}$) dibuktikan menggunakan prinsip **kesetimbangan momentum sudut**. Total momen gaya yang bekerja pada volume $V$ harus sama dengan laju perubahan momentum sudut:

$$
\iiint_V \epsilon_{ijk} x_j \rho \ddot{u}_k \, dV = \iiint_V \epsilon_{ijk} x_j f_k \, dV + \iint_S \epsilon_{ijk} x_j T_k \, dS
$$

Substitusi $T_k = \tau_{lk} n_l$ dan gunakan Teorema Divergensi Gauss pada integral permukaan:

$$
\iint_S \epsilon_{ijk} x_j \tau_{lk} n_l \, dS = \iiint_V \frac{\partial}{\partial x_l} \left( \epsilon_{ijk} x_j \tau_{lk} \right) dV
$$

Lakukan diferensiasi produk di dalam integral:

$$
\frac{\partial}{\partial x_l} \left( \epsilon_{ijk} x_j \tau_{lk} \right) = \epsilon_{ijk} \delta_{jl} \tau_{lk} + \epsilon_{ijk} x_j \tau_{lk,l} = \epsilon_{ijk} \tau_{jk} + \epsilon_{ijk} x_j \tau_{lk,l}
$$

Masukkan kembali ke persamaan momentum sudut dan eliminasi suku-suku yang mengandung persamaan gerak elastodinamika ($\rho \ddot{u}_k - f_k - \tau_{lk,l} = 0$). Hasil akhirnya adalah:

$$
\iiint_V \epsilon_{ijk} \tau_{jk} \, dV = 0
$$

Karena berlaku untuk volume sebarang, diperoleh $\epsilon_{ijk} \tau_{jk} = 0$. Sifat dari simbol Levi-Civita $\epsilon_{ijk}$ memaksa bagian anti-simetris dari $\tau_{jk}$ bernilai nol, sehingga terbukti bahwa tensor tegangan Cauchy bersifat simetris:

$$
\tau_{ji} = \tau_{ij}
$$

---

## 2. HUBUNGAN KONSTITUTIF DAN ENERGI REGANGAN

### 2.1 Hukum Hooke Tergeneralisasi
Untuk medium elastis linier, hubungan antara tegangan dan regangan didefinisikan melalui Hukum Hooke Tergeneralisasi:

$$
\tau_{ij} = c_{ijkl} e_{kl}
$$

Di mana $c_{ijkl}$ adalah **tensor elastisitas (kekakuan)** orde empat yang memiliki $3 \times 3 \times 3 \times 3 = 81$ komponen. Namun, jumlah parameter bebas ini berkurang secara drastis karena sifat-sifat simetri berikut:
1. **Simetri Tegangan** ($\tau_{ij} = \tau_{ji}$): Mengurangi jumlah komponen dari 81 menjadi 54 ($c_{ijkl} = c_{jikl}$).
2. **Simetri Regangan** ($e_{kl} = e_{lk}$): Mengurangi jumlah komponen dari 54 menjadi 36 ($c_{ijkl} = c_{ijlk}$).
3. **Sifat Termodinamika (Simetri Mayor)**: Keberadaan fungsi energi regangan (potensial elastis) mengharuskan $c_{ijkl} = c_{klij}$, sehingga mengurangi parameter independen menjadi **21 komponen bebas** untuk medium anisotropik paling umum (triklinik).

### 2.2 Fungsi Energi Regangan dan Karakteristik Adiabatik
Energi regangan elastis per satuan volume $W$ didefinisikan sebagai usaha yang dilakukan untuk mendeformasi medium dari keadaan tanpa regangan:

$$
W = \frac{1}{2} \tau_{ij} e_{ij} = \frac{1}{2} c_{ijkl} e_{ij} e_{kl}
$$

> **Aspek Fisika (Adiabatik vs. Isotermal)**: Gelombang seismik menjalar dengan frekuensi tinggi (orde Hz hingga ratusan Hz) dan kecepatan tinggi (kilometer per detik). Proses kompresi dan dilatasi yang sangat cepat ini tidak memberikan cukup waktu bagi panas untuk berpindah keluar-masuk dari elemen volume batuan. Oleh karena itu, penjalaran gelombang seismik dikategorikan sebagai **proses adiabatik** (bukan isotermal). Konstanta elastisitas $c_{ijkl}$ yang digunakan dalam seismologi adalah konstanta elastisitas adiabatik, yang nilainya sedikit lebih tinggi daripada konstanta elastisitas isotermal yang diukur pada proses deformasi tektonik lambat.

### 2.3 Medium Isotropik dan Parameter Lamé
Jika sifat fisik medium tidak bergantung pada arah (isotropik), tensor elastisitas $c_{ijkl}$ harus bersifat invarian terhadap rotasi sistem koordinat. Bentuk paling umum dari tensor orde empat isotropik adalah:

$$
c_{ijkl} = \lambda \delta_{ij} \delta_{kl} + \mu (\delta_{ik} \delta_{jl} + \delta_{il} \delta_{jk})
$$

Di mana:
- $\lambda$ dan $\mu$ adalah **konstanta elastisitas Lamé** (di mana $\mu$ juga dikenal sebagai modulus geser atau *rigidity*).
- $\delta_{ij}$ adalah Kronecker delta.

Substitusi bentuk tensor ini ke dalam Hukum Hooke Tergeneralisasi menghasilkan **hubungan konstitutif isotropik**:

$$
\tau_{ij} = \lambda \delta_{ij} e_{kk} + 2\mu e_{ij}
$$

Suku pertama merepresentasikan kontribusi perubahan volume ($e_{kk} = \nabla \cdot \mathbf{u}$), sedangkan suku kedua merepresentasikan deformasi geser murni.

---

## 3. TEOREMA KEUNIKAN DAN RECIPROSITAS BETTI

### 3.1 Teorema Keunikan (Uniqueness Theorem)
Teorema ini menjamin bahwa solusi dari persamaan gerak elastodinamika dengan kondisi awal dan kondisi batas tertentu bersifat tunggal (unik). 

Misalkan terdapat dua solusi perpindahan yang berbeda, $\mathbf{u}^{(1)}$ and $\mathbf{u}^{(2)}$, yang memenuhi persamaan gerak yang sama dengan gaya luar $f_i$ yang sama. Selisih dari kedua solusi tersebut, $\mathbf{w} = \mathbf{u}^{(1)} - \mathbf{u}^{(2)}$, akan memenuhi persamaan gerak homogen tanpa gaya luar ($f_i = 0$):

$$
\rho \ddot{w}_i = \tau_{ji,j}(\mathbf{w})
$$

Kondisi awal untuk selisih solusi ini adalah tenang (nol perpindahan dan nol kecepatan pada $t=0$):
$$
w_i(\mathbf{x}, 0) = 0, \quad \dot{w}_i(\mathbf{x}, 0) = 0
$$

Kondisi batas pada permukaan $S$ yang melingkupi volume $V$ mengharuskan salah satu dari kondisi berikut terpenuhi di setiap titik:
- Nilai perpindahan ditentukan (Dirichlet): $w_i = 0$ pada $S$.
- Nilai traksi ditentukan (Neumann): $T_i(\mathbf{w}) = 0$ pada $S$.

Evaluasi total energi mekanik (kinetik $K$ dan regangan $U$) dari medan selisih $\mathbf{w}$:

$$
E(t) = K(t) + U(t) = \iiint_V \left( \frac{1}{2} \rho \dot{w}_i \dot{w}_i + \frac{1}{2} c_{ijkl} e_{ij}(\mathbf{w}) e_{kl}(\mathbf{w}) \right) dV
$$

Laju perubahan energi terhadap waktu:

$$
\frac{dE}{dt} = \iiint_V \left( \rho \dot{w}_i \ddot{w}_i + \tau_{ij}(\mathbf{w}) \dot{e}_{ij}(\mathbf{w}) \right) dV
$$

Menggunakan persamaan gerak elastodinamika homogen $\rho \ddot{w}_i = \tau_{ji,j}(\mathbf{w})$ dan identitas kalkulus:

$$
\frac{dE}{dt} = \iiint_V \left( \tau_{ji,j}(\mathbf{w}) \dot{w}_i + \tau_{ji}(\mathbf{w}) \dot{w}_{i,j} \right) dV = \iiint_V \frac{\partial}{\partial x_j} \left( \tau_{ji}(\mathbf{w}) \dot{w}_i \right) dV
$$

Gunakan Teorema Divergensi Gauss:

$$
\frac{dE}{dt} = \iint_S \tau_{ji}(\mathbf{w}) \dot{w}_i n_j \, dS = \iint_S T_i(\mathbf{w}) \dot{w}_i \, dS
$$

Karena kondisi batas mensyaratkan $T_i(\mathbf{w}) = 0$ atau $w_i = 0$ (yang berimplikasi $\dot{w}_i = 0$) pada permukaan $S$, maka integral permukaan tersebut bernilai nol:

$$
\frac{dE}{dt} = 0 \implies E(t) = E(0)
$$

Karena pada kondisi awal $t=0$ nilai $w_i = 0$ dan $\dot{w}_i = 0$, maka $E(0) = 0$. Akibatnya, $E(t) = 0$ untuk seluruh $t \ge 0$. Karena energi kinetik dan regangan bernilai positif-semi-definit, satu-satunya cara agar total energi bernilai nol adalah jika $\dot{w}_i = 0$ dan $e_{ij}(\mathbf{w}) = 0$. Hal ini membuktikan bahwa $\mathbf{w} = 0$, atau dengan kata lain:

$$
\mathbf{u}^{(1)} = \mathbf{u}^{(2)} \quad \text{(Solusi Unik)}
$$

### 3.2 Teorema Resiprositas Betti
Teorema Resiprositas Betti menghubungkan dua keadaan elastis bebas yang berbeda pada medium yang sama. Misalkan keadaan pertama didefinisikan oleh perpindahan $\mathbf{u}$ akibat gaya volume $\mathbf{f}$ dengan traksi $\mathbf{T}(\mathbf{u})$, dan keadaan kedua didefinisikan oleh perpindahan $\mathbf{v}$ akibat gaya volume $\mathbf{g}$ dengan traksi $\mathbf{T}(\mathbf{v})$.

Bentuk statis Teorema Betti didasarkan pada kesimetrisan tensor elastisitas ($c_{ijkl} = c_{klij}$), yang menghasilkan kesamaan kepadatan energi kerja silang:

$$
\tau_{ij}(\mathbf{u}) e_{ij}(\mathbf{v}) = \tau_{ij}(\mathbf{v}) e_{ij}(\mathbf{u})
$$

Melalui integrasi volume dan aplikasi Teorema Divergensi Gauss, diperoleh hubungan integral dinamis Teorema Resiprositas Betti:

$$
\iiint_V (f_i - \rho \ddot{u}_i) v_i \, dV + \iint_S T_i(\mathbf{u}, \mathbf{n}) v_i \, dS = \iiint_V (g_i - \rho \ddot{v}_i) u_i \, dV + \iint_S T_i(\mathbf{v}, \mathbf{n}) u_i \, dS
$$

### 3.3 Bentuk Konvolusi Ruang-Waktu (Quiescent Past)
Jika kita mengasumsikan medium dalam kondisi tenang pada masa lalu yang jauh ($t < 0$, asumsi *quiescent past*), kita dapat menerapkan transformasi Fourier atau operasi konvolusi waktu pada Teorema Resiprositas Betti. Hubungan resiprokal dalam domain waktu dinyatakan sebagai:

$$
\int_{-\infty}^{\infty} dt \iiint_V \left[ f_i(\mathbf{x}, t) v_i(\mathbf{x}, \tau - t) - g_i(\mathbf{x}, \tau - t) u_i(\mathbf{x}, t) \right] dV = \int_{-\infty}^{\infty} dt \iint_S \left[ u_i(\mathbf{x}, t) T_i(\mathbf{v}(\mathbf{x}, \tau - t), \mathbf{n}) - v_i(\mathbf{x}, \tau - t) T_i(\mathbf{u}(\mathbf{x}, t), \mathbf{n}) \right] dS
$$

Formulasi konvolusi ini sangat krusial dalam seismologi karena memungkinkan kita menukar posisi sumber dan penerima gelombang (*source-receiver reciprocity*).

---

## 4. PENGANTAR FUNGSI GREEN DAN TEOREMA REPRESENTASI

### 4.1 Definisi Fungsi Green Elastodinamika
Fungsi Green $G_{in}(\mathbf{x}, t; \boldsymbol{\xi}, \tau)$ didefinisikan sebagai respon perpindahan pada titik koordinat $\mathbf{x}$ dan waktu $t$ dalam arah sumbu-$i$, yang dihasilkan oleh sumber impuls gaya titik terkonsentrasi (Dirac delta) yang bekerja pada titik lokasi $\boldsymbol{\xi}$ dan waktu $\tau$ dalam arah sumbu-$n$.

### 4.2 Persamaan Diferensial Pengatur Fungsi Green
Secara matematis, Fungsi Green memenuhi persamaan gerak elastodinamika dengan gaya volume berupa fungsi delta Dirac ruang-waktu:

$$
\rho(\mathbf{x}) \frac{\partial^2}{\partial t^2} G_{in}(\mathbf{x}, t; \boldsymbol{\xi}, \tau) - \frac{\partial}{\partial x_j} \left( c_{ijlk}(\mathbf{x}) \frac{\partial}{\partial x_k} G_{ln}(\mathbf{x}, t; \boldsymbol{\xi}, \tau) \right) = \delta_{in} \delta(\mathbf{x} - \boldsymbol{\xi}) \delta(t - \tau)
$$

### 4.3 Sifat Resiprositas Ruang-Waktu
Menggunakan Teorema Resiprositas Betti, dapat dibuktikan bahwa Fungsi Green bersifat resiprokal terhadap pertukaran posisi ruang dan waktu:

$$
G_{in}(\mathbf{x}, t; \boldsymbol{\xi}, \tau) = G_{ni}(\boldsymbol{\xi}, -\tau; \mathbf{x}, -t)
$$

Untuk medium invarian-waktu, sifat ini menyederhanakan hubungan koordinat waktu menjadi:

$$
G_{in}(\mathbf{x}, t; \boldsymbol{\xi}, 0) = G_{ni}(\boldsymbol{\xi}, t; \mathbf{x}, 0)
$$

Hal ini berarti: perekaman komponen gerak arah-$i$ di stasiun $\mathbf{x}$ akibat sumber arah-$n$ di stasiun $\boldsymbol{\xi}$ akan menghasilkan bentuk gelombang yang persis sama jika stasiun penerima dan sumber ditukar posisinya.

### 4.4 Teorema Representasi Elastodinamika (Representation Theorem)
Teorema Representasi menghubungkan medan perpindahan elastis $u_n(\mathbf{x}, t)$ di sembarang titik di dalam volume $V$ dengan gaya volume internal $f_i$ dan kondisi batas di permukaan luar $S$.

Dengan mensubstitusi medan perpindahan nyata $u_i(\mathbf{x}, t)$ dan Fungsi Green $G_{in}(\mathbf{x}, t; \boldsymbol{\xi}, \tau)$ ke dalam Teorema Betti bentuk konvolusi, kita memperoleh **Teorema Representasi Elastodinamika**:

$$
u_n(\mathbf{x}, t) = \iiint_V f_i(\boldsymbol{\xi}, \tau) * G_{in}(\mathbf{x}, t; \boldsymbol{\xi}, \tau) \, dV(\boldsymbol{\xi}) + \iint_S \left[ G_{in}(\mathbf{x}, t; \boldsymbol{\xi}, \tau) * T_i(\mathbf{u}(\boldsymbol{\xi}, \tau), \mathbf{n}) - u_i(\boldsymbol{\xi}, \tau) * c_{ijkl}(\boldsymbol{\xi}) \frac{\partial G_{kn}(\mathbf{x}, t; \boldsymbol{\xi}, \tau)}{\partial \xi_l} n_j \right] dS(\boldsymbol{\xi})
$$

Di mana simbol $*$ menyatakan operator konvolusi waktu:
$$
A(t) * B(t) = \int_{-\infty}^{\infty} A(\tau) B(t - \tau) \, d\tau
$$

**Interpretasi Fisik**:
- Suku pertama (integral volume) merepresentasikan kontribusi langsung dari gaya luar atau sumber gempa yang berada di dalam medium.
- Suku kedua (integral permukaan) merepresentasikan kontribusi kondisi batas (traksi dan perpindahan) di permukaan luar $S$ yang dirambatkan ke titik penerima menggunakan Fungsi Green dan gradien spasialnya.

---

## 5. FORMULASI DALAM KOORDINAT KURVILINIER ORTOGONAL

Bumi sering kali dimodelkan sebagai bola berlapis (misal model PREM). Untuk sistem fisik dengan simetri bola atau silinder, penyelesaian persamaan elastodinamika dalam koordinat Kartesian menjadi sangat rumit. Oleh karena itu, kita memerlukan formulasi dalam koordinat kurvilinier ortogonal dengan menggunakan **faktor skala (scaling functions)** $h_1, h_2, h_3$.

Elemen garis ds dalam koordinat kurvilinier didefinisikan sebagai:
$$
(ds)^2 = (h_1 dq_1)^2 + (h_2 dq_2)^2 + (h_3 dq_3)^2
$$

### 5.1 Koordinat Polar Silinder $(r, \phi, z)$
Faktor skala untuk koordinat silinder adalah $h_r = 1$, $h_\phi = r$, dan $h_z = 1$.

- **Hubungan Regangan-Perpindahan (Strain-Displacement)**:
  $$
  e_{rr} = \frac{\partial u_r}{\partial r}
  $$
  $$
  e_{\phi\phi} = \frac{1}{r}\frac{\partial u_\phi}{\partial \phi} + \frac{u_r}{r}
  $$
  $$
  e_{zz} = \frac{\partial u_z}{\partial z}
  $$
  $$
  e_{r\phi} = \frac{1}{2}\left( \frac{1}{r}\frac{\partial u_r}{\partial \phi} + \frac{\partial u_\phi}{\partial r} - \frac{u_\phi}{r} \right)
  $$
  $$
  e_{\phi z} = \frac{1}{2}\left( \frac{\partial u_\phi}{\partial z} + \frac{1}{r}\frac{\partial u_z}{\partial \phi} \right)
  $$
  $$
  e_{zr} = \frac{1}{2}\left( \frac{\partial u_z}{\partial r} + \frac{\partial u_r}{\partial z} \right)
  $$

### 5.2 Koordinat Polar Bola $(r, \theta, \phi)$
Faktor skala untuk koordinat bola adalah $h_r = 1$, $h_\theta = r$, dan $h_\phi = r \sin\theta$.

- **Hubungan Regangan-Perpindahan (Strain-Displacement)**:
  $$
  e_{rr} = \frac{\partial u_r}{\partial r}
  $$
  $$
  e_{\theta\theta} = \frac{1}{r}\frac{\partial u_\theta}{\partial \theta} + \frac{u_r}{r}
  $$
  $$
  e_{\phi\phi} = \frac{1}{r \sin\theta}\frac{\partial u_\phi}{\partial \phi} + \frac{u_r}{r} + \frac{u_\theta \cot\theta}{r}
  $$
  $$
  e_{r\theta} = \frac{1}{2}\left( r \frac{\partial}{\partial r}\left(\frac{u_\theta}{r}\right) + \frac{1}{r}\frac{\partial u_r}{\partial \theta} \right)
  $$
  $$
  e_{\theta\phi} = \frac{1}{2}\left( \frac{\sin\theta}{r}\frac{\partial}{\partial \theta}\left(\frac{u_\phi}{\sin\theta}\right) + \frac{1}{r \sin\theta}\frac{\partial u_\theta}{\partial \phi} \right)
  $$
  $$
  e_{\phi r} = \frac{1}{2}\left( \frac{1}{r \sin\theta}\frac{\partial u_r}{\partial \phi} + r \frac{\partial}{\partial r}\left(\frac{u_\phi}{r}\right) \right)
  $$

Formulasi ini sangat penting untuk menurunkan persamaan gelombang seismik global (seperti moda vibrasi bebas Bumi / *free oscillation*) dan pemodelan penjalaran gelombang dalam skala bola Bumi utuh.
