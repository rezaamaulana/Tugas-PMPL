### chapter 1 

# The software quality challenge

Two basic questions should be raised before we proceed to list the variety of subjects and details of the book:

(1) Is it justified to devote a special book to software quality assurance (SQA)
or, in other words, can we not use the general quality assurance textbooks
available that are applicable to numerous areas and industries?

(2) Having decided to develop specialized books for software quality assurance, at which of the various environments of software development, from
amateurs’ hobby to professionals’ work, should we aim our main efforts?
Put simply, what are the unique characteristics of the SQA environment?

> _Dua pertanyaan dasar harus diajukan sebelum kita melanjutkan untuk membuat daftar variasi dari topik dan detail buku:_
>
>_(1) Apakah dibenarkan untuk mencurahkan buku khusus untuk jaminan kualitas perangkat lunak (SQA)
atau, dengan kata lain, tidak bisakah kita menggunakan buku teks penjaminan mutu umum?
tersedia yang berlaku untuk berbagai area dan industri?_
>
>_(2) Setelah memutuskan untuk mengembangkan buku khusus untuk jaminan kualitas perangkat lunak, di mana dari berbagai lingkungan pengembangan perangkat lunak, dari:
hobi amatir ke pekerjaan profesional, haruskah kita mengarahkan upaya utama kita?
Sederhananya, apa karakteristik unik dari lingkungan SQA?_

The objective of this chapter is to answer these questions by exploring the related issues.

After completing this chapter, you will be able to:

- Identify the unique characteristics of software as a product and as production process that justify separate treatment of its quality issues.
- Recognize the characteristics of the environment where professional software development and maintenance take place.
- Explain the main environmental difficulties faced by software development and maintenance teams as a result of the environment in which
they operate. 

> _Tujuan dari bab ini adalah untuk menjawab pertanyaan-pertanyaan ini dengan mengeksplorasi isu-isu terkait._
>
> _Setelah menyelesaikan bab ini, Anda akan dapat:_
>
> - _Identifikasi karakteristik unik perangkat lunak sebagai produk dan sebagai proses produksi yang membenarkan perlakuan terpisah terhadap masalah kualitasnya._
> - _Mengenali karakteristik lingkungan tempat pengembangan dan pemeliharaan perangkat lunak profesional berlangsung._
> - _Jelaskan kesulitan lingkungan utama yang dihadapi oleh tim pengembangan dan pemeliharaan perangkat lunak sebagai akibat dari lingkungan di mana
mereka beroperasi._

**1.1 The uniqueness of software quality assurance**

“Look at this,” shouted my friend while handing me Dagal Features’s
Limited Warranty leaflet. “Even Dagal Features can’t cope with software
bugs.” He pointed to a short paragraph on page 3 of the leaflet that states
the conditions of the warranty for AMGAL, a leading Software Master product
sold all over the world. The leaflet states the following:

> _“Lihat ini,” teriak temanku sambil menyodorkan Fitur Dagal kepadaku
Pamflet Garansi Terbatas. “Bahkan Fitur Dagal tidak dapat mengatasi perangkat lunak
bug." Dia menunjuk ke paragraf pendek di halaman 3 dari selebaran yang menyatakan
ketentuan garansi untuk AMGAL, produk Master Perangkat Lunak terkemuka
dijual di seluruh dunia. Selebaran tersebut menyatakan sebagai berikut:_

**LIMITED WARRANTY**

Dagal Features provides no warranty, either expressed or implied, with
respect to AMGAL’s performance, reliability or fitness for any specified
purpose. Dagal Features does not warrant that the software or its documentation will fulfil your requirements. although Dagal Features has
performed thorough tests of the software and reviewed the documentation, Dagal Features does not provide any warranty that the software and
its documentation are free of errors. Dagal Features will in no case be
liable for any damages, incidental, direct, indirect or consequential,
incurred as a result of impaired data, recovery costs, profit loss and third
party claims. the software is licensed “as is”. the purchaser assumes the
complete risk stemming from application of the AMGAL program, its
quality and performance.

If physical defects are discovered in the documentation or the CD on
which AMGAL is distributed, Dagal Features will replace, at no charge,
the documentation or the CD within 180 days of purchase, provided
proof of purchase is presented.

> _**GARANSI TERBATAS**_
>
> _Fitur Dagal tidak memberikan jaminan, baik tersurat maupun tersirat, dengan
sehubungan dengan kinerja, keandalan, atau kesesuaian AMGAL untuk semua yang ditentukan
tujuan. Fitur Dagal tidak menjamin bahwa perangkat lunak atau dokumentasinya akan memenuhi kebutuhan Anda. meskipun Fitur Dagal memiliki
melakukan pengujian perangkat lunak secara menyeluruh dan meninjau dokumentasi, Fitur Dagal tidak memberikan jaminan apa pun bahwa perangkat lunak dan
dokumentasinya bebas dari kesalahan. Fitur Dagal tidak akan menjadi
bertanggung jawab atas segala kerusakan, insidental, langsung, tidak langsung atau konsekuensial,
timbul sebagai akibat dari data yang rusak, biaya pemulihan, kerugian laba, dan ketiga
klaim pihak. perangkat lunak dilisensikan "sebagaimana adanya". pembeli mengasumsikan
risiko lengkap yang berasal dari penerapan program AMGAL,
kualitas dan kinerja._
>
> _Jika cacat fisik ditemukan dalam dokumentasi atau CD di
yang AMGAL didistribusikan, Fitur Dagal akan menggantikan, tanpa biaya,
dokumentasi atau CD dalam waktu 180 hari setelah pembelian, asalkan
bukti pembelian disajikan._

