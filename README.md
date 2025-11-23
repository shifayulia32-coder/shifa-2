# Sistem Backup Otomatis
## Nama: Shifa yulia azizah
## Nim: 05301425023
## Kelas: A
## MK: Sistem Operasi

### Membuat folder baru
https://drive.google.com/file/d/1vVY0dEM6hZKcUxqrtWxMjZte9SNcmbpN/view?usp=drivesdk
### Masuk ke folder
https://drive.google.com/file/d/1ha9kI5RYRcx5g2XimIjieaLZkPJeUIVy/view?usp=drivesdk
### membuat file script bernama backup.sh
https://drive.google.com/file/d/1Zo-EhTtf0nYwD-mGCiNn619dMwh8hIKt/view?usp=drivesdk
```
!/bin/bash
SOURCE_DIR="/home/shifayulia/Desktop"

BACKUP_DIR="/home/shifayulia/backup1"

mkdir -p "$BACKUP_DIR"

TIMESTAMP=$(date +'%Y%m%d_%H%M%S')

BACKUP_FILE="backup_${TIMESTAMP}.tar.gz"

LOG_FILE="$BACKUP_DIR/backup.log"

FILES_TO_BACKUP=$(find "$SOURCE_DIR" -type f \( -name "*.pdf" -o -name "*.txt" \) -mtime -7)

if [ -z "$FILES_TO_BACKUP" ]; then
    echo "$TIMESTAMP - Tidak ditemukan file yang memenuhi kriteria backup." >> "$LOG_FILE"
    echo "Backup gagal: tidak ada file yang sesuai kriteria."
    exit 1
fi

tar -czf "$BACKUP_DIR/$BACKUP_FILE" $FILES_TO_BACKUP

if [ $? -eq 0 ]; then
    echo "$TIMESTAMP - Backup berhasil: $BACKUP_FILE dibuat." >> "$LOG_FILE"
    echo "Backup berhasil: $BACKUP_FILE"
else
    echo "$TIMESTAMP - Backup gagal." >> "$LOG_FILE"
    echo "Backup gagal."
    exit 1
fi


c.
```
### isi script:
https://drive.google.com/file/d/1vRlnre07KJF3YVghdyqRqcpmc8AEqHTn/view?usp=drivesdk

### mengubah izin file agar bisa dieksekusi
https://drive.google.com/file/d/1JvNpzjoDQsQik0GhcDeu88AfMYE1cwhy/view?usp=drivesdk
### menjalankan script backup
https://drive.google.com/file/d/1YgPyDdtKLVl1bFJRozRsqJAfYpzPsTQr/view?usp=drivesdk
