# Laporan Praktikum 2: Organisasi dan Arsitektur Komputer
**Nama:** Ghina Emelia Yantes  
**NIM:** 13525119  
**Status:** All Phases Conquered (10/10) ✅

---

## 📑 Daftar Jawaban Tiap Phase

Berikut adalah ringkasan kunci jawaban untuk melewati setiap gerbang keamanan pada *binary bomb* praktikum kali ini:

| Phase | Fungsi Utama | Tipe Tantangan | Jawaban (Input) |
| :--- | :--- | :--- | :--- |
| **1** | `shigatsu_wa_kimi_no_uso` | String Comparison | `frulli_frulla` |
| **2** | `gurren_lagann` | Integer Comparison | `726` |
| **3** | `cruel_angel_thesis` | Caesar Cipher | `derosoy` |
| **4** | `one_piece` | Bitwise XOR | `NODQHDBD` |
| **5** | `Geometric_Dance` | Recursive Series ($3n+1$) | `564 1693 5080 15241` |
| **6** | `crossing_field` | String Manipulation | `wkrpgd` |
| **7** | `renai_circulation` | Recursive Arithmetic | `82 14` |
| **B1** | `kira_game` | Advanced XOR | `L_0wns_u` |
| **B2** | `Shougaizettaisouaisengen` | Magic Square ($3 \times 3$) | `182435796` |
| **B3** | `Ruler_Count_Zero_2` | Binary Tree Traversal | `98` |

---

## 🔍 Analisis Teknis (Highlights)

### 1. Phase 3: The Caesar Cipher
Fungsi ini melakukan validasi menggunakan rumus:  
`(*(char *)(a1 + i) - 49) % 26 + 65 == v3[i]`  
Dimana `v3` berisi string `"ZANKOKU"`. Melalui perhitungan *reverse engineering*, didapatkan bahwa input `derosoy` akan menghasilkan karakter-karakter tersebut setelah melewati operasi modulo 26.

### 2. Phase 4: Bitwise XOR
Logika utama menggunakan operasi `^ 0x21` (desimal 33).  
**Formula:** `Input ^ 33 = "onepiece"`.  
Dengan memanfaatkan sifat XOR yang *reversible*, kita menghitung `onepiece ^ 33` per karakter, yang menghasilkan string: `NODQHDBD`.

### 3. Bonus Phase 2: Nexus of Balance (Magic Square)
Tantangan paling kompleks yang mengharuskan pembuatan matriks $3 \times 3$ dengan jumlah baris, kolom, dan diagonal yang sama (15).
* **Mapping:** `array_3149[(digit - 48) % 9]`
* **Koreksi Modulo:** Digit `9` memetakan ke index `0`.
* **Susunan Matriks Nilai:**
    ```text
    2  7  6
    9  5  1
    4  3  8
    ```
* **Hasil Input:** `182435796`

### 4. Bonus Phase 3: The Tree of Destiny
Navigasi pada *Binary Tree* di dalam memori menggunakan input `8` (Kiri) dan `9` (Kanan).
* **Target:** Mencapai node dengan nilai `67`.
* **Path:** Root (10) → Right (20) → Left (67).
* **Input:** `9` kemudian `8` → `98`.

---

## 💻 Environment & Tools
* **Debugger:** GDB (GNU Debugger)
* **Decompiler:** Hex-Rays / Dogbolt
* **OS:** Ubuntu via WSL
* **Language:** C & x86 Assembly

---

> **Note:** Praktikum diselesaikan dengan sukses. Program keluar dengan status `exited normally`. 
> 
> *while (alive) { learn(); build(); commit(); repeat(); }*