“Is the AMGAL software really so special that its developers are incapable
of meeting the challenge of assuring a bug-free product?” continued my
friend. “Do other software packages limit their warranties in the same way?”
Though Dagal Features and AMGAL are fictitious, an examination of
the warranties offered by other software developers reveals a similar pattern.
No developer will declare that its software is free of defects, as major manufacturers of computer hardware are wont to do. This refusal actually
reflects the essential elemental differences between software and other industrial
products, such as automobiles, washing machines or radios. These differences can be categorized as follows:

> _“Apakah perangkat lunak AMGAL benar-benar istimewa sehingga pengembangnya tidak mampu
memenuhi tantangan untuk memastikan produk bebas bug?” lanjut saya
teman. “Apakah paket perangkat lunak lain membatasi jaminan mereka dengan cara yang sama?”
Meskipun Fitur Dagal dan AMGAL adalah fiktif, pemeriksaan terhadap
jaminan yang ditawarkan oleh pengembang perangkat lunak lain mengungkapkan pola yang sama.
Tidak ada pengembang yang akan menyatakan bahwa perangkat lunaknya bebas dari cacat, seperti yang biasa dilakukan oleh produsen besar perangkat keras komputer. Penolakan ini sebenarnya
mencerminkan perbedaan unsur penting antara perangkat lunak dan industri lainnya
produk, seperti mobil, mesin cuci atau radio. Perbedaan tersebut dapat dikategorikan sebagai berikut:_

1. Product complexity. Product complexity can be measured by the number of operational modes the product permits. An industrial product,
even an advanced machine, does not allow for more than a few thousand modes of operation, created by the combinations of its different
machine settings. Looking at a typical software package one can find
millions of software operation possibilities. Assuring that the multitude
of operational possibilities is correctly defined and developed is a major
challenge to the software industry.

    > 1. _Kompleksitas produk. Kompleksitas produk dapat diukur dengan jumlah mode operasional yang diizinkan produk. Sebuah produk industri,
bahkan mesin canggih, tidak memungkinkan lebih dari beberapa ribu mode operasi, yang dibuat oleh kombinasi yang berbeda
pengaturan mesin. Melihat paket perangkat lunak khas yang dapat ditemukan
jutaan kemungkinan operasi perangkat lunak. Memastikan bahwa orang banyak
kemungkinan operasional didefinisikan dengan benar dan dikembangkan adalah
tantangan bagi industri perangkat lunak._

2. Product visibility. Whereas the industrial products are visible, software
products are invisible. Most of the defects in an industrial product can be
detected during the manufacturing process. Moreover the absence of a
part in an industrial product is, as a rule, highly visible (imagine a door
missing from your new car). However, defects in software products
(whether stored on diskettes or CDs) are invisible, as is the fact that parts
of a software package may be absent from the beginning.

    >2. _Visibilitas produk. Sedangkan produk industri terlihat, perangkat lunak
produk tidak terlihat. Sebagian besar cacat pada produk industri dapat
terdeteksi selama proses produksi. Apalagi tidak adanya
bagian dalam produk industri, sebagai suatu peraturan, sangat terlihat (bayangkan sebuah pintu
hilang dari mobil baru Anda). Namun, cacat pada produk perangkat lunak
(apakah disimpan di disket atau CD) tidak terlihat, seperti fakta bahwa bagian-bagiannya
paket perangkat lunak mungkin tidak ada sejak awal._

3. Product development and production process. Let us now review the
phases at which the possibility of detecting defects in an industrial product may arise : 

    (a) Product development. In this phase the designers and quality assurance (QA) staff check and test the product prototype, in order to detect its defects.
    
    (b) Product production planning. During this phase the production process and tools are designed and prepared. In some products there is a need for a special production line to be designed and built. This phase thus provides additional opportunities to inspect the product, which may reveal defects that “escaped” the reviews and tests conducted during the development phase.

    (c) Manufacturing. At this phase QA procedures are applied to detect failures of products themselves. Defects in the product detected in the first period of manufacturing can usually be corrected by a change in the product’s design or materials or in the production tools, in a way that eliminates such defects in products manufactured in the future. 

    > 3. _Pengembangan produk dan proses produksi. Mari kita tinjau sekarang fase di mana kemungkinan mendeteksi cacat pada produk industri mungkin muncul:_
    >
    >       _(a) Pengembangan produk. Pada fase ini para desainer dan staf jaminan kualitas (QA) memeriksa dan menguji prototipe produk, untuk mendeteksi cacatnya._
    >
    >       _(b) Perencanaan produksi produk. Selama fase ini proses produksi dan alat dirancang dan disiapkan. Dalam beberapa produk ada kebutuhan untuk jalur produksi khusus untuk dirancang dan dibangun. Fase ini dengan demikian memberikan peluang tambahan untuk memeriksa produk, yang dapat mengungkapkan cacat yang "lolos" dari tinjauan dan pengujian yang dilakukan selama fase pengembangan._
    >
    >       _(c) Manufaktur. Pada fase ini prosedur QA diterapkan untuk mendeteksi kegagalan produk itu sendiri. Cacat pada produk yang terdeteksi pada periode pertama pembuatan biasanya dapat diperbaiki dengan perubahan desain produk atau bahan atau alat produksi, dengan cara menghilangkan cacat tersebut pada produk yang diproduksi di masa depan._

In comparison to industrial products, software products do not benefit
from the opportunities for detection of defects at all three phases of the
production process. The only phase when defects can be detected is the
development phase. Let us review what each phase contributes to the
detection of defects:

