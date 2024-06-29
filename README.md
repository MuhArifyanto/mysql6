# Tugas Praktikum { Pertemuan ke 11 }

|**Nama**|**NIM**|**Kelas**|**Matkul**|
|----|---|-----|------|
|Muhammad Arif Mulyanto|312310359|TI.23.A.5|Basis Data|

# Soal Latihan Praktikum ( Pegawai )

![tugas 6 3](https://github.com/MuhArifyanto/mysql6/assets/147913440/7c1f768c-b4e1-4b7b-a1cf-c16f7bc90c4c)

**Perintah SQL :**

```
CREATE TABLE pegawai (
    idpegawai VARCHAR(5) PRIMARY KEY,
    nama_depan VARCHAR(10) NOT NULL,
    nama_belakang VARCHAR(15) NOT NULL,
    email VARCHAR(25) UNIQUE KEY,
    telepon VARCHAR(15),
    tgl_kontrak DATA,
    id_job VARCHAR(5),
    gaji INT,
    tunjangan INT
    );
INSERT INTO pegawai VALUES
    ('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
	('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
	('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
	('E004', 'Emna', 'Bunton', 'emna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
	('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
	('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);
```

***Output :***

![tugas 6 11](https://github.com/MuhArifyanto/mysql6/assets/147913440/e0af7d5b-cf5c-4e0d-ae7f-1eaeebb8f0aa)

## Tugas Praktikum

**1. Tampilkan pegawai yang gajinya bukan 2.000.000 dan 1.250.000 !**

```
SELECT*FROM pegawai WHERE gaji NOT IN (2000000, 1250000);
```

***Output :***

![tugas 6 12](https://github.com/MuhArifyanto/mysql6/assets/147913440/5a1dafa5-6ba7-40c3-a48a-517d35dea21d)

**2. Tampilkan pegawai yang tunjangannya NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NULL;
```

***Output :***

![tugas 6 13](https://github.com/MuhArifyanto/mysql6/assets/147913440/82536a75-0645-4bbe-92c2-0956323cd278)


**3. Tampilkan pegawai yang tunjangannya tidak NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NOT NULL;
```

***Output :***
![tugas 6 14](https://github.com/MuhArifyanto/mysql6/assets/147913440/ec1a04ee-7372-42d1-afe4-218898968521)


**4. Tampilkan/hitung jumlah baris/record tabel pegawai!**

```
SELECT COUNT(*) AS jmlh_pegawai FROM pegawai;
```

***Output :***
![tugas 6 15](https://github.com/MuhArifyanto/mysql6/assets/147913440/ef291f86-c6f8-4a73-91b8-b967a8f79e6b)


**5. Tampilkan/hitung jumlah total gaji di tabel pegawai!**

```
SELECT SUM(gaji) AS ttl_gaji FROM pegawai;
```

***Output :***

![tugas 6 16](https://github.com/MuhArifyanto/mysql6/assets/147913440/a6cd6656-d561-4fad-a34c-ad491f676712)


**6. Tampilkan/hitung rata-rata gaji pegawai!**

```
SELECT AVG(gaji) AS mean_gaji FROM pegawai;
```

***Output :***

![tugas 6 17](https://github.com/MuhArifyanto/mysql6/assets/147913440/83b6fe56-c2b7-4b51-b2dd-42f6941e91b5)


**7. Tampilkan gaji terkecil!**

```
SELECT MIN(gaji) AS terkecil FROM pegawai;
```

***Output :***

![tugas 6 18](https://github.com/MuhArifyanto/mysql6/assets/147913440/6cb58ef1-ff18-4408-b84d-55c268ca36b2)


**8. Tampilkan gaji terbesar!**

```
SELECT MAX(gaji) AS terbesar FROM pegawai;
```

***Output :***

![tugas 6 19](https://github.com/MuhArifyanto/mysql6/assets/147913440/d9267f08-b754-4410-8c54-0dca84201783)


# Soal Latihan Praktikum ( Hewan )

![tugas 6 2](https://github.com/MuhArifyanto/mysql6/assets/147913440/14a98f96-05b4-4d9f-8dbc-6c9e62331fa8)


**Perintah SQL :**

```
CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );
INSERT INTO hewan VALUES
    ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
    ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
    ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
    ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
    ('p5', 'Fang', 'Benny', 'Dog', 'M'),
    ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
    ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
    ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
    ('p9', 'Slim', 'Benny', 'Snake', 'M');
```

***Output :***

![tugas 6 4](https://github.com/MuhArifyanto/mysql6/assets/147913440/583aa326-e370-4838-92f2-5a54e0f23d46)

## Tugas Praktikum

**1. Tampilkan jumlah hewan yang dimiliki setiap owner.**

```
SELECT owner, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY owner;
```

***Output :***

![tugas 6 5](https://github.com/MuhArifyanto/mysql6/assets/147913440/0e367f85-5172-4ed2-ae0b-7b40a22debbd)


**2. Tampilkan jumlah hewan berdasarkan spesies**

```
SELECT species, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY species;
```

***Output :***

![tugas 6 6](https://github.com/MuhArifyanto/mysql6/assets/147913440/9caf8680-2fa1-4463-819c-9a16c740a9cb)


**3. Tampilkan jumlah hewan berdasarkan jenis kelamin**

```
SELECT sex, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY sex;
```

***Output :***

![tugas 6 7](https://github.com/MuhArifyanto/mysql6/assets/147913440/53ce52cf-6c73-4356-af84-6a760590d6cb)

**4. Tampilkan jumlah hewan berdasarkan spesies dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;
```

***Output :***

![tugas 6 8](https://github.com/MuhArifyanto/mysql6/assets/147913440/2355d709-b0b1-440e-b51a-d01d674a2288)

**5. Tampilkan jumlah hewan berdasarkan spesis (cat dan dog saja) dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE
species IN ('Cat', 'Dog')
GROUP BY species, sex;
```

***Output :***

![tugas 6 9](https://github.com/MuhArifyanto/mysql6/assets/147913440/fa364b11-3f30-4c21-80c8-cc31cee6f3f9)

**6. Tampilkan jumlah hewan berdasarkan jenis kelamin yang diketahui saja**

```
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

***Output :***

![tugas 6 10](https://github.com/MuhArifyanto/mysql6/assets/147913440/4e3ea2ac-5825-40f6-a488-2623847218df)

## Tulis semua perintah-perintah SQL percobaan di atas beserta outputnya!

```
CREATE DATABASE praktikum4;
USE praktikum4;
CREATE TABLE pegawai (
    idpegawai VARCHAR (5) PRIMARY KEY,
    nama_depan VARCHAR (10) NOT NULL,
    nama_belakang VARCHAR (15) NOT NULL,
    email VARCHAR (25) UNIQUE KEY,
    telepon VARCHAR (15),
    tgl_kontrak DATE,
    id_job VARCHAR (5),
    gaji INT,
    tunjangan INT
    );
INSERT INTO pegawai VALUES
    ('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
	('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
	('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
	('E004', 'Emna', 'Bunton', 'emna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
	('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
	('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);
SELECT * FROM pegawai;
SELECT * FROM pegawai WHERE gaji NOT IN (2000000, 1250000);
SELECT * FROM pegawai WHERE tunjangan IS NULL;
SELECT * FROM pegawai WHERE tunjangan IS NOT NULL;
SELECT COUNT(*) AS jumlah_pegawai FROM pegawai;
SELECT SUM(gaji) AS total_gaji FROM pegawai;
SELECT AVG(gaji) AS rata_rata_gaji FROM pegawai;
SELECT MIN(gaji) AS gaji_terkecil FROM pegawai;
SELECT MAX(gaji) AS gaji_terbesar FROM pegawai;
CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );
INSERT INTO hewan (id, name, owner, species, sex)
VALUES ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
       ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
       ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
       ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
       ('p5', 'Fang', 'Benny', 'Dog', 'M'),
       ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
       ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
       ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
       ('p9', 'Slim', 'Benny', 'Snake', 'M');
SELECT * from hewan;
SELECT owner, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY owner;
SELECT species, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species;
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY sex;
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE species IN ('Cat', 'Dog') GROUP BY species, sex;
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

## Berikan Kesimpulan Anda !

Terdapat beberapa ***Query Filter*** yang ditemukan pada tugas praktikum 4 :

Penggunaan operator, fungsi agregat, dan klausa pengelompokan dalam SQL sangat penting untuk memanipulasi dan menganalisis data secara efektif. Operator IN dan NOT IN memfilter data berdasarkan daftar nilai, 
sementara operator IS NULL dan IS NOT NULL memfilter berdasarkan keberadaan nilai NULL. Fungsi agregat seperti COUNT, SUM, AVG, MIN, dan MAX membantu dalam melakukan perhitungan pada kolom data.
Klausa GROUP BY memungkinkan pengelompokan data berdasarkan kolom tertentu, memudahkan dalam analisis data yang lebih kompleks. 
Dengan memahami dan menggunakan perintah-perintah ini, pengguna dapat melakukan query yang lebih efisien dan mendapatkan wawasan yang lebih mendalam dari data mereka.
