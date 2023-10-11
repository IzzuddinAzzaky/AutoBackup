#!/bin/bash

# Nama folder sumber
folder_sumber="sumber"

# Nama folder tujuan berdasarkan tanggal dan waktu
folder_tujuan="backup_$(date +\%Y\%m\%d_\%H\%M)"

# Nama file zip dengan format yang sesuai
nama_file_zip="${folder_sumber}_$(date +\%Y\%m\%d_\%H\%M).zip"

# Buat folder tujuan
mkdir -p "$folder_tujuan"

# Lakukan backup folder sumber
tar -czvf "$folder_tujuan/$nama_file_zip" "$folder_sumber"

echo "Backup selesai: $nama_file_zip"