(a) Product development. During this phase, efforts of the development teams and software quality assurance professionals are directed toward detecting inherent product defects. At the end of this phase an approved prototype, ready for reproduction, becomes available.

(b) Product production planning. This phase is not required for the software production process, as the manufacturing of software copies
and printing of software manuals are conducted automatically. This
applies to any software product, whether the number of copies is
small, as in custom-made software, or large, as in software packages
sold to the general public.

(c) Manufacturing. As mentioned previously, the manufacturing of
software is limited to copying the product and printing copies of the
software manuals. Consequently, expectations for detecting defects
are quite limited during this phase.

>_Dibandingkan dengan produk industri, produk perangkat lunak tidak menguntungkan
dari peluang untuk mendeteksi cacat pada ketiga fase
proses produksi. Satu-satunya fase ketika cacat dapat dideteksi adalah
fase pengembangan. Mari kita tinjau apa kontribusi setiap fase terhadap
deteksi cacat:_
>
>_(a) Pengembangan produk. Selama fase ini, upaya tim pengembangan dan profesional jaminan kualitas perangkat lunak diarahkan untuk mendeteksi cacat produk yang melekat. Pada akhir fase ini, prototipe yang disetujui, siap untuk direproduksi, tersedia._
>
>_(b) Perencanaan produksi produk. Fase ini tidak diperlukan untuk proses produksi perangkat lunak, karena pembuatan salinan perangkat lunak
dan pencetakan manual perangkat lunak dilakukan secara otomatis. Ini
berlaku untuk produk perangkat lunak apa pun, baik jumlah salinannya
kecil, seperti dalam perangkat lunak yang dibuat khusus, atau besar, seperti dalam paket perangkat lunak
dijual kepada masyarakat umum._
>
>_(c) Manufaktur. Seperti disebutkan sebelumnya, pembuatan
perangkat lunak terbatas untuk menyalin produk dan mencetak salinan dari
manual perangkat lunak. Akibatnya, harapan untuk mendeteksi cacat
sangat terbatas selama fase ini._

The differences affecting the detection of defects in software products versus other industrial products are shown in Table 1.1 and Frame 1.1.

It should be noted that significant parts of advanced machinery as well
as of household machines and other products include embedded software
components (usually termed “firmware”) that are integrated into the product. These software components (the firmware) share the same
characteristics of the software products mentioned above. It follows that the
comparison shown above should actually be that of software products versus other industrial products and non-software components of industrial
products that include firmware. Hereinafter, when mentioning software, we
will mean software products as well as firmware.

The fundamental differences between the development and production
processes related to software products and those of other industrial products
warrant the creation of a different SQA methodology for software. The need
for special tools and methods for the software industry is reflected in the professional publications as well in special standards devoted to SQA, such as
ISO 9000-3, “Guidelines for the application of ISO 9001 to the development, supply and maintenance of software”. This point is supported by the fact
that targeted guidelines have not been prepared by ISO for other industries,
>_Perbedaan yang mempengaruhi deteksi cacat pada produk perangkat lunak dibandingkan produk industri lainnya ditunjukkan pada Tabel 1.1 dan Bingkai 1.1._
>
>_Perlu dicatat bahwa bagian penting dari mesin canggih juga
pada mesin rumah tangga dan produk lainnya termasuk perangkat lunak tertanam
komponen (biasanya disebut "firmware") yang terintegrasi ke dalam produk. Komponen perangkat lunak ini (firmware) berbagi hal yang sama
karakteristik produk perangkat lunak yang disebutkan di atas. Oleh karena itu,
perbandingan yang ditunjukkan di atas sebenarnya adalah produk perangkat lunak versus produk industri lainnya dan komponen non-perangkat lunak industri
produk yang menyertakan firmware. Selanjutnya, ketika menyebutkan perangkat lunak, kami
akan berarti produk perangkat lunak serta firmware._
>
>_Perbedaan mendasar antara pengembangan dan produksi
proses yang terkait dengan produk perangkat lunak dan produk industri lainnya
menjamin pembuatan metodologi SQA yang berbeda untuk perangkat lunak. Kebutuhan
untuk alat dan metode khusus untuk industri perangkat lunak tercermin dalam publikasi profesional serta dalam standar khusus yang ditujukan untuk SQA, seperti
ISO 9000-3, “Pedoman penerapan ISO 9001 untuk pengembangan, penyediaan dan pemeliharaan perangkat lunak”. Poin ini didukung oleh fakta
bahwa pedoman yang ditargetkan belum disiapkan oleh ISO untuk industri lain,_

