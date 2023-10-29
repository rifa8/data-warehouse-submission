## Task Part 4 - Google Cloud Storage

### 1. Buat sebuah bucket di GCS, upload beberapa file ke bucket tersebut!
#### 1) Cari 'bucket' di kotak pencarian lalu pilih 'Buckets'
![search-bucket](ss/search_bucket.png)

#### 2) Pilih create
![create](ss/create_bucket.png)

#### 3) Beri nama, lalu continue
![name](ss/name_bucket.png)

#### 4) Lengkapi semua data yang lain, lalu create
![create](ss/create_bucket_2.png)

#### 5) Bucket berhasil dibuat
![created](ss/created.png)

#### 6) Pilih upload files
![upload](ss/upload.png)

#### 7) Files berhasil diupload
![uploaded](ss/uploaded.png)

### 2. Hapus file yang sudah diupload!
#### 1) Select all rows untuk memilih semua file lalu pilih delete
![select-all](ss/select.png)

#### 2) Confirm delete
![confirm-delete](ss/confirm_delete.png)

#### 3) File berhasil dihapus
![deleted](ss/deleted.png)

### 3. Lakukan eksplorasi sample data [wikipedia](https://console.cloud.google.com/bigquery?p=bigquery-public-data&d=samples&t=wikipedia&page=table) dengan menggunakan big query!
#### 1) Masuk ke [link](https://console.cloud.google.com/bigquery?p=bigquery-public-data&d=samples&t=wikipedia&page=table) lalu buka query
![untitled](ss/untitled.png)

#### 2) Jalankan beberapa query
```
select count(1) from `bigquery-public-data.samples.wikipedia`;
```
![count](ss/count.png)

```
select * from `bigquery-public-data.samples.wikipedia` limit 10;
```
![query-2](ss/query_2.png)

```
select title, num_characters from `bigquery-public-data.samples.wikipedia`
where id > 999999
order by num_characters desc
limit 5;
```
![query-3](ss/query_3.png)

```
select title, num_characters from `bigquery-public-data.samples.wikipedia`
where title like '%indonesia%'
and num_characters between 10 and 100
and length(title) < 20
order by num_characters desc
limit 5;
```
![query-4](ss/query_4.png)

### 4. Munculkan jumlah kontribusi dari masing-masing contributor_ip, urutkan dari kontribusi terbesar ke kontribusi terkecil!
```
select contributor_ip, count(*) as jumlah_kontribusi
from `bigquery-public-data.samples.wikipedia`
group by contributor_ip
order by jumlah_kontribusi desc;
```
![jumlah-kontribusi](ss/jumlah_kontribusi.png)
