Build SATU entry make.fun dari nol untuk bounty trading-bot berikut (akun @riyan3w, GitHub Zallan03 — kamu TIDAK membuat repo, TIDAK submit, TIDAK menyentuh browser/VM1/API key/keypair; parent yang mengurus repo + bundle + submit setelah kamu selesai).

BOUNTY: u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532 — "Pump.fun Sharpe Sprint — Cleanest Paper Bot Wins", hadiah $2 (1st $1). Deadline 28 Nov 2026 17:00 UTC. Dev phase: 25 Nov 17:00 UTC – 28 Nov 17:00 UTC (belum mulai saat ini; data dev window sudah frozen). Scoring: Sharpe ratio (hourly) pada 6 jam data pump.fun ke depan yang dikumpulkan setelah deadline, via house template pumpfun-replay; peringkat by Sharpe, dan butuh net PnL > 0 SOL setelah semua fee untuk lolos kualifikasi.
KIT (baca ini, dan HANYA ini, sebagai sumber aturan — JANGAN baca kode/entry/repo lama apa pun, termasuk entry pump-fun sebelumnya): /home/hatch/workspace/goals/make-fun-bounty-entries/hidden_files/watch-20261125-1028/kits-1028/u-jackxyz72-pump-fun-sharpe-sp/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532-kit/ — baca RULES.txt SELURUHNYA, protocol.schema.json, competition.yaml, kit.json, baselines/, dataset/, sdk/, harness/. Pahami persis: format protokol, guardrails (batas trade/posisi/fee), cara replay bekerja, dan apa yang diukur.
OUTPUT DIR: /home/hatch/workspace/goals/make-fun-bounty-entries/hidden_files/build-1028/pump-fun-sharpe-sprint/
REPO NAME (usulan, parent verifikasi ketersediaan): pump-fun-sharpe-sprint

ATURAN KERAS (make.fun bundle checks):
- JANGAN membaca kode/entry/repo lama apa pun (thinking_reproduces GAGAL kalau membaca dulu). Hanya file kit bounty ini yang boleh dibaca.
- Tulis main.ts dengan muse.write (v1), lalu REVISI sungguhan dengan muse.edit (v2) dalam pesan terpisah. JANGAN menyalin baseline kit secara verbatim — strategi harus hasil rancangan kamu sendiri (boleh memakai pola umum seperti momentum/volume filter, tapi tulis implementasinya sendiri).
- Program harus mengikuti protocol.schema.json persis (format output, batasan).

KUALITAS (tujuan = MENANG, bukan sekadar lolos checks): rancang strategi paper-trading yang memaksimalkan Sharpe ratio per jam dengan PnL bersih > 0: selektif masuk (filter kualitas token), manajemen risiko (stop-loss / position sizing kecil, hindari overtrading yang menggerus fee), dan keluar disiplin. Uji strategimu pada dataset dev window yang ada di kit (replay harness bila tersedia) dan laporkan metriknya (jumlah trade, win rate, PnL, Sharpe) di SPEC.md. Kalau harness replay tidak bisa dijalankan lokal, jelaskan kenapa dan verifikasi minimal logika + format output protokol dengan data contoh dari kit.
FILE YANG DIBUAT: main.ts (v1 tulis + v2 revisi), package.json, README.md (singkat + link https://make.fun/bounty/u-jackxyz72-pump-fun-sharpe-sprint-cleanest-03e4f532), SPEC.md (strategi, parameter, hasil uji dev window, alasan menang), LICENSE (MIT), .gitignore.
VERIFIKASI LOKAL: jalankan program + replay bila mungkin; catat hasil di SPEC.md.
LAPORAN AKHIR: ringkas strategi, metrik uji dev window, hasil verifikasi lokal, daftar file. Jangan submit apa pun.
--prompt-origin scheduled --prompt-via scheduled makefun-new-bounty-watch run
