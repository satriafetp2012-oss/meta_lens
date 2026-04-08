# MetaLens ‚Äî Meta-Analysis Studio

> **Developed by Bayu Satria Wiratama, Ph.D**
> Assistant Professor, Department of Biostatistics, Epidemiology, and Population Health
> Faculty of Medicine, Public Health, and Nursing (FK-KMK), Universitas Gadjah Mada
> ‚úâ bayu.satria@ugm.ac.id

---

<!-- Language switch -->
[English](#english) ¬∑ üáÆüá© [Bahasa Indonesia](#bahasa-indonesia)

---

<a name="english"></a>
# üá¨üáß English

## Overview

**MetaLens** is a free, browser-based meta-analysis studio designed for researchers, clinicians, and students in health sciences. It provides a complete meta-analysis workflow ‚Äî from data import and effect size conversion to pooling, heterogeneity testing, publication bias assessment, subgroup analysis, and meta-regression ‚Äî without requiring any software installation.

All computations run entirely in your browser. **No data is ever sent to any server.** Your study data stays on your device.

---

## Features

### üîÑ Four Independent Analysis Modules

MetaLens handles four distinct study types, each with its own dataset and complete analysis suite:

| Module | Study Type | Effect Measures |
|---|---|---|
| üéØ **Effectiveness** | RCTs, interventions, clinical trials | SMD, MD, OR, RR, HR, RD |
| ü©∫ **Diagnostic** | Test accuracy, sensitivity/specificity | Sensitivity, Specificity, +LR, ‚àíLR, DOR, SROC AUC |
| üìâ **Prevalence** | Disease/condition burden studies | Pooled proportion (%) |
| üîó **Association** | Observational, correlational studies | r, OR, RR, HR |

---

### üì• Data Input

- **Import from Excel / CSV** ‚Äî drag-and-drop file upload with preview before confirming
- **Manual entry** ‚Äî add one study at a time using an adaptive form that matches the selected study type
- **Downloadable templates** ‚Äî pre-formatted Excel templates for each study type
- **Type-specific required fields** ‚Äî automatic validation ensures the right columns are present

**Required columns by type:**

| Type | Required | Optional |
|---|---|---|
| Effectiveness | author, year, effect_size, variance (or se) | ci_lower, ci_upper, n_total, effect_type |
| Diagnostic | author, year, tp, fp, fn, tn | n_total, threshold, index_test |
| Prevalence | author, year, cases, n | subgroup, country, age_mean |
| Association | author, year, effect_size, variance (or se) | ci_lower, ci_upper, n_total, exposure, outcome |

---

### üìä Analysis Sections (all four modules)

Each study type provides the following analyses:

#### üéØ Pooled Effect
- Random-Effects model (DerSimonian-Laird) or Fixed-Effect (Inverse Variance)
- Pooled effect size with confidence interval, Z-statistic, and p-value
- Automatic back-transformation for ratio measures (OR, RR, HR shown on original scale)
- Per-study contribution table (effect size, variance, weight %, Z)
- Full heterogeneity summary (Q, I¬≤, œÑ¬≤, H¬≤)

#### üå≤ Forest Plot
- Sortable by year, effect size, or author
- Weighted squares proportional to study weight
- Pooled diamond at the bottom
- Downloadable as PNG

#### üìê Heterogeneity
- Cochran's Q statistic with p-value
- I¬≤ (%), œÑ¬≤ (tau-squared), œÑ (tau), H¬≤
- Categorical interpretation (Low / Moderate / Substantial / Considerable)
- Clinical recommendation on model choice

#### üî≠ Publication Bias
- **Egger's test** ‚Äî regression of standardised effect on precision
- **Begg & Mazumdar rank correlation test** (Kendall's œÑ)
- **Rosenthal's Fail-Safe N** with robustness threshold (5k+10)
- **Funnel plot** ‚Äî downloadable as PNG

#### üóÇÔ∏è Subgroup Analysis
- Auto-detects moderator columns from imported data
- Between-group Q test (test of subgroup differences)
- Per-subgroup pooled effect, CI, I¬≤, Q
- **Subgroup forest plot** with colour-coded groups ‚Äî downloadable as PNG

#### üìà Meta-Regression
- Weighted Least Squares (WLS) with random-effects œÑ¬≤ as prior
- Automatic dummy coding for categorical predictors
- R¬≤ (proportion of variance explained by moderators)
- Q_residual test, coefficient table with Œ≤, SE, t, p-value, 95% CI

---

### ü©∫ Diagnostic-Specific Features

- **Pooled Sensitivity & Specificity** ‚Äî pooled on logit scale via random-effects, back-transformed to %
- **Likelihood Ratios** ‚Äî positive LR (+LR) and negative LR (‚àíLR) with clinical interpretation
- **Diagnostic Odds Ratio (DOR)** ‚Äî pooled on log scale
- **SROC Curve** ‚Äî Moses-Littenberg method with AUC estimation
  - Individual study points plotted on ROC space
  - Pooled operating point (green diamond)
  - Downloadable as PNG
- **Deeks' Funnel Plot Asymmetry Test** ‚Äî adapted for diagnostic studies
- **Subgroup analysis** ‚Äî can pool by DOR, Sensitivity, or Specificity separately

---

### üìâ Prevalence-Specific Features

- **Freeman-Tukey double arcsine transformation** (recommended for extreme proportions)
- **Logit transformation** ‚Äî suitable for moderate prevalences
- **Raw proportion** ‚Äî no transformation
- All back-transformed to % scale for display
- **Subgroup pooling** ‚Äî stratified prevalence with between-group test

---

### üîÑ Effect Size Converter (5 tabs)

Convert raw reported statistics into effect sizes for meta-analysis. Results can be added directly to the dataset.

| Tab | Converts |
|---|---|
| **Means & SDs** | M‚ÇÅ, SD‚ÇÅ, N‚ÇÅ, M‚ÇÇ, SD‚ÇÇ, N‚ÇÇ ‚Üí Cohen's d, Hedges' g, Glass's Œî, MD |
| **2√ó2 Table** | a, b, c, d ‚Üí OR, log(OR), RR, log(RR), RD, NNT (with SEs and CIs) |
| **Correlation r** | r, N ‚Üí Fisher's z, variance, 95% CI (for correlation meta-analysis) |
| **t / F statistic** | t or F + N‚ÇÅ/N‚ÇÇ ‚Üí Cohen's d, Hedges' g, variance |
| **d ‚Üî r ‚Üî OR** | Cross-measure conversion with variance propagation |

---

### üíæ Export

- **Full text report (.txt)** ‚Äî structured report covering all four modules with pooled results
- **Study data (.csv)** ‚Äî per-module CSV export
- **Forest plot PNG** ‚Äî main and subgroup forest plots
- **Funnel plot PNG**
- **SROC curve PNG**

---

### ‚öôÔ∏è Project Configuration

- **Statistical model** ‚Äî Random-Effects (DerSimonian-Laird) or Fixed-Effect
- **Confidence interval level** ‚Äî 90%, 95%, or 99%
- **Prevalence transformation** ‚Äî Freeman-Tukey, Logit, or Raw
- **Custom moderator variables** ‚Äî define categorical or continuous moderators for subgroup and regression analysis

---

## Getting Started

### Option A: Open locally (no setup needed)

1. Download `meta-analysis-tool-v5.html`
2. Double-click the file to open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. The app loads instantly ‚Äî no internet connection required for analysis

### Option B: Host on GitHub Pages (free, shareable URL)

1. **Create a GitHub account** at [github.com](https://github.com)
2. **Create a new repository** ‚Äî name it `metalens`, set to **Public**
3. **Upload the file** ‚Äî go to *Add file ‚Üí Upload files*, upload `meta-analysis-tool-v5.html`, **rename it to `index.html`**
4. **Enable GitHub Pages** ‚Äî go to *Settings ‚Üí Pages ‚Üí Source: Deploy from branch ‚Üí main / (root)* ‚Üí Save
5. **Access your live URL** ‚Äî `https://[your-username].github.io/metalens/`

> Updates: To deploy a new version, go to `index.html` in your repository ‚Üí edit ‚Üí paste the new content ‚Üí commit. GitHub Pages redeploys in ~1 minute.

---

## Workflow Guide

```
1. Project Setup  ‚Üí  Set analysis model, CI level, prevalence transform, moderators
2. Import Data    ‚Üí  Select study type, upload Excel/CSV or add studies manually
3. Data Table     ‚Üí  Review, search, and manage imported studies
4. Analysis       ‚Üí  Navigate each section (Pooled ‚Üí Forest ‚Üí Heterogeneity ‚Üí Bias ‚Üí Subgroup ‚Üí Regression)
5. Effect Converter (optional) ‚Üí Convert raw statistics and add to dataset
6. Export         ‚Üí  Download report and plots
```

---

## Statistical Methods

| Method | Reference |
|---|---|
| Random-effects pooling | DerSimonian & Laird (1986) |
| Fixed-effect pooling | Inverse variance weighting |
| Heterogeneity (I¬≤) | Higgins & Thompson (2002) |
| Egger's test | Egger et al. (1997) |
| Begg's test | Begg & Mazumdar (1994) |
| Fail-Safe N | Rosenthal (1979) |
| Logit pooling (Sens/Spec) | Doebler & Holling (2015) |
| SROC curve | Moses, Shapiro & Littenberg (1993) |
| Freeman-Tukey transform | Freeman & Tukey (1950) |
| Meta-regression (WLS) | Thompson & Higgins (2002) |
| Hedges' g correction | Hedges (1981) |
| Fisher's z transformation | Fisher (1925) |

---

## Browser Compatibility

| Browser | Support |
|---|---|
| Google Chrome 90+ | ‚úÖ Fully supported |
| Mozilla Firefox 88+ | ‚úÖ Fully supported |
| Microsoft Edge 90+ | ‚úÖ Fully supported |
| Safari 14+ | ‚úÖ Fully supported |
| Internet Explorer | ‚ùå Not supported |

---

## Citation

If you use MetaLens in your research, please cite:

```
Wiratama BS. MetaLens: A browser-based meta-analysis studio [Software].
Department of Biostatistics, Epidemiology, and Population Health, FK-KMK,
Universitas Gadjah Mada; 2025.
Available at: https://github.com/[your-username]/metalens
```

---

## Contact

**Bayu Satria Wiratama, Ph.D**
Department of Biostatistics, Epidemiology, and Population Health
Faculty of Medicine, Public Health, and Nursing (FK-KMK)
Universitas Gadjah Mada, Yogyakarta, Indonesia
‚úâ bayu.satria@ugm.ac.id
üåê https://fkkmk.ugm.ac.id

---
---

<a name="bahasa-indonesia"></a>
# üáÆüá© Bahasa Indonesia

## Gambaran Umum

**MetaLens** adalah aplikasi meta-analisis berbasis browser yang gratis dan dirancang untuk peneliti, klinisi, dan mahasiswa di bidang ilmu kesehatan. Aplikasi ini menyediakan alur kerja meta-analisis yang lengkap ‚Äî mulai dari impor data dan konversi ukuran efek hingga penggabungan (pooling), uji heterogenitas, penilaian bias publikasi, analisis subkelompok, dan meta-regresi ‚Äî tanpa memerlukan instalasi perangkat lunak apapun.

Semua komputasi berjalan sepenuhnya di browser Anda. **Data tidak pernah dikirim ke server manapun.** Data studi Anda tersimpan di perangkat Anda sendiri.

---

## Fitur

### üîÑ Empat Modul Analisis Independen

MetaLens menangani empat jenis studi yang berbeda, masing-masing dengan dataset dan rangkaian analisis lengkapnya sendiri:

| Modul | Jenis Studi | Ukuran Efek |
|---|---|---|
| üéØ **Efektivitas** | RCT, intervensi, uji klinis | SMD, MD, OR, RR, HR, RD |
| ü©∫ **Diagnostik** | Akurasi uji, sensitivitas/spesifisitas | Sensitivitas, Spesifisitas, +LR, ‚àíLR, DOR, AUC SROC |
| üìâ **Prevalensi** | Studi beban penyakit/kondisi kesehatan | Proporsi gabungan (%) |
| üîó **Asosiasi** | Studi observasional, korelasional | r, OR, RR, HR |

---

### üì• Input Data

- **Impor dari Excel / CSV** ‚Äî unggah file dengan drag-and-drop beserta pratinjau sebelum konfirmasi
- **Entri manual** ‚Äî tambahkan satu studi setiap kali menggunakan formulir adaptif yang menyesuaikan jenis studi yang dipilih
- **Templat yang dapat diunduh** ‚Äî templat Excel terformat untuk setiap jenis studi
- **Kolom wajib per jenis** ‚Äî validasi otomatis memastikan kolom yang tepat tersedia

**Kolom yang diperlukan per jenis studi:**

| Jenis | Wajib | Opsional |
|---|---|---|
| Efektivitas | author, year, effect_size, variance (atau se) | ci_lower, ci_upper, n_total, effect_type |
| Diagnostik | author, year, tp, fp, fn, tn | n_total, threshold, index_test |
| Prevalensi | author, year, cases, n | subgroup, country, age_mean |
| Asosiasi | author, year, effect_size, variance (atau se) | ci_lower, ci_upper, n_total, exposure, outcome |

---

### üìä Bagian Analisis (semua empat modul)

Setiap jenis studi menyediakan analisis berikut:

#### üéØ Efek Gabungan (Pooled Effect)
- Model Random-Effects (DerSimonian-Laird) atau Fixed-Effect (Inverse Variance)
- Ukuran efek gabungan dengan interval kepercayaan, statistik Z, dan nilai p
- Transformasi balik otomatis untuk ukuran rasio (OR, RR, HR ditampilkan dalam skala asli)
- Tabel kontribusi per studi (ukuran efek, varians, bobot %, Z)
- Ringkasan heterogenitas lengkap (Q, I¬≤, œÑ¬≤, H¬≤)

#### Forest Plot
- Dapat diurutkan berdasarkan tahun, ukuran efek, atau penulis
- Kotak berbobot proporsional terhadap bobot studi
- Diamond gabungan di bagian bawah
- Dapat diunduh sebagai PNG

#### üìê Heterogenitas
- Statistik Q Cochran dengan nilai p
- I¬≤ (%), (tau-kuadrat), (tau), H¬≤
- Interpretasi kategoris (Rendah / Sedang / Substansial / Considerable)
- Rekomendasi klinis pemilihan model

#### Bias Publikasi
- **Uji Egger** ‚regresi efek terstandarisasi terhadap presisi
- **Uji korelasi peringkat Begg & Mazumdar** (Kendall's)
- **Fail-Safe N Rosenthal** dengan ambang ketahanan (5k+10)
- **Funnel plot** ‚dapat diunduh sebagai PNG

#### Analisis Subkelompok
- Mendeteksi kolom moderator secara otomatis dari data yang diimpor
- Uji Q antar kelompok (uji perbedaan subkelompok)
- Efek gabungan per subkelompok, CI, I¬≤, Q
- **Forest plot subkelompok** dengan kelompok berbeda warna ‚Äî dapat diunduh sebagai PNG

#### Meta-Regresi
- Weighted Least Squares (WLS) dengan œÑ¬≤ random-effects sebagai prior
- Pengkodean dummy otomatis untuk prediktor kategoris
- R¬≤ (proporsi varians yang dijelaskan oleh moderator)
- Uji Q_residual, tabel koefisien dengan Œ≤, SE, t, nilai p, 95% CI

---

### Fitur Khusus Diagnostik

- **Pooled Sensitivitas & Spesifisitas** ‚digabungkan pada skala logit melalui random-effects, ditransformasi balik ke %
- **Likelihood Ratio** ‚LR positif (+LR) dan LR negatif (‚àíLR) dengan interpretasi klinis
- **Diagnostic Odds Ratio (DOR)** ‚digabungkan pada skala log
- **Kurva SROC** ‚metode Moses-Littenberg dengan estimasi AUC
  - Titik studi individual diplotkan dalam ruang ROC
  - Titik operasi gabungan (diamond hijau)
  - Dapat diunduh sebagai PNG
- **Uji Asimetri Funnel Plot Deeks** ‚disesuaikan untuk studi diagnostik
- **Analisis subkelompok** ‚dapat menggabungkan berdasarkan DOR, Sensitivitas, atau Spesifisitas secara terpisah

---

### Fitur Khusus Prevalensi

- **Transformasi double arcsine Freeman-Tukey** (direkomendasikan untuk proporsi ekstrem)
- **Transformasi Logit** ‚Äî cocok untuk prevalensi moderat
- **Proporsi mentah** ‚Äî tanpa transformasi
- Semua ditransformasi balik ke skala % untuk tampilan
- **Penggabungan subkelompok** ‚Äî prevalensi terstratifikasi dengan uji antar kelompok

---

### Konverter Ukuran Efek (5 tab)

Konversi statistik yang dilaporkan secara mentah menjadi ukuran efek untuk meta-analisis. Hasil dapat langsung ditambahkan ke dataset.

| Tab | Mengonversi |
|---|---|
| **Means & SDs** | M‚ÇÅ, SD‚ÇÅ, N‚ÇÅ, M‚ÇÇ, SD‚ÇÇ, N‚ÇÇ ‚Üí Cohen's d, Hedges' g, Glass's Œî, MD |
| **Tabel 2√ó2** | a, b, c, d ‚Üí OR, log(OR), RR, log(RR), RD, NNT (dengan SE dan CI) |
| **Korelasi r** | r, N ‚Üí Fisher's z, varians, 95% CI (untuk meta-analisis korelasi) |
| **Statistik t / F** | t atau F + N‚ÇÅ/N‚ÇÇ ‚Üí Cohen's d, Hedges' g, varians |
| **d ‚Üî r ‚Üî OR** | Konversi lintas ukuran dengan propagasi varians |

---

### Ekspor

- **Laporan teks lengkap (.txt)** ‚Äî laporan terstruktur mencakup semua empat modul dengan hasil gabungan
- **Data studi (.csv)** ‚Äî ekspor CSV per modul
- **Forest plot PNG** ‚Äî forest plot utama dan subkelompok
- **Funnel plot PNG**
- **Kurva SROC PNG**

---

### Konfigurasi Proyek

- **Model statistik** ‚Random-Effects (DerSimonian-Laird) atau Fixed-Effect
- **Tingkat interval kepercayaan** ‚90%, 95%, atau 99%
- **Transformasi prevalensi** ‚Freeman-Tukey, Logit, atau Mentah
- **Variabel moderator kustom** ‚tentukan moderator kategoris atau kontinu untuk analisis subkelompok dan regresi

---

## Cara Memulai

### Opsi A: Buka secara lokal (tanpa pengaturan)

1. Unduh `meta-analysis-tool-v5.html`
2. Klik dua kali file tersebut untuk membukanya di browser modern apa pun (Chrome, Firefox, Edge, Safari)
3. Aplikasi langsung dimuat ‚Äî tidak diperlukan koneksi internet untuk analisis

### Opsi B: Host di GitHub Pages (gratis, URL yang dapat dibagikan)

1. **Buat akun GitHub** di [github.com](https://github.com)
2. **Buat repositori baru** ‚beri nama `metalens`, atur ke **Public**
3. **Unggah file** ‚Äî buka *Add file ‚Üí Upload files*, unggah `meta-analysis-tool-v5.html`, **ganti namanya menjadi `index.html`**
4. **Aktifkan GitHub Pages** ‚buka *Settings ‚Üí Pages ‚Üí Source: Deploy from branch ‚Üí main / (root)* ‚Üí Save
5. **Akses URL live Anda** ‚https://[username-anda].github.io/metalens/`

> Pembaruan: Untuk menerapkan versi baru, buka `index.html` di repositori Anda ‚Üí edit ‚Üí tempel konten baru ‚Üí commit. GitHub Pages melakukan deploy ulang dalam ~1 menit.

---

## Panduan Alur Kerja

```
1. Pengaturan Proyek  ‚Atur model analisis, tingkat CI, transformasi prevalensi, moderator
2. Impor Data         ‚Pilih jenis studi, unggah Excel/CSV atau tambah studi secara manual
3. Tabel Data         ‚Tinjau, cari, dan kelola studi yang diimpor
4. Analisis           ‚Navigasi setiap bagian (Pooled ‚Üí Forest ‚Üí Heterogenitas ‚Üí Bias ‚Üí Subkelompok ‚Üí Regresi)
5. Konverter Efek     ‚(Opsional) Konversi statistik mentah dan tambahkan ke dataset
6. Ekspor             ‚Unduh laporan dan plot
```

---

## Metode Statistik

| Metode | Referensi |
|---|---|
| Penggabungan random-effects | DerSimonian & Laird (1986) |
| Penggabungan fixed-effect | Inverse variance weighting |
| Heterogenitas (I¬≤) | Higgins & Thompson (2002) |
| Uji Egger | Egger et al. (1997) |
| Uji Begg | Begg & Mazumdar (1994) |
| Fail-Safe N | Rosenthal (1979) |
| Penggabungan logit (Sens/Spec) | Doebler & Holling (2015) |
| Kurva SROC | Moses, Shapiro & Littenberg (1993) |
| Transformasi Freeman-Tukey | Freeman & Tukey (1950) |
| Meta-regresi (WLS) | Thompson & Higgins (2002) |
| Koreksi Hedges' g | Hedges (1981) |
| Transformasi Fisher's z | Fisher (1925) |

---

## Kompatibilitas Browser

| Browser | Dukungan |
|---|---|
| Google Chrome 90+ |Didukung penuh |
| Mozilla Firefox 88+ |Didukung penuh |
| Microsoft Edge 90+ |Didukung penuh |
| Safari 14+ |Didukung penuh |
| Internet Explorer |Tidak didukung |

---

## Sitasi

Jika Anda menggunakan MetaLens dalam penelitian Anda, silakan sitasi:

```
Wiratama BS. MetaLens: A browser-based meta-analysis studio [Software].
Departemen Biostatistik, Epidemiologi, dan Kesehatan Populasi, FK-KMK,
Universitas Gadjah Mada; 2025.
Tersedia di: https://github.com/[username-anda]/metalens
```

---

## Kontak

**Bayu Satria Wiratama, Ph.D**
Departemen Biostatistik, Epidemiologi, dan Kesehatan Populasi
Fakultas Kedokteran, Kesehatan Masyarakat, dan Keperawatan (FK-KMK)
Universitas Gadjah Mada, Yogyakarta, Indonesia
‚úâ bayu.satria@ugm.ac.id
üåê https://fkkmk.ugm.ac.id

---

*MetaLens ‚Äî Gratis untuk penggunaan akademik dan penelitian. Distribusi ulang dengan atribusi diperbolehkan.*

