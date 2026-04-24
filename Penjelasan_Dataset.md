## Daftar Fitur Dataset `diabetic_data.csv`

Dataset ini berisi **101.766 baris** dan **50 kolom** dari catatan rawat inap pasien diabetes di 130 rumah sakit AS (1999-2008).

---

## Kolom Identitas (Tidak dipakai untuk model)

| No | Nama Kolom | Terjemahan | Tipe | Keterangan |
|----|-----------|------------|------|------------|
| 1 | `encounter_id` | ID Kunjungan | Numerik | Identifikasi unik setiap kunjungan rawat inap |
| 2 | `patient_nbr` | Nomor Pasien | Numerik | Identifikasi unik pasien |

---

## Kolom Fitur Demografis

| No | Nama Kolom | Terjemahan | Tipe | Nilai |
|----|-----------|------------|------|-------|
| 3 | `race` | Ras | Kategorikal | Caucasian, AfricanAmerican, Hispanic, Asian, Other, ? |
| 4 | `gender` | Jenis Kelamin | Kategorikal | Female, Male, Unknown/Invalid |
| 5 | `age` | Rentang Usia | Kategorikal | [0-10), [10-20), ..., [90-100) (per kelompok 10 tahun) |

---

## Kolom Fitur Informasi Rawat Inap

| No | Nama Kolom | Terjemahan | Tipe | Keterangan |
|----|-----------|------------|------|------------|
| 6 | `weight` | Berat Badan | Kategorikal | Rentang berat dalam pon (>40% missing, biasanya dihapus) |
| 7 | `admission_type_id` | ID Tipe Masuk | Numerik | 1=Emergency, 2=Urgent, 3=Elective, 4=Newborn, dll. |
| 8 | `discharge_disposition_id` | ID Disposisi Pulang | Numerik | 1=Pulang ke rumah, 3=Pindah RS, 6=Meninggal, 11=Expired, dll. |
| 9 | `admission_source_id` | ID Sumber Masuk | Numerik | 1=Rujukan dokter, 2=Klinik, 7=UGD, dll. |
| 10 | `time_in_hospital` | Lama Rawat Inap (hari) | Numerik | Integer 1-14 hari |
| 11 | `payer_code` | Kode Pembayar | Kategorikal | MC=Medicare, MD=Medicaid, BC=Blue Cross, dll. |
| 12 | `medical_specialty` | Spesialisasi Medis | Kategorikal | Spesialisasi dokter penerima (>49% missing, biasanya dihapus) |

---

## Kolom Fitur Prosedur & Pengobatan

| No | Nama Kolom | Terjemahan | Tipe | Keterangan |
|----|-----------|------------|------|------------|
| 13 | `num_lab_procedures` | Jumlah Prosedur Lab | Numerik | Berapa tes lab yang dilakukan |
| 14 | `num_procedures` | Jumlah Prosedur Non-Lab | Numerik | Prosedur selain lab (operasi, radiologi, dll.) |
| 15 | `num_medications` | Jumlah Obat | Numerik | Total obat generik yang diberikan |
| 16 | `number_outpatient` | Jumlah Kunjungan Rawat Jalan | Numerik | Kunjungan rawat jalan dalam 1 tahun sebelum rawat inap ini |
| 17 | `number_emergency` | Jumlah Kunjungan Darurat | Numerik | Kunjungan UGD dalam 1 tahun sebelumnya |
| 18 | `number_inpatient` | Jumlah Rawat Inap Sebelumnya | Numerik | Kunjungan rawat inap dalam 1 tahun sebelumnya |

---

## Kolom Fitur Diagnosis (Kode ICD-9)

| No | Nama Kolom | Terjemahan | Tipe | Keterangan |
|----|-----------|------------|------|------------|
| 19 | `diag_1` | Diagnosis Utama | Kategorikal | Kode ICD-9 diagnosis primer (misal 250.xx=Diabetes) |
| 20 | `diag_2` | Diagnosis Sekunder | Kategorikal | Kode ICD-9 diagnosis kedua |
| 21 | `diag_3` | Diagnosis Tambahan | Kategorikal | Kode ICD-9 diagnosis ketiga |
| 22 | `number_diagnoses` | Jumlah Diagnosis | Numerik | Total diagnosis yang tercatat (1-16) |

---

## Kolom Fitur Hasil Tes

