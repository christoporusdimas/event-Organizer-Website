# Diagram Proposal Clic Organizer

Berikut adalah beberapa diagram yang merepresentasikan struktur dan alur dari website Clic Organizer yang telah dibuat. Diagram ini dapat digunakan untuk kebutuhan proposal teknis maupun pengembangan.

## 1. Diagram Sitemap (Struktur Website)
Diagram ini menggambarkan struktur konten yang ada pada Landing Page (Single Page Application).

```mermaid
mindmap
  root((Clic Organizer<br/>Website))
    Header/Navigasi
      Beranda
      Layanan
      Keunggulan
      Tentang
      Galeri
      Konsultasi (CTA)
    Hero Section
      Visual Utama
      Headline
      CTA: Mulai Konsultasi
      CTA: Lihat Portofolio
    Layanan
      The Perfect Wedding
      Strategic Corporate Events
      Social Celebrations
    Keunggulan (Why Us)
      Tim Profesional
      Perhatian Detail
      Jaringan Vendor
    Tentang Kami
      Filosofi
      Pengalaman (7+ Tahun)
    Alur Kerja (Process)
      1. Discovery & Briefing
      2. Planning & Sourcing
      3. Execution & Control
    Testimoni
      Review Klien
    Portofolio
      Galeri Foto Event
    Footer
      Quick Links
      Copyright
```

## 2. Diagram Alur Pengguna (User Flow)
Diagram ini menggambarkan perjalanan pengguna (user journey) saat mengunjungi website hingga melakukan aksi konversi (menghubungi via WhatsApp).

```mermaid
%%{ init: { 'flowchart': { 'curve': 'linear' } } }%%
flowchart TD
    Start([Mulai: User Mengunjungi Website]) --> Hero[Tampilan Hero Section]
    
    Hero --> Choice{Apa aksi user?}
    
    %% Alur Navigasi & Scroll
    Choice -- "Scroll/Navigasi" --> Explore[Eksplorasi Halaman]
    Explore --> Section{Pilih Bagian}
    Section -- "Lihat Layanan" --> Services[Bagian Services]
    Section -- "Lihat Why Us" --> WhyUs[Bagian Keunggulan]
    Section -- "Lihat Galeri" --> Portfolio[Bagian Portofolio]
    
    Services --> Interest{Tertarik?}
    WhyUs --> Interest
    Portfolio --> Interest
    
    Interest -- "Belum" --> Explore
    Interest -- "Ya" --> CTA[Klik Tombol CTA / WhatsApp]

    %% Alur Langsung
    Choice -- "Klik CTA Utama" --> CTA
    
    %% Proses Konversi
    CTA --> System{Buka WhatsApp?}
    System -- "Mobile/Web" --> WARedirect[Redirect ke API WhatsApp]
    WARedirect --> Chat[Template Pesan Terisi]
    Chat --> Send([User Mengirim Pesan])
    
    Send --> End([Selesai: Konversi Berhasil])
```

## 3. Diagram Alur Bisnis (Process Flow)
Diagram ini menggambarkan "3 Langkah Menuju Kesuksesan" yang dijelaskan dalam konten website, relevan untuk proposal bisnis.

```mermaid
sequenceDiagram
    participant Client
    participant ClicOrganizer
    
    Note over Client, ClicOrganizer: Tahap 1: Discovery & Briefing
    Client->>ClicOrganizer: Konsultasi Visi & Budget
    ClicOrganizer-->>Client: Rancangan Kerangka Awal
    
    Note over Client, ClicOrganizer: Tahap 2: Planning & Sourcing
    ClicOrganizer->>ClicOrganizer: Susun Timeline & Pilih Vendor
    ClicOrganizer->>Client: Finalisasi Konsep Visual
    
    Note over Client, ClicOrganizer: Tahap 3: Execution & Control
    ClicOrganizer->>Client: Eksekusi Acara (Hari H)
    ClicOrganizer->>Client: Monitoring & Kontrol Lapangan
    Client->>ClicOrganizer: Feedback & Testimoni
```
