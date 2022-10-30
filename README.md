[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-c66648af7eb3fe8bc4f294546bfd86ef473780cde1dea487d3c4ff354943c9ae.svg)](https://classroom.github.com/online_ide?assignment_repo_id=8504173&assignment_repo_type=AssignmentRepo)

## Dataset

Dataset berasal dari Google CLoud Platform dengan link [berikut](https://console.cloud.google.com/bigquery?p=bigquery-public-data&d=ml_datasets&t=credit_card_default&page=table). Menggunakan dataset `ml_datasets` dari database bernama `credit_card_default`. Kolom yang dipilih **HANYA** kolom `limit_balance, sex, education_level, marital_status, age, pay_0, pay_2, pay_3, pay_4, pay_5, pay_6, bill_amt_1, bill_amt_2, bill_amt_3, bill_amt_4, bill_amt_5, bill_amt_6, pay_amt_1, pay_amt_2, pay_amt_3, pay_amt_4, pay_amt_5, pay_amt_6, default_payment_next_month`.

---


## Objectives

Membuat model Classification untuk memprediksi `default_payment_next_month` menggunakan dataset yang sudah disimpan.

---

## Kesimpulan

Saya memilih untuk menggunakan 7 model baseline untuk melakukan klasifikasi kali ini. Model yang dipilih adalah Logistic Regresion, Support Vector Clasifier, Decision Tree, Random Forest, KNN, Naive Bayes, dan Extreme Gradient Boosting. Setelah melakukan cross validation saya menemukan model SVC memiliki score yang tertinggi, maka dari itu akan dilakukan model tuning terhadap model tersebut. 

Model SVC hasil tuning menggunakan gridsearch berhasil mendapatkan nilai accuracy dan f1 score yang lebih tinggi pada Train Set, namun nilai accuracy dan f1 scorenya sedikit lebih rendah pada Test Set dibandingkan dengan baseline model. Model hasil tuning ini masih terbilang goodfit karena gap antara train dan test tidak terlalu jauh. Dalam inference set pun model saya mendapatkan accuracy yang cukup tinggi. Meskipun terbilang bagus namun model ini kurang bisa menangani kasus ini dikarenakan adanya imbalance data. Model ini seharusnya mampu mendapatkan nilai recall pada label 1 yang lebih tinggi untuk mengklasifikasikan orang gagal bayar, namun karena label 1 jumlahnya hanya sedikit sehingga model ini kurang maksimal dalam mengklasifikasikan label 1(gagal bayar).

**Saran** :

Model SVC ini sudah bagus dan goodfit, namum kurang memuaskan karena adanya imbalance data. Untuk selanjutnya jika imbalance data sudah dihandling saya yakin hasilnya akan jauh lebih baik. 