| No | Nama Kolom | Terjemahan | Tipe | Keterangan |
|----|-----------|------------|------|------------|
| 23 | `max_glu_serum` | Kadar Glukosa Serum Maks | Kategorikal | Hasil tes glukosa: None, Norm, >200, >300 (~95% missing) |
| 24 | `A1Cresult` | Hasil A1C (HbA1c) | Kategorikal | Hasil tes HbA1c: None, Norm, >7, >8 (~83% missing) |

---

## Kolom Fitur Obat Diabetes (23 kolom obat)

Setiap kolom menunjukkan apakah dosis obat tersebut **berubah** selama rawat inap.

**Nilai:** `No` (tidak diresepkan), `Steady` (dosis tetap), `Up` (dosis naik), `Down` (dosis turun)

| No | Nama Kolom | Terjemahan / Jenis Obat | Golongan |
|----|-----------|------------------------|----------|
| 25 | `metformin` | Metformin | Biguanida |
| 26 | `repaglinide` | Repaglinide | Meglitinida |
| 27 | `nateglinide` | Nateglinide | Meglitinida |
| 28 | `chlorpropamide` | Klorpropamida | Sulfonilurea |
| 29 | `glimepiride` | Glimepiride | Sulfonilurea |
| 30 | `acetohexamide` | Asetoheksamida | Sulfonilurea |
| 31 | `glipizide` | Glipizide | Sulfonilurea |
| 32 | `glyburide` | Glyburide | Sulfonilurea |
| 33 | `tolbutamide` | Tolbutamida | Sulfonilurea |
| 34 | `pioglitazone` | Pioglitazone | Thiazolidinedione |
| 35 | `rosiglitazone` | Rosiglitazone | Thiazolidinedione |
| 36 | `acarbose` | Acarbose | Penghambat Alfa-Glukosidase |
| 37 | `miglitol` | Miglitol | Penghambat Alfa-Glukosidase |
| 38 | `troglitazone` | Troglitazone | Thiazolidinedione |
| 39 | `tolazamide` | Tolazamide | Sulfonilurea |
| 40 | `examide` | Examide | - (hampir selalu "No") |
| 41 | `citoglipton` | Citoglipton | - (hampir selalu "No") |
| 42 | `insulin` | Insulin | Insulin |
| 43 | `glyburide-metformin` | Glyburide-Metformin | Kombinasi |
| 44 | `glipizide-metformin` | Glipizide-Metformin | Kombinasi |
| 45 | `glimepiride-pioglitazone` | Glimepiride-Pioglitazone | Kombinasi |
| 46 | `metformin-rosiglitazone` | Metformin-Rosiglitazone | Kombinasi |
| 47 | `metformin-pioglitazone` | Metformin-Pioglitazone | Kombinasi |

---

## Kolom Fitur Ringkasan Pengobatan

| No | Nama Kolom | Terjemahan | Tipe | Keterangan |
|----|-----------|------------|------|------------|
| 48 | `change` | Perubahan Obat | Kategorikal | `Ch` = ada perubahan obat diabetes, `No` = tidak ada |
| 49 | `diabetesMed` | Obat Diabetes Diresepkan | Kategorikal | `Yes` = diresepkan, `No` = tidak |

---

## LABEL / TARGET KLASIFIKASI

| No | Nama Kolom | Terjemahan | Tipe | Nilai |
|----|-----------|------------|------|-------|
| **50** | **`readmitted`** | **Status Masuk Kembali** | **Kategorikal** | **`NO`** = tidak masuk kembali, **`<30`** = masuk kembali dalam <30 hari, **`>30`** = masuk kembali setelah >30 hari |

> [!IMPORTANT]
> **`readmitted` adalah LABEL (target) untuk klasifikasi.** Kolom ini menunjukkan apakah pasien masuk kembali ke rumah sakit setelah dipulangkan.
> 
> - **3 kelas (multiclass):** `NO`, `<30`, `>30`
> - **2 kelas (binary):** Bisa dikonversi menjadi `Readmitted` vs `Tidak Readmitted` dengan menggabungkan `<30` dan `>30`

---

## Ringkasan Tipe Kolom

| Kategori | Jumlah | Keterangan |
|----------|--------|------------|
| ID (tidak dipakai) | 2 | encounter_id, patient_nbr |
| Fitur Numerik | 11 | admission_type_id, time_in_hospital, num_lab_procedures, dll. |
| Fitur Kategorikal | 36 | race, gender, age, obat-obatan, diagnosis, dll. |
| **Label/Target** | **1** | **readmitted** |
| **Total** | **50** | |
