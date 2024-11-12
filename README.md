```
ansible-project/
├── ansible.cfg              # File konfigurasi Ansible
├── hosts.ini                # File inventory, bisa diberi nama sesuai kebutuhan
├── group_vars/              # Variabel untuk grup host
│   ├── all.yml              # Variabel untuk semua host
│   └── my_servers.yml       # Variabel khusus untuk grup `my_servers`
├── host_vars/               # Variabel untuk host individual
│   └── 192.168.1.10.yml     # Variabel untuk IP tertentu
├── roles/                   # Tempat untuk menyimpan roles Ansible
│   └── common/              # Contoh role bernama "common"
│       ├── tasks/           # Tugas dalam role "common"
│       │   └── main.yml     # File tugas utama
│       ├── handlers/        # Handlers untuk role ini
│       │   └── main.yml
│       ├── templates/       # Template file .j2 untuk Jinja2
│       ├── files/           # File statis untuk role ini
│       ├── vars/            # Variabel khusus untuk role ini
│       └── defaults/        # Default variabel untuk role ini
├── playbooks/               # Direktori untuk semua playbook
│   ├── setup.yml            # Contoh playbook setup
│   └── deploy.yml           # Contoh playbook untuk deployment
└── files/                   # File statis umum untuk semua playbook
    └── example.conf         # Contoh file konfigurasi
```

## Penjelasan Folder

- ansible.cfg: File konfigurasi utama untuk Ansible. Di sini Anda bisa mengatur lokasi inventory, mengatur remote_user, dan mengkonfigurasi opsi lainnya.

- hosts.ini: Inventory file utama, berisi daftar host dan grup yang Anda kelola dengan Ansible.

- group_vars/: Direktori untuk variabel tingkat grup. File dalam direktori ini menyimpan variabel yang berlaku untuk grup host tertentu (misalnya, my_servers.yml untuk grup my_servers).

- host_vars/: Direktori untuk variabel tingkat host individual. File dalam direktori ini menyimpan variabel yang spesifik untuk host tertentu berdasarkan alamat IP atau nama host.

- roles/: Direktori untuk role Ansible, yang merupakan cara terstruktur untuk mengelompokkan tugas, variabel, template, dan file yang diperlukan untuk mencapai tujuan tertentu, seperti instalasi software atau konfigurasi sistem.

- playbooks/: Tempat untuk playbook Ansible. Setiap playbook dapat berisi urutan tugas untuk dikerjakan pada satu atau lebih host.

- files/: Tempat untuk file statis atau berkas konfigurasi yang digunakan oleh playbook atau role secara umum. Anda bisa menggunakan files/ dalam role untuk file khusus role.
