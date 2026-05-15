# Specialist Agents Registry

File ini mendefinisikan daftar agen spesialis yang dapat dipanggil oleh ORCA untuk menyelesaikan Equity Research Pipeline.

## [agent1-macro]
- **Role**: Macro & Industry Analyst
- **Capabilities**: Analisis ekonomi makro Indonesia, tren industri, regulasi, dan struktur kompetisi sektor.
- **Input**: Master Context dari ORCA.

## [agent2-companyresearch]
- **Role**: Company Research Analyst
- **Capabilities**: Analisis model bisnis, moat (keunggulan kompetitif), profil manajemen, dan strategi korporasi.
- **Input**: Master Context dari ORCA.

## [agent3-financials]
- **Role**: Financial Modeler
- **Capabilities**: Analisis laporan keuangan historis 5 tahun, pembuatan proyeksi 3 tahun, dan perhitungan rasio keuangan (NIM, ROE, dll).
- **Dependencies**: Membutuhkan data operasional dari agent2-companyresearch.

## [agent4-esg]
- **Role**: ESG Analyst
- **Capabilities**: Penilaian Environmental, Social, dan Governance serta identifikasi risiko material non-finansial.
- **Input**: Master Context dari ORCA.

## [agent5-valuation]
- **Role**: Valuation Analyst
- **Capabilities**: Valuasi DCF, Relative Valuation (PER/PBV), Sensitivity Analysis, dan penentuan Target Price.
- **Dependencies**: Membutuhkan model keuangan dari agent3-financials.

## [agent6-risk]
- **Role**: Risk Analyst
- **Capabilities**: Identifikasi risiko sistemik dan non-sistemik menggunakan Likelihood & Impact scoring.
- **Dependencies**: Membutuhkan output dari Agent 1, 2, dan 3.

## [agent8-chart]
- **Role**: Chart Generator
- **Capabilities**: Mengubah array data JSON menjadi visualisasi grafik (Base64) standar institusi.
- **Input**: `charts_needed` dari semua agen spesialis.

## [agent7-report]
- **Role**: Report Writer
- **Capabilities**: Sintesis akhir seluruh narasi dan grafik menjadi satu laporan riset final standar CFA.
- **Dependencies**: Harus menunggu seluruh Agent 1-6 dan Agent 8 selesai.