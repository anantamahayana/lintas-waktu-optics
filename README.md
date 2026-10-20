# Lintas Waktu Optics Lab (`lintas-waktu-optics`)

**AI Depth & Subject Alpha Matting + Spatially-Varying Optical Lens Simulator** untuk workflow **Capture One & Adobe Lightroom** pada **Lintas Waktu Visual** (`lintaswaktuvisual.com`).

## ✨ Fitur Utama (Engine v1.0 AI)

1. **Real On-Device Neural Networks (100% Gratis, Tanpa API Key):**
   * **AI Subject & Hair Alpha Matting (`briaai/RMBG-1.4`):** Memisahkan subjek manusia, gaun pengantin, jas, dan helai rambut secara presisi.
   * **AI Monocular 3D Depth Estimation (`Depth-Anything-V2-Small`):** Menghitung peta kedalaman 3D sesungguhnya sehingga ketajaman lantai di kaki subjek menyambung alami (*ground-plane continuity*) dan ukuran *Circle of Confusion (CoC)* membesar secara bertahap sesuai jarak objek.
2. **Multi-Plane Background Inpainting (Anti-Halo / Tidak Terlihat Tempelan):**
   * Sebelum latar belakang di-blur oleh shader optik, area subjek pada layer latar belakang dihapus/di-ekstrapolasi keluar (*boundary inpainting*). Hal ini mencegah warna pakaian/kulit subjek bocor (*bleeding*) ke bola-bola bokeh di belakangnya.
3. **Simulasi Karakteristik Lensa Klasik & Sinema (WebGL2 SV-PSF Shader):**
   * **Helios 44-2 58mm f/2:** Pusaran bokeh tangensial (*Swirly Bokeh*) + *Cat-Eye mechanical vignetting* di sudut frame.
   * **Lomography Petzval 85mm f/2.2:** Pusaran vortex ekstrem di tepi frame dengan ketajaman kristal di tengah.
   * **Cooke / Atlas Orion Anamorphic 2.0x:** Bokeh lonjong vertikal (*Oval Squeeze*) khas lensa sinema.
   * **Meyer-Optik Trioplan 100mm f/2.8:** Profil aberasi sferis *Soap-Bubble Ring* (cincin tepi bokeh yang tegas).
   * **Contax 645 Planar 80mm f/2:** Transisi kedalaman *Medium Format* yang sangat lembut (*Creamy Bokeh*).
4. **Linear HDR Specular Highlight Extraction + Organic Film Grain:**
   * Mengonversi piksel ke ruang cahaya **Linear HDR** sebelum konvolusi sehingga celah cahaya di pepohonan atau lampu otomatis mengembang menjadi bola bokeh (*Bokeh Balls*) asli—bukan stiker overlay tempelan.
   * Menambahkan *Organic Sensor Grain* pada area blur agar tekstur bokeh menyatu dengan *grain* kamera asli.

---

## 🔗 Live Cloud Studio (Zero Local Storage)

Buka langsung di browser:
👉 **[https://anantamahayana.github.io/lintas-waktu-optics/](https://anantamahayana.github.io/lintas-waktu-optics/)**

---

## 🖥️ Integrasi dengan Capture One & Lightroom (Windows)

Untuk memanggil **Lintas Waktu Optics** langsung dari **Capture One** atau **Lightroom Classic** melalui klik kanan **`Edit With...`**:
1. Pilih foto klien (misalnya yang sudah ditandai **Rating 5 / Label Green** oleh `.xmp` dari galeri klien Lintas Waktu).
2. Klik kanan $\rightarrow$ **Edit With** $\rightarrow$ pilih aplikasi/launcher **Lintas Waktu Optics**.
3. Atur karakter lensa (*Swirl*, *Anamorphic*, *Cat-Eye*, *Focus Plane*) dan simpan kembali ke folder sesi Capture One.
