Handout Kuliah: Seismologi Kuantitatif (Minggu 1) - Teorema Dasar dalam Elastisitas Dinamis

1. Fondasi Formulasi Elastodinamika dan Kinematika Deformasi

Seismologi kuantitatif merupakan disiplin yang mendeduksi sifat fisik interior Bumi dan mekanisme sumber gempa melalui analisis seismogram. Secara fundamental, elastodinamika menyediakan kerangka kerja matematis untuk memahami bagaimana gangguan mekanis merambat sebagai gelombang. Penting bagi kita untuk memahami derivasi matematis secara ketat guna menghindari kesalahan interpretasi fisik. Sejarah mencatat kasus F. Omori (1906) yang salah mengidentifikasi polarisasi fase S sebagai gerakan longitudinal. Kesalahan ini merupakan "kesalahan ganda" (double error) yang ironisnya konsisten dengan observasi pada saat itu: Omori menempatkan episenter pada jarak yang salah karena mengabaikan kedalaman fokus, dan kesimpulannya didukung oleh pandangan dominan "Isostasi" (yang meyakini interior Bumi terlalu daktil untuk patahan dalam) serta "Doktrin Mallet" (yang menyatakan gerak utama di area episentral bersifat longitudinal). Tanpa pemahaman dinamika yang kuat, konsistensi semu semacam ini dapat menyesatkan sains selama puluhan tahun.

* Analisis Deskripsi Lagrangian vs. Eulerian: Dalam mekanika kontinuum, deskripsi Lagrangian berfokus pada partikel materi spesifik yang diidentifikasi oleh posisi referensinya \mathbf{x} pada waktu t_0. Sebaliknya, deskripsi Eulerian berfokus pada apa yang terjadi di titik spasial tetap \mathbf{X} seiring waktu. Dalam seismologi, kita hampir secara eksklusif menggunakan deskripsi Lagrangian. Hal ini dikarenakan seismometer dipasang pada partikel tanah tertentu; dengan demikian, seismogram adalah rekaman langsung dari sejarah gerak partikel tersebut, u(\mathbf{x}, t).
* Derivasi Tensor Regangan Infinitesimal (e_{ij}): Untuk menganalisis deformasi, kita meninjau perubahan posisi relatif antara dua titik yang awalnya berada di \mathbf{x} dan \mathbf{x} + \delta\mathbf{x}. Melalui ekspansi Taylor dari medan perpindahan \mathbf{u} di sekitar \mathbf{x}: u_i(\mathbf{x} + \delta\mathbf{x}) = u_i(\mathbf{x}) + \frac{\partial u_i}{\partial x_j} \delta x_j + \mathcal{O}(|\delta\mathbf{x}|^2) Perubahan relatif posisi atau distorsi ditentukan oleh gradien perpindahan u_{i,j} = \frac{\partial u_i}{\partial x_j}. Kita dapat mendefinisikan tensor regangan infinitesimal e_{ij} sebagai bagian simetris dari gradien ini: e_{ij} = \frac{1}{2}(u_{i,j} + u_{j,i})
* Dekomposisi Gerak Lokal: Gerak total suatu elemen volume infinitesimal \delta u_i dapat didekomposisi menjadi regangan murni dan rotasi benda tegar: \delta u_i = e_{ij} \delta x_j + \frac{1}{2}(u_{i,j} - u_{j,i}) \delta x_j Menggunakan identitas vektor, suku kedua dapat dinyatakan sebagai rotasi infinitesimal: \delta u_i = e_{ij} \delta x_j + \frac{1}{2}(\text{curl } \mathbf{u} \times \delta \mathbf{x})_i Di sini, e_{ij} menyebabkan perubahan bentuk dan volume, sementara rotasi tidak mengubah panjang elemen garis.
* Mekanika Tegangan dan Hukum Kesetimbangan: Traksi \mathbf{T}(\mathbf{n}) adalah gaya per satuan luas yang bekerja pada permukaan dengan normal \mathbf{n}. Melalui analisis momentum pada tetrahedron infinitesimal dan mengambil limit volume \Delta V \to 0, kita membuktikan hubungan linier antara traksi dan tensor tegangan Cauchy \tau_{ji}: T_i(\mathbf{n}) = \tau_{ji} n_j Persamaan ini menunjukkan bahwa tegangan pada titik mana pun ditentukan sepenuhnya oleh sembilan komponen \tau_{ji}.
* Derivasi Persamaan Gerak (Equation of Motion): Dengan menerapkan hukum Newton II pada volume kontinuum dan menggunakan teorema divergensi Gauss untuk mengubah gaya permukaan menjadi gaya volume, kita memperoleh: \rho \ddot{u}_i = f_i + \tau_{ji,j} Simetri tensor tegangan (\tau_{ji} = \tau_{ij}) dibuktikan melalui kekekalan momentum sudut. Menggunakan tensor alternasi Levi-Civita \epsilon_{ijk}: \iiint_V \epsilon_{ijk} \tau_{jk} dV = 0 \implies \epsilon_{ijk} \tau_{jk} = 0 Karena identitas ini berlaku untuk setiap volume V, maka haruslah \tau_{jk} = \tau_{kj}.