and the only other targeted guidelines have been prepared for services (ISO
9004-2, “Quality management and quality systems elements: Guidelines for
the services”).
The great complexity as well as invisibility of software, among other
product characteristics, make the development of SQA methodology and its
successful implementation a highly professional challenge.
>_dan satu-satunya pedoman yang ditargetkan lainnya telah disiapkan untuk layanan (ISO
9004-2, “Manajemen mutu dan elemen sistem mutu: Pedoman untuk
pelayanan").
Kompleksitas besar serta ketidaktampakan perangkat lunak, antara lain
karakteristik produk, membuat pengembangan metodologi SQA dan
keberhasilan implementasi tantangan yang sangat profesional._

**1.2 The environments for which SQA methods are developed**

The software developed by many individuals and in different situations fulfills a variety of needs:
* Pupils and students develop software as part of their education.
* Software amateurs develop software as a hobby.
* Professionals in engineering, economics, management and other fields
develop software to assist them in their work, to perform calculations,
summarize research and survey activities, and so forth.
* Software development professionals (systems analysts and programmers)
develop software products or firmware as a professional career objective
while in the employment of software houses or by software development
and maintenance units (teams, departments, etc.) of large and small
industrial, financial and other organizations.
>_Perangkat lunak yang dikembangkan oleh banyak individu dan dalam situasi yang berbeda memenuhi berbagai kebutuhan:_
>* _Murid dan siswa mengembangkan perangkat lunak sebagai bagian dari pendidikan mereka._
>* _Software amatir mengembangkan software sebagai hobi._
>* _Profesional di bidang teknik, ekonomi, manajemen, dan bidang lainnya
mengembangkan perangkat lunak untuk membantu mereka dalam pekerjaan mereka, untuk melakukan perhitungan,
merangkum kegiatan penelitian dan survei, dan sebagainya._
>* _Profesional pengembangan perangkat lunak (analis sistem dan pemrogram)
mengembangkan produk perangkat lunak atau firmware sebagai tujuan karir profesional
saat bekerja di rumah perangkat lunak atau dengan pengembangan perangkat lunak
dan unit pemeliharaan (tim, departemen, dll.) besar dan kecil_

All those who participate in these activities are required to deal with software quality problems (“bugs”). However, quality problems in their most
severe form govern the professional software development.

This book is devoted, therefore, to defining and solving many of the software quality assurance (SQA) problems confronted by software development
and maintenance professionals. However, all other types of software developers can find portions of the book applicable to and recommended for their
own software development efforts.

Let us begin with the examination of the environment of professional software development and maintenance (hereafter “the SQA environment”), as it
is a major consideration in the development of SQA methodologies and their
implementation. The main characteristics of this environment are as follows:
>_Semua orang yang berpartisipasi dalam aktivitas ini diharuskan untuk menangani masalah kualitas perangkat lunak (“bug”). Namun, masalah kualitas di sebagian besar mereka
bentuk parah mengatur pengembangan perangkat lunak profesional.
>
>_Oleh karena itu, buku ini dikhususkan untuk mendefinisikan dan memecahkan banyak masalah jaminan kualitas perangkat lunak (SQA) yang dihadapi oleh pengembangan perangkat lunak.
dan profesional pemeliharaan. Namun, semua jenis pengembang perangkat lunak lainnya dapat menemukan bagian dari buku yang berlaku dan direkomendasikan untuk mereka
upaya pengembangan perangkat lunak sendiri._
>
>_Mari kita mulai dengan pemeriksaan lingkungan pengembangan dan pemeliharaan perangkat lunak profesional (selanjutnya disebut "lingkungan SQA"), karena
adalah pertimbangan utama dalam pengembangan metodologi SQA dan
penerapan. Ciri-ciri utama dari lingkungan ini adalah sebagai berikut:_

(1) Contractual conditions. As a result of the commitments and conditions
defined in the contract between the software developer and the customer,
the activities of software development and maintenance need to cope with:
* A defined list of functional requirements that the developed software
and its maintenance need to fulfill.
* The project budget.
* The project timetable.

The managers of software development and maintenance projects need
to invest a considerable amount of effort in the oversight of activities in
order to meet the contract’s requirements. 
>_(1) Kondisi kontrak. Sebagai hasil dari komitmen dan kondisi
didefinisikan dalam kontrak antara pengembang perangkat lunak dan pelanggan,
kegiatan pengembangan dan pemeliharaan perangkat lunak perlu mengatasi:_
>* _Daftar persyaratan fungsional yang ditentukan oleh perangkat lunak yang dikembangkan
dan pemeliharaannya harus dipenuhi._
>* _Anggaran proyek._
>* _Jadwal proyek._
>
>_Manajer proyek pengembangan dan pemeliharaan perangkat lunak membutuhkan
untuk menginvestasikan sejumlah besar upaya dalam pengawasan kegiatan di
untuk memenuhi persyaratan kontrak._

(2) Subjection to customer–supplier relationship. Throughout the process of
software development and maintenance, activities are under the oversight of the customer. The project team has to cooperate continuously
with the customer: to consider his request for changes, to discuss his criticisms about the various aspects of the project, and to get his approval
for changes initiated by the development team. Such relationships do not
usually exist when software is developed by non-software professionals.
>_(2) Tunduk pada hubungan pelanggan-pemasok. Sepanjang proses
pengembangan dan pemeliharaan perangkat lunak, kegiatan berada di bawah pengawasan pelanggan. Tim proyek harus bekerja sama terus menerus
dengan pelanggan: untuk mempertimbangkan permintaannya untuk perubahan, untuk mendiskusikan kritiknya tentang berbagai aspek proyek, dan untuk mendapatkan persetujuannya
untuk perubahan yang diprakarsai oleh tim pengembangan. Hubungan seperti itu tidak
biasanya ada ketika perangkat lunak dikembangkan oleh profesional non-perangkat lunak._

(3) Required teamwork. Three factors usually motivate the establishment of
a project team rather than assigning the project to one professional:
* Timetable requirements. In other words, the workload undertaken
during the project period requires the participation of more than one
person if the project is to be completed on time.
* The need for a variety of specializations in order to carry out the project.
* The wish to benefit from professional mutual support and review for
the enhancement of project quality.
>_(3) Diperlukan kerja sama tim. Tiga faktor biasanya memotivasi pembentukan:
tim proyek daripada menugaskan proyek ke satu profesional:_
>* _Persyaratan jadwal. Dengan kata lain, beban kerja yang dilakukan
selama periode proyek membutuhkan partisipasi lebih dari satu
orang jika proyek harus diselesaikan tepat waktu._
>* _Kebutuhan akan berbagai spesialisasi untuk melaksanakan proyek._
>* _Keinginan untuk mendapatkan keuntungan dari saling mendukung dan meninjau secara profesional untuk
peningkatan kualitas proyek._

(4) Cooperation and coordination with other software teams. The carryingout of projects, especially large-scale projects, by more than one team is
a very common event in the software industry. In these cases, cooperation may be required with:
* Other software development teams in the same organization.
* Hardware development teams in the same organization.
* Software and hardware development teams of other suppliers.
* Customer software and hardware development teams that take part

in the project’s development.
An outline of cooperation needs, as seen from the perspective of the
development team, is shown in Figure 1.1.
>_(4) Kerjasama dan koordinasi dengan tim perangkat lunak lain. Pelaksanaan proyek, terutama proyek skala besar, oleh lebih dari satu tim adalah
peristiwa yang sangat umum di industri perangkat lunak. Dalam kasus ini, kerjasama mungkin diperlukan dengan:_
>* _Tim pengembangan perangkat lunak lain dalam organisasi yang sama._
>* _Tim pengembangan perangkat keras dalam organisasi yang sama._
>* _Tim pengembangan perangkat lunak dan perangkat keras dari pemasok lain._
>* _Tim pengembangan perangkat lunak dan perangkat keras pelanggan yang ambil bagian_
>
>_dalam pengembangan proyek.
Garis besar kebutuhan kerjasama, dilihat dari sudut pandang
tim pengembang, ditunjukkan pada Gambar 1.1._

(5) Interfaces with other software systems. Nowadays, most software systems include interfaces with other software packages. These interfaces
allow data in electronic form to flow between the software systems, free
from keying in of data processed by the other software systems. One can
identify the following main types of interfaces:
* Input interfaces, where other software systems transmit data to your
software system.
* Output interfaces, where your software system transmits processed
data to other software systems.
* Input and output interfaces to the machine’s control board, as in medical and laboratory control systems, metal processing equipment, etc.

Salary processing software packages provide good examples of typical
input and output interfaces to other software packages – see Figure 1.2.
First let us look at the input interface. In order to calculate salaries, one
needs the employees’ attendance information, as captured by the time
>_(5) Antarmuka dengan sistem perangkat lunak lain. Saat ini, sebagian besar sistem perangkat lunak menyertakan antarmuka dengan paket perangkat lunak lain. Antarmuka ini
memungkinkan data dalam bentuk elektronik mengalir di antara sistem perangkat lunak, gratis
dari memasukkan data yang diproses oleh sistem perangkat lunak lain. Satu bisa
mengidentifikasi jenis antarmuka utama berikut:_
>* _Antarmuka input, tempat sistem perangkat lunak lain mengirimkan data ke
sistem perangkat lunak._
>* _Antarmuka keluaran, tempat sistem perangkat lunak Anda mentransmisikan proses
data ke sistem perangkat lunak lain._
>* _Antarmuka input dan output ke papan kontrol mesin, seperti dalam sistem kontrol medis dan laboratorium, peralatan pemrosesan logam, dll._
>
>_Paket perangkat lunak pengolah gaji memberikan contoh yang baik dari tipikal
antarmuka input dan output ke paket perangkat lunak lain – lihat Gambar 1.2.
Pertama mari kita lihat antarmuka input. Untuk menghitung gaji, satu
membutuhkan informasi kehadiran karyawan, seperti yang ditangkap oleh waktu_

clocks placed at the entrance to the office building and processed later
by the attendance control software system. Once a month, this information (the attendance lists including the overtime data) is transmitted
electronically from the attendance control system to the salary processing system. This information transmission represents an input interface
for the salary processing software system; at the same time it represents
an output interface to the attendance control system. Now, let us examine
the output interface of our system. One of the outputs of the salary
processing system is the list of “net” salaries, after deduction of the
income tax and other items, payable to the employees. This list, including
the employees’ bank account details, has to be sent to the banks. The
transmission of the list of salary payments is done electronically, representing an output interface for the salary processing system and an input
interface for the bank’s account system.
>_jam ditempatkan di pintu masuk gedung kantor dan diproses nanti
oleh sistem perangkat lunak kontrol kehadiran. Sebulan sekali, informasi ini (daftar kehadiran termasuk data lembur) dikirimkan
elektronik dari sistem kontrol kehadiran ke sistem pemrosesan gaji. Transmisi informasi ini mewakili antarmuka input
untuk sistem perangkat lunak pengolah gaji; pada saat yang sama itu mewakili
antarmuka output ke sistem kontrol kehadiran. Sekarang, mari kita periksa
antarmuka keluaran sistem kami. Salah satu output dari gaji
sistem pemrosesan adalah daftar gaji "bersih", setelah dikurangi
pajak penghasilan dan hal-hal lain yang harus dibayarkan kepada karyawan. Daftar ini, termasuk
rincian rekening bank karyawan, harus dikirim ke bank. Itu
transmisi daftar pembayaran gaji dilakukan secara elektronik, mewakili antarmuka output untuk sistem pemrosesan gaji dan input
antarmuka untuk sistem rekening bank._

(6) The need to continue carrying out a project despite team member
changes. It is quite common for team members to leave the team during
the project development period, whether owing to promotions to higher
level jobs, a switch in employers, transfers to another city, and so forth.
The team leader then has to replace the departing team member either
by another employee or by a newly recruited employee. No matter how
much effort is invested in training the new team member, “the show
must go on”, which means that the original project contract timetable
will not change. 
>_(6) Kebutuhan untuk terus melaksanakan proyek meskipun anggota tim
perubahan. Sangat umum bagi anggota tim untuk meninggalkan tim selama
periode pengembangan proyek, baik karena promosi ke yang lebih tinggi
pekerjaan tingkat, beralih majikan, transfer ke kota lain, dan sebagainya.
Pemimpin tim kemudian harus mengganti anggota tim yang pergi juga
oleh karyawan lain atau oleh karyawan yang baru direkrut. Bagaimanapun caranya
banyak upaya diinvestasikan dalam melatih anggota tim baru, "pertunjukan"
harus dilanjutkan”, yang berarti jadwal kontrak proyek asli
tidak akan berubah._

(7) The need to continue carrying out software maintenance for an extended period. Customers who develop or purchase a software system expect
to continue utilizing it for a long period, usually for 5–10 years. During
the service period, the need for maintenance will eventually arise. In
most cases, the developer is required to supply these services directly.
Internal “customers”, in cases where the software has been developed
in-house, share the same expectation regarding the software maintenance during the service period of the software system.
>_(7) Kebutuhan untuk terus melakukan pemeliharaan perangkat lunak untuk waktu yang lama. Pelanggan yang mengembangkan atau membeli sistem perangkat lunak mengharapkan
untuk terus menggunakannya untuk waktu yang lama, biasanya selama 5-10 tahun. Selama
masa layanan, kebutuhan akan pemeliharaan pada akhirnya akan muncul. Di
kebanyakan kasus, pengembang diharuskan untuk menyediakan layanan ini secara langsung.
“Pelanggan” internal, dalam kasus di mana perangkat lunak telah dikembangkan
in-house, berbagi harapan yang sama mengenai pemeliharaan perangkat lunak selama masa layanan sistem perangkat lunak._

The environmental characteristics create a need for intensive and continuous
managerial efforts parallel to the professional efforts that have to be invested in order to assure the project’s quality, in other words to assure the
project’s success.

A summary of the main characteristics of the SQA environment is shown
in Frame 1.2.

A significant amount of software as well as firmware development is not
carried out subject to formal contracts or formal customer–supplier relationships, as mentioned in the first two SQA environment characteristics. This
type of activity usually concerns software developed in-house for internal use
>_Karakteristik lingkungan menciptakan kebutuhan yang intensif dan berkesinambungan
upaya manajerial sejajar dengan upaya profesional yang harus diinvestasikan untuk menjamin kualitas proyek, dengan kata lain untuk menjamin
keberhasilan proyek._
>
>_Ringkasan karakteristik utama lingkungan SQA ditampilkan
di Bingkai 1.2._
>
>_Sejumlah besar perangkat lunak serta pengembangan firmware tidak
dilakukan dengan tunduk pada kontrak formal atau hubungan formal pelanggan-pemasok, sebagaimana disebutkan dalam dua karakteristik lingkungan SQA pertama. Ini
jenis aktivitas biasanya menyangkut perangkat lunak yang dikembangkan sendiri untuk penggunaan internal_

**Frame 1.2 Summary of the main characteristics of SQA environment**
1. Being contracted
2. Subjection to customer–supplier relationship
3. Requirement for teamwork
4. Need for cooperation and coordination with other development teams
5. Need for interfaces with other software systems
6. Need to continue carrying out a project while the team changes
7. Need to continue maintaining the software system for years
>_**Frame 1.2 Ringkasan karakteristik utama lingkungan SQA**_
>1. _Dikontrak_
>2. _Ketundukan pada hubungan pelanggan-pemasok_
>3. _Persyaratan untuk kerja tim_
>4. _Perlu kerjasama dan koordinasi dengan tim pengembangan lainnya_
>5. _Kebutuhan akan antarmuka dengan sistem perangkat lunak lain_
>6. _Perlu terus menjalankan proyek saat tim berubah_
>7. _Perlu terus memelihara sistem perangkat lunak selama bertahun-tahun_

or for marketing as software packages and in-house development of firmware. The relationships between the marketing department that initiates and
defines the qualifications of a new product and the respective in-house software development department often resemble a contract and customer–
supplier relationship. The same applies to internal requests for a new software system or for the upgrading of current software or firmware to be
implemented by the organization’s software department. Actual relationships between the internal “customers” and the development departments
are found to vary greatly when measured by a formal–informal scale. Some
managers claim that the closer the relationships to the formal form, the
greater the prospects for the project’s success. 
>_atau untuk pemasaran sebagai paket perangkat lunak dan pengembangan firmware internal. Hubungan antara departemen pemasaran yang memulai dan
mendefinisikan kualifikasi produk baru dan departemen pengembangan perangkat lunak internal masing-masing sering menyerupai kontrak dan pelanggan–
hubungan pemasok. Hal yang sama berlaku untuk permintaan internal untuk sistem perangkat lunak baru atau untuk meningkatkan perangkat lunak atau firmware saat ini menjadi
diimplementasikan oleh departemen perangkat lunak organisasi. Hubungan aktual antara "pelanggan" internal dan departemen pengembangan
ditemukan sangat bervariasi ketika diukur dengan skala formal-informal. Beberapa
manajer mengklaim bahwa semakin dekat hubungan dengan bentuk formal,
semakin besar prospek keberhasilan proyek._

## Summary

**(1) The uniqueness of software quality assurance.**

The fundamental differences between software products (including firmware) and
other products are caused by the higher product complexity, by the invisibility of
software and by the nature of the product development and production process.
These differences create the need for an SQA methodology and tools for SQA that
will meet the special and different challenges for the development and operation of
quality assurance for software. 
>_**(1) Keunikan jaminan kualitas perangkat lunak.**_
>
>_Perbedaan mendasar antara produk perangkat lunak (termasuk firmware) dan
produk lain disebabkan oleh kompleksitas produk yang lebih tinggi, oleh tembus pandang
perangkat lunak dan oleh sifat pengembangan produk dan proses produksi.
Perbedaan ini menciptakan kebutuhan akan metodologi dan alat SQA untuk SQA yang
akan memenuhi tantangan khusus dan berbeda untuk pengembangan dan pengoperasian
jaminan kualitas untuk perangkat lunak._

**(2) The environments for which SQA methods were developed.**

The SQA methods and tools discussed in this book are specially aimed at the needs
of professional software development and maintenance, activities where quality
problems appear in their most severe form, and where the most painful losses are
expected. Therefore any method or tool to be applied is subject to the environmental characteristics of their activities, namely:
* Contract conditions and commitments defining the contents and timetable.
* The conditions of the customer–supplier relationship, as realized by the need
for consultation with the customer and the acquisition of his approval.
* Teamwork requirements.
* Need for cooperation and coordination with other software and hardware development teams both internally and externally.
* Need for interfaces with other software systems.
* Need to continue carrying out a project when team members change.
* Need to conduct maintenance of the software system for several years.

These environmental characteristics also apply to internal development of software
and firmware, though only informal contract or informal customer–supplier relationships exist in these cases. These characteristics demand that intensive and
continuous managerial efforts be expended in parallel to the professional efforts
that have to be invested in order to ensure the project’s quality or, in other words,
to assure the project’s success.

>**_(2) Lingkungan di mana metode SQA dikembangkan._**
>
>_Metode dan alat SQA yang dibahas dalam buku ini secara khusus ditujukan untuk kebutuhan
pengembangan dan pemeliharaan perangkat lunak profesional, aktivitas di mana kualitas
masalah muncul dalam bentuk yang paling parah, dan di mana kerugian yang paling menyakitkan adalah
mengharapkan. Oleh karena itu metode atau alat apa pun yang akan diterapkan tunduk pada karakteristik lingkungan kegiatannya, yaitu:_
>* _Kondisi kontrak dan komitmen yang menentukan isi dan jadwal._
>* _Kondisi hubungan pelanggan-pemasok, sebagaimana diwujudkan oleh kebutuhan
untuk konsultasi dengan pelanggan dan perolehan persetujuannya._
>* _Persyaratan kerja tim._
>* _Perlu kerjasama dan koordinasi dengan tim pengembangan perangkat lunak dan perangkat keras lainnya baik internal maupun eksternal._
>* _Kebutuhan untuk antarmuka dengan sistem perangkat lunak lain._
>* _Perlu terus melaksanakan proyek ketika anggota tim berubah._
>* _Perlu melakukan pemeliharaan sistem perangkat lunak selama beberapa tahun._
>
>_Karakteristik lingkungan ini juga berlaku untuk pengembangan internal perangkat lunak
dan firmware, meskipun hanya kontrak informal atau hubungan pelanggan-pemasok informal yang ada dalam kasus ini. Sifat-sifat ini menuntut bahwa intensif dan
upaya manajerial yang berkelanjutan dikeluarkan secara paralel dengan upaya profesional
yang harus diinvestasikan untuk memastikan kualitas proyek atau, dengan kata lain,
untuk memastikan keberhasilan proyek._

## Review questions

1.1 There are three major differences between software products and other industrial
products.

1. Identify and describe the differences.

2. Discuss the ways in which these differences affect SQA.

1.2 It is claimed that no significant SQA activities are expected to take place during the
phase of production planning for software products.

1. Discuss this claim.

2. Compare the required production planning for a new automobile model with the
production planning efforts required for a new release of a software product.

1.3 Seven issues characterize the professional software development and maintenance environment.

1.  Identify and describe these characteristics.

2.  Which of these environmental characteristics mainly affect the professional
efforts required for carrying out software development and maintenance projects? List the characteristics and explain why a professional effort is needed.

3.  Which of these environmental characteristics mainly affect the managerial
efforts required for carrying out software development and maintenance projects? List the characteristics and explain why such efforts are needed.
>_1.1 Ada tiga perbedaan utama antara produk perangkat lunak dan industri lainnya
produk._
>
>1. _Identifikasi dan jelaskan perbedaannya._
>
>2. _Diskusikan bagaimana perbedaan ini mempengaruhi SQA._
>
>_1.2 Diklaim bahwa tidak ada kegiatan SQA yang signifikan yang diharapkan terjadi selama
tahap perencanaan produksi untuk produk perangkat lunak._
>
>1. _Diskusikan klaim ini._
>
>2. _Bandingkan perencanaan produksi yang diperlukan untuk model mobil baru dengan
upaya perencanaan produksi yang diperlukan untuk rilis baru produk perangkat lunak._
>
>_1.3 Tujuh masalah menjadi ciri lingkungan pengembangan dan pemeliharaan perangkat lunak profesional._
>
>1. _Identifikasi dan jelaskan ciri-ciri tersebut._
>
>2. _Manakah dari karakteristik lingkungan berikut yang paling mempengaruhi profesional?
upaya yang diperlukan untuk melaksanakan proyek pengembangan dan pemeliharaan perangkat lunak? Sebutkan ciri-ciri dan jelaskan mengapa upaya profesional diperlukan._
>
>3. _Manakah dari karakteristik lingkungan ini yang paling mempengaruhi manajerial?
upaya yang diperlukan untuk melaksanakan proyek pengembangan dan pemeliharaan perangkat lunak? Sebutkan ciri-ciri dan jelaskan mengapa upaya tersebut diperlukan._

## Topics for discussion

1.1 Educational systems are assumed to prepare the students to cope with real-life
conditions. Examine the procedural requirements of a software development project or final software project, and determine which of the requirements could be
considered as preparatory to professional life situations as discussed above. 
>_1.1 Sistem pendidikan diasumsikan mempersiapkan siswa untuk menghadapi kehidupan nyata
kondisi. Periksa persyaratan prosedural dari proyek pengembangan perangkat lunak atau proyek perangkat lunak akhir, dan tentukan persyaratan mana yang mungkin:
dianggap sebagai persiapan untuk situasi kehidupan profesional seperti yang dibahas di atas._

1.2 Referring to the seven environmental characteristics of software development and
121 The software quality challenge
maintenance, consider the characteristics of future software products, discussing
whether the professional and managerial burden of coping with these characteristics in future is expected to be higher or lower when compared with the current
performance of these activities. 
>_1.2 Mengacu pada tujuh karakteristik lingkungan pengembangan perangkat lunak dan
121 Tantangan kualitas perangkat lunak
pemeliharaan, pertimbangkan karakteristik produk perangkat lunak masa depan, diskusikan
apakah beban profesional dan manajerial untuk mengatasi karakteristik ini di masa depan diharapkan lebih tinggi atau lebih rendah jika dibandingkan dengan saat ini
kinerja kegiatan-kegiatan tersebut._

1.3 The interfaces of a salary processing system are exhibited in Figure 1.2.
1. Suggest what are the main benefits of applying computerized interfaces
instead of transferring printouts.
2. Give two additional examples where input interfaces are applied.
3. Give two additional examples where output interfaces are applied.
4. Suggest additional situations where the use of input and output interfaces is
not applied and should be recommended.
5. Would you advise all information transfers from one organization to another
be performed by computerized interface? Discuss the reasons behind your
answer
>_1.3 Antarmuka sistem pemrosesan gaji ditunjukkan pada Gambar 1.2._
>1. _Sarankan apa manfaat utama dari penerapan antarmuka terkomputerisasi
alih-alih mentransfer hasil cetak._
>2. _Berikan dua contoh tambahan di mana antarmuka input diterapkan._
>3. _Berikan dua contoh tambahan di mana antarmuka keluaran diterapkan._
>4. _Sarankan situasi tambahan di mana penggunaan antarmuka input dan output
tidak diterapkan dan harus direkomendasikan._
>5. _Apakah Anda menyarankan semua transfer informasi dari satu organisasi ke organisasi lain?
dilakukan oleh antarmuka terkomputerisasi? Diskusikan alasan di balik
menjawab_

1.4 The need to carry out work by a team demands additional investment in coordination of the team members. Discuss whether these managerial efforts could be
saved if the work were performed as a “one-man job”. 
>_1.4 Kebutuhan untuk melaksanakan pekerjaan oleh tim menuntut investasi tambahan dalam koordinasi anggota tim. Diskusikan apakah upaya manajerial ini dapat
diselamatkan jika pekerjaan itu dilakukan sebagai "pekerjaan satu orang"._

1.5 It is clear that a software development project carried out by a software house for
a specific customer is carried out under content and timetable obligations, and is
subject to the customer–supplier relationship.
1. Discuss whether a customer–supplier relationship is expected when the software developed is to be sold to the public as a software package.
2. Discuss whether a customer–supplier relationship is expected when software
is developed for in-house use, as in the case where a software development
department develops an inventory program for the company’s warehouses.
3. Some managers claim that the closer relationships are to a formal pattern, the
greater the prospects are for the project’s success. Discuss whether implementing customer–supplier relationships in the situations mentioned in (1)
and (2) are a benefit for the company (referring to the internal customer and
supplier) or an unnecessary burden to the development team.
>_1.5 Jelas bahwa proyek pengembangan perangkat lunak dilakukan oleh rumah perangkat lunak untuk
pelanggan tertentu dilakukan di bawah konten dan kewajiban jadwal, dan adalah
tunduk pada hubungan pelanggan-pemasok._
>1. _Diskusikan apakah hubungan pelanggan-pemasok diharapkan ketika perangkat lunak yang dikembangkan akan dijual kepada publik sebagai paket perangkat lunak._
>2. _Diskusikan apakah hubungan pelanggan-pemasok diharapkan ketika perangkat lunak
dikembangkan untuk penggunaan in-house, seperti dalam kasus di mana pengembangan perangkat lunak_
departemen mengembangkan program persediaan untuk gudang perusahaan.
>3. _Beberapa manajer mengklaim bahwa semakin dekat hubungan dengan pola formal,
semakin besar prospek untuk keberhasilan proyek. Diskusikan apakah menerapkan hubungan pelanggan-pemasok dalam situasi yang disebutkan dalam (1)
dan (2) merupakan keuntungan bagi perusahaan (mengacu pada pelanggan internal dan
pemasok) atau beban yang tidak perlu bagi tim pengembangan._

1.6 It has been claimed that environmental characteristics create the need for intensive and continuous managerial efforts parallel to the professional efforts that
have to be invested in order to ensure the project’s quality or, in other words, to
assure the project’s success. Discuss the reasons behind this claim, including an
analysis of the managerial effort created by each of the SQA environmental characteristics.
>_1.6 Telah diklaim bahwa karakteristik lingkungan menciptakan kebutuhan akan upaya manajerial yang intensif dan berkesinambungan sejajar dengan upaya profesional yang
harus diinvestasikan untuk memastikan kualitas proyek atau, dengan kata lain, untuk
menjamin keberhasilan proyek. Diskusikan alasan di balik klaim ini, termasuk
analisis upaya manajerial yang diciptakan oleh masing-masing karakteristik lingkungan SQA._