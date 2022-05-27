# RFM-Analysis

## Overview
RFM adalah singkatan dari **Recency, Frequency, dan Monetary value**, masing-masing sesuai dengan beberapa sifat pelanggan utama. Metrik RFM ini adalah indikator penting dari perilaku pelanggan karena frekuensi dan nilai moneter memengaruhi nilai umur pelanggan, dan keterkinian memengaruhi retensi, ukuran keterlibatan.

Bisnis yang tidak memiliki aspek moneter, seperti jumlah penayangan, jumlah pembaca, atau produk yang berorientasi pada penjelajahan, dapat menggunakan parameter Keterlibatan daripada yang Moneter. Ini menghasilkan penggunaan **RFE (Recency, Frequency, Engagement)** - variasi RFM. Lebih lanjut, parameter Keterlibatan ini dapat didefinisikan sebagai nilai gabungan berdasarkan metrik seperti rasio pentalan, durasi kunjungan, jumlah halaman yang dikunjungi, waktu yang dihabiskan per halaman, dll.

Fitur RFM pelanggan menggambarkan karakteristik berikut:

- Semakin baru mereka membeli, semakin responsif mereka terhadap promosi.
- Semakin sering mereka membeli, semakin terlibat dan puas.
- Semakin banyak nilai uang membantu membedakan pembelanja tinggi vs pembelanjaan rendah.

Fokus pembahasan ini adalah melakukan proses pemodelan dan analisis RFM berdasarkan perilaku transaksi para pelanggannya.

## Dataset
Dataset yang digunakan adalah data pesanan pelanggan dari e-commerce asal Brazil yaitu Olist Store. Dataset ini berisi 100.000 data dari tahun 2016-2018 yang dihimpun dari beberapa pasar yang ada di Brazil. Dataset yang digunakan dapat Anda download di link ini https://www.kaggle.com/olistbr/brazilian-ecommerce.

Terdapat 3 file yang digunakan antara lain:
1. `olist_customers_dataset.csv` berisi informasi tentang pelanggan dan lokasinya.
    - customer_id : key to the orders dataset, each order has a unique customer_id
    - customer_unique_id : unique identifier of a customer
    - customer_zip_code_prefix : first five digits of customer zip code
    - customer_city : customer city name
    - customer_state : customer state
    
2. `olist_orders_dataset.csv` berisi informasi tentang pesanan pelanggan.   
    - order_id : unique identifier of the order
    - customer_id : key to the customer dataset. Each order has a unique customer_id
    - order_status : reference to the order status (delivered, shipped, etc)
    - order_purchase_timestamp : shows the purchase timestamp
    - order_approved_at : shows the payment approval timestamp
    - order_delivered_carrier_date : shows the order posting timestamp. When it was handled to the logistic partner
    - order_delivered_customer_date : shows the actual order delivery date to the customer
    - order_estimated_delivery_date : shows the estimated delivery date that was informed to customer at the purchase moment   
    
3. `olist_order_items_dataset.csv` berisi informasi barang dalam setiap pesanan.
    - order_id : order unique identifier
    - order_item_id : sequential number identifying number of items included in the same order
    - product_id : product unique identifier
    - seller_id : seller unique identifier
    - shipping_limit_date : shows the seller shipping limit date for handling the order over to the logistic partner
    - price : item price
    - freight_value : item freight value item (if an order has more than one item the freight value is splitted between items)