Connective Tissue: Persamaan gerak di atas memberikan 3 persamaan dengan 9 komponen tegangan yang tidak diketahui. Untuk menutup sistem ini (close the system), kita memerlukan hubungan fungsional yang menghubungkan tegangan dengan regangan berdasarkan sifat material.

2. Hubungan Konstitutif, Termodinamika, dan Isotropi

Hukum konstitutif menjembatani konsep mekanika murni dengan realitas material Bumi. Hubungan ini menentukan bagaimana medium menyimpan energi potensial elastis dan merespons beban dinamis.

* Hukum Hooke Tergeneralisasi: Untuk deformasi kecil, hubungan antara tegangan dan regangan bersifat linier melalui tensor elastisitas orde empat c_{ijkl}: \tau_{ij} = c_{ijkl} e_{kl}
* Reduksi Parameter dan Fungsi Energi Regangan (W): Tensor c_{ijkl} awalnya memiliki 81 komponen. Simetri \tau_{ij} dan e_{kl} mereduksi komponen independen menjadi 36. Selanjutnya, argumen termodinamika mengenai keberadaan fungsi energi regangan W = \frac{1}{2}c_{ijkl}e_{ij}e_{kl} (di mana \tau_{ij} = \partial W / \partial e_{ij}) mensyaratkan simetri tambahan c_{ijkl} = c_{klij}, sehingga menyisakan 21 parameter bebas untuk medium anisotropik umum.
* Kondisi Adiabatik dalam Seismologi: Propagasi gelombang seismik adalah proses adiabatik (entropi konstan), bukan isotermal. Hal ini dikarenakan konstanta waktu difusi termal dalam batuan ((\text{jarak})^2/\text{difusivitas}) jauh lebih lama daripada periode gelombang seismik. Oleh karena itu, kita menggunakan modulus elastisitas adiabatik dalam setiap perhitungan kecepatan gelombang.
* Medium Isotropik dan Parameter Lamé: Bumi sering dimodelkan sebagai medium isotropik di mana sifat elastis tidak bergantung arah. Dalam kondisi ini, c_{ijkl} hanya bergantung pada parameter \lambda dan \mu (modulus geser): \tau_{ij} = \lambda \delta_{ij} e_{kk} + 2\mu e_{ij} Di mana e_{kk} = e_{11} + e_{22} + e_{33} mewakili dilatasi (perubahan volume).

Connective Tissue: Dengan 3 persamaan gerak, 6 hubungan konstitutif, dan 6 definisi regangan, kita kini memiliki sistem 15 persamaan dengan 15 variabel (u_i, e_{ij}, \tau_{ij}) yang tertutup. Tugas selanjutnya adalah memastikan bahwa solusi dari sistem ini bersifat unik.

3. Teorema Keunikan dan Resiprositas Betti

Teorema keunikan menjamin bahwa pemodelan kita memiliki makna fisik tunggal, sementara resiprositas memberikan simetri matematis yang sangat kuat antara sumber dan penerima.

* Teorema Keunikan: Solusi perpindahan \mathbf{u}(\mathbf{x}, t) di dalam volume V bersifat unik jika diberikan:
  1. Kondisi awal \mathbf{u} dan \dot{\mathbf{u}} pada t = t_0.
  2. Gaya volume \mathbf{f} di seluruh V untuk t > t_0.
  3. Kondisi batas pada permukaan S (baik traksi \mathbf{T} atau perpindahan \mathbf{u}). Bukti keunikan didasarkan pada sifat positif definit dari energi kinetik dan energi regangan; jika ada dua solusi, selisih energinya harus nol, yang berarti kedua solusi tersebut identik.
* Teorema Resiprositas Betti: Mengaitkan dua keadaan elastis yang berbeda (\mathbf{u}, \mathbf{f} dan \mathbf{v}, \mathbf{g}) pada medium yang sama: \iiint_V (\mathbf{f} - \rho\mathbf{\ddot{u}}) \cdot \mathbf{v} \, dV + \iint_S \mathbf{T}(\mathbf{u}, \mathbf{n}) \cdot \mathbf{v} \, dS = \iiint_V (\mathbf{g} - \rho\mathbf{\ddot{v}}) \cdot \mathbf{u} \, dV + \iint_S \mathbf{T}(\mathbf{v}, \mathbf{n}) \cdot \mathbf{u} \, dS
* Quiescent Past: Untuk medium yang diam sebelum gangguan (t < 0), kita dapat menerapkan konvolusi waktu pada teorema Betti: \int_{-\infty}^{\infty} dt \iiint_V u_i g_i \, dV + \int_{-\infty}^{\infty} dt \iint_S v_i T_i(\mathbf{u}) \, dS = \dots

