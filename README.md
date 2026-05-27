# TKA_B10_Modul-5-Cloudsim-dan-Load-Balancing
## TokoKita

### Struktur Folder
~~~
TokoKita/
├── backend1/
│   ├── Dockerfile
│   ├── main.py
│   └── requirements.txt
├── backend2/
│   ├── Dockerfile
│   ├── main.py
│   └── requirements.txt
├── nginx/
│   ├── Dockerfile
│   └── nginx.conf
└── docker-compose.yml
~~~

### Cara Menjalankan

### 1. Build dan jalankan semua container
\`\`\`bash
docker-compose up --build
\`\`\`

## 2. Pengujian

### Akses Load Balancer (NGINX)
Buka browser dan akses: http://localhost

Refresh beberapa kali. Pola yang muncul seharusnya:
- Refresh 1 → Server 1 - TokoKita
- Refresh 2 → Server 1 - TokoKita
- Refresh 3 → Server 1 - TokoKita
- Refresh 4 → Server 2 - TokoKita
(pola 3:1 sesuai weight)

### 3. Akses Endpoint Produk

http://localhost/products

Akan menampilkan data produk dalam format JSON:
```
[
  {"id": 1, "name": "Laptop", "price": 12000000},
  {"id": 2, "name": "Mouse", "price": 150000},
  {"id": 3, "name": "Keyboard", "price": 350000}
]
```
