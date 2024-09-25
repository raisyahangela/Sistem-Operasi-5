# Praktikum Sistem Operasi - Job Control

### NAMA: Raisyah Mepa Angela  
### NIM: 09011282328033  
### KELAS: SK3C  
### MATA KULIAH: PRAKTIKUM SISTEM OPERASI  

## Tugas 1: Eksekusi seluruh profile yang ada

1. Edit file profile `/etc/profile` dan tampilkan pesan sebagai berikut:

    ```bash
    echo "Profile dari /etc/profile"
    ```

2. Asumsi nama anda `stD100201`, edit semua profile yang ada:

    ```bash
    /home/stD100201/.bash_profile  
    /home/.stD002001/.bash_login  
    /home/mahasiswa/.profile  
    /home/mahasiswa/.bashrc  
    ```

3. Ganti nama `home/mahasiswa` dengan nama anda sendiri. Pada setiap file tersebut, cantumkan instruksi `echo`, misalnya pada `/home/mahasiswa/.bash_profile`:

    ```bash
    echo "Profile dari .bash_profile"
    ```

   Gambar:
   ![Gambar 1](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/1.png)
   
4. Lakukan hal yang sama untuk file lainnya:
   
   Gambar:
   ![Gambar 2](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/2.png)
   ![Gambar 3](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/3.png)
   ![Gambar 4](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/4.png)

5. Jalankan instruksi substitute user, kemudian keluar dengan perintah:

    ```bash
    $ su mahasiswa  
    $ exit  
    $ su -- mahasiswa  
    $ exit
    ```

   Jelaskan perbedaan kedua utilitas tersebut.

## Tugas 2: Prompt String (PS)

1. Edit file `.bash_profile`, ganti prompt `PS1` dengan `/`:

    ```bash
    PS1='/'
    export PS1
    ```

## Tugas 3: Logout

1. Edit file `.bash_logout`, tampilkan pesan dan tahan selama 5 detik, sebelum eksekusi logout:

    ```bash
    echo "Terima kasih atas sesi yang diberikan"
    sleep 5
    clear
    ```

   Gambar:
   ![Gambar 5](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/5.png)

## Tugas 4: Bash Script

1. Buat 3 buah script `ps1.sh`, `ps2.sh`, `ps3.sh` dengan isi masing-masing:

    - `ps1.sh`
    
      ```bash
      #! /bin/bash
      echo "Program p1"
      ls -l
      ```

    - `ps2.sh`
    
      ```bash
      #! /bin/bash
      echo "Program P2"
      who
      ```

    - `ps3.sh`
    
      ```bash
      #! /bin/bash
      echo "Program p3"
      ps
      ```

   Gambar:
   ![Gambar 6](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/6.png)
   ![Gambar 7](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/7.png)

2. Jalankan script tersebut:

    ```bash
    $ ./ps1.sh ; ./ps3.sh ; ./ps2.sh  
    $ ./ps1.sh && ./ps2.sh && ./ps3.sh  
    $ ./ps1.sh & ./ps2.sh & ./ps3.sh &
    ```

   Gambar:
   ![Gambar 8](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/8.png)  
   ![Gambar 9](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/9.png)

## Tugas 5: Jobs

1. Buat shell-script `waktu.sh` yang melakukan loop setiap 10 detik, kemudian menyimpan tanggal dan jam pada file `hasil`:

    ```bash
    #! /bin/bash
    while [ true ]
    do
    date >> hasil
    sleep 10
    done
    ```

   Gambar:
   ![Gambar 10](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/10.png)

2. Jalankan sebagai background:

    ```bash
    $ jobs
    $ find / -print > files 2>/dev/null &  
    $ jobs
    ```

   Gambar:
   ![Gambar 11](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/11.png)

3. Jadikan program ke 1 sebagai foreground, tekan `^Z` dan kembalikan program tersebut ke background:

    ```bash
    $ fg %1  
    $ bg %1
    ```

   Gambar:
   ![Gambar 12](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/12.png)

4. Stop program background dengan utilitas `kill`:

    ```bash
    $ ps x  
    $ kill [Nomor PID]
    ```

## Tugas 6: History

1. Ganti nilai `HISTSIZE` dari 1000 menjadi 20:

    ```bash
    HISTSIZE=20
    ```

   Gambar:
   ![Gambar 13](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/13.png)  
   ![Gambar 14](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/14.png)  
   ![Gambar 15](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/15.png)

2. Gunakan fasilitas history:

    ```bash
    $ history  
    $ !5
    ```

   Gambar:
   ![Gambar 16](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/16.png)  
   ![Gambar 17](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/17.png)

3. Ulangi instruksi yang terakhir dengan navigasi `^P` dan `^N`, ulangi instruksi buffer nomor 150:

    ```bash
    ^P ^N  
    $ !150
    ```

   Gambar:
   ![Gambar 18](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/18.png)

4. Ulangi instruksi dengan prefix `ls`:

    ```bash
    $ !ls
    ```

   Gambar:
   ![Gambar 19](https://github.com/raisyahangela/Sistem-Operasi-5/blob/main/19.png)