Connective Tissue: Formalisme resiprositas ini memungkinkan kita untuk menggunakan respons terhadap sumber titik sederhana (Fungsi Green) guna membangun solusi bagi sumber gempa yang jauh lebih kompleks.

4. Fungsi Green dan Teorema Representasi Elastodinamika

Fungsi Green G_{in}(\mathbf{x}, t; \mathbf{\xi}, \tau) mewakili perpindahan pada arah-i di titik \mathbf{x} waktu t, akibat gaya impuls satuan pada arah-n di titik \mathbf{\xi} waktu \tau.

* Persamaan Diferensial Fungsi Green: \rho \frac{\partial^2}{\partial t^2} G_{in} = \delta_{in} \delta(\mathbf{x}-\mathbf{\xi}) \delta(t-\tau) + \frac{\partial}{\partial x_j} \left( c_{ijkl} \frac{\partial}{\partial x_l} G_{kn} \right)
* Teorema Representasi de Hoop-Knopoff: Sesuai dengan peran "bookkeeping", perpindahan total u_n di sembarang titik dapat dinyatakan sebagai: u_n(\mathbf{x}, t) = \int_{-\infty}^{\infty} d\tau \iiint_V f_i(\mathbf{\xi}, \tau) G_{in}(\mathbf{\xi}, t-\tau; \mathbf{x}, 0) \, dV(\mathbf{\xi}) + \int_{-\infty}^{\infty} d\tau \iint_S [G_{in} T_i(\mathbf{u}, \mathbf{n}) - u_i c_{ijkl} n_j \frac{\partial}{\partial \xi_l} G_{kn}] \, dS(\mathbf{\xi})
* Interpretasi Fisis: Suku pertama mewakili kontribusi langsung dari gaya volume (seperti ledakan), sedangkan suku kedua mewakili kontribusi dari kondisi batas atau diskontinuitas pada permukaan (seperti pergeseran pada bidang patahan gempa).

Connective Tissue: Formulasi di atas menggunakan koordinat Cartesian, namun untuk aplikasi pada Bumi yang bulat, kita harus mentransformasikan persamaan ini ke dalam koordinat kurvilinier.

5. Formulasi dalam Koordinat Kurvilinier Ortogonal

Penggunaan koordinat kurvilinier (bola, silinder) diperlukan untuk menyederhanakan penerapan kondisi batas pada permukaan melengkung Bumi.

* Faktor Skala (h^p): Elemen garis dalam koordinat ortogonal umum c^1, c^2, c^3 diberikan oleh (ds)^2 = (h^1 dc^1)^2 + (h^2 dc^2)^2 + (h^3 dc^3)^2. Untuk koordinat bola (r, \theta, \phi): h^1 = 1, \quad h^2 = r, \quad h^3 = r \sin \theta
* Regangan dalam Koordinat Kurvilinier: Komponen regangan mengalami modifikasi akibat perubahan arah vektor basis. Menggunakan komponen fisik, regangan diagonal e_{pp} didefinisikan sebagai: e_{11} = \frac{1}{h^1} \frac{\partial u_1}{\partial c^1} + \frac{u_2}{h^1 h^2} \frac{\partial h^1}{\partial c^2} + \frac{u_3}{h^1 h^3} \frac{\partial h^1}{\partial c^3} Sebagai contoh, untuk komponen e_{\theta\theta} (arah \theta) dalam koordinat bola: e_{\theta\theta} = \frac{1}{r} \frac{\partial u_\theta}{\partial \theta} + \frac{u_r}{r} Munculnya suku tambahan u_r/r menunjukkan bahwa perpindahan radial murni dapat menyebabkan regangan tangensial pada permukaan melengkung.
* Persamaan Gerak Global: Persamaan \rho \ddot{u}_i dalam koordinat ini melibatkan suku-suku kelengkungan yang memungkinkan kita untuk memecahkan masalah getaran bebas Bumi (free oscillations) dan perambatan gelombang permukaan pada geometri bola.

Seluruh teorema dasar ini membentuk landasan bagi analisis mekanisme sumber gempa yang akan kita bahas pada sesi berikutnya. Pemahaman mendalam tentang Fungsi Green dan Teorema Representasi adalah kunci untuk mengubah data seismogram menjadi parameter fisis sumber gempa.
