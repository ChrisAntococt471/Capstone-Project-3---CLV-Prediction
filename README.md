# Capstone-Project-3---CLV-Prediction
CLV Prediction using Regression
### **Business Problem**  
Sebuah perusahaan bernama PT. ABC merupakan perusahaan yang bergerak di bidang asuransi kendaraan bermotor. PT ABC menyediakan fasilitas asuransi pada berbagai jenis kendaraan dimulai dari kendaraan kota, SUV, hingga kendaraan premium.  
  
  
Dengan banyaknya pesaing yang bermunculan, PT ABC harus bertahan dari gempuran para pesaing tersebut. Banyak strategi yang bisa dilakukan oleh PT ABC, salah satunya adalah menjaga relasi dengan pelanggan yang ada. Berdasarkan Marketing Metrics yang dikutip dari artikel Forbes *Don't Get Lazy About Your Client Relationships*, bisnis memiliki kemungkinan mencapai 60 - 70% untuk menjual produknya ke konsumen yang sudah ada dan hanya 5 - 20% pada konsumen baru. Oleh karena itu, PT ABC berniat untuk memaksimalkan potensial pasar yang sudah ada.  

    
Namun, tidak semua konsumen di PT ABC memiliki karakteristik dan kebutuhan yang sama. Oleh karena itu, PT ABC ingin menelusuri lebih lanjut karakteristik dan nilai konsumen agar PT ABC tidak salah dalam mengalokasikan sumber daya untuk pemasaran. Salah satu indikator yang ingin dicari adalah Customer Lifetime Value (CLV). Customer Lifetime Value adalah indikator yang menyatakan nilai suatu pelanggan terhadap merk tertentu. Indikator tersebut mampu membantu PT ABC untuk mengenali nilai pelanggannya dengan lebih baik, sehingga PT ABC mampu menyiapkan strategi pemasaran dan penawaran yang lebih baik. Dengan tujuan tersebut, PT ABC ingin melakukan prediksi nilai Customer Lifetime Value.  
  
### **Conclusion**  
Berdasarkan hasil evaluasi model, maka pada kasus ini, model yang paling optimal untuk digunakan untuk memprediksi nilai CLV adalah model Random Forest setelah dilakukan hyperparameter tuning.  
  
Dari semua variabel yang ada, variabel Number of Policies dan Monthly Premium Auto merupakan variabel yang paling berpengaruh pada nilai CLV.  
  
### **Modelling**  
![alt text](https://github.com/ChrisAntococt471/Capstone-Project-3---CLV-Prediction/blob/main/Model%20Eval.png)  
Berdasarkan hasil metrik di atas, terdapat 3 model yang memiliki nilai error yang paling kecil, yaitu Decision Tree, Random Forest, dan XGBoost.  
- Model XGBoost memiliki nilai RMSE yang paling kecil setelah Random Forest.
- Model Decision Tree memiliki nilai MAE yang kecil, kedua terkecil setelah Random Forest.  
- Dari semua metrik yang ada, Random Forest memiliki nilai yang paling baik (Nilai RMSE, MAE, dan MAPE yang terkecil)  
  
**Predict to Test Set with Chosen Model**  
![alt text](https://github.com/ChrisAntococt471/Capstone-Project-3---CLV-Prediction/blob/main/Model%20Eval1.png)  
Pada prediksi pada test set kali ini, ditambah metrik baru, yaitu R-Squared.  
- Berdasarkan evaluasi metrik, model Random Forest merupakan nilai terbaik, dengan nilai error terkecil yang digambarkan oleh RMSE, MAE, dan MAPE serta nilai R-Squared yang paling besar  
  
**Hyperparameter Tuning Performance Comparison**    
![alt text](https://github.com/ChrisAntococt471/Capstone-Project-3---CLV-Prediction/blob/main/Performance%20comparison.png)  
Terdapat perbedaan performa model Random Forest sebelum tuning dan setelah tuning.  
- Nilai RMSE pada model Random Forest setelah tuning terlihat menurun dibandingkan dengan model sebelum tuning  
- Nilai MAE pada model Random Forest setelah tuning terlihat meningkat dibandingkan dengan model sebelum tuning  
- Nilai MAP pada model Random Forest setelah tuning terlihat meningkat tipis dibandingkan dengan model sebelum tuning  
- Nilai R-Squared pada model Random Forest setelah tuning terlihat meningkat dibandingkan dengan model sebelum tuning  
  
Dengan pertimbangan adanya peningkatan nilai R-Squared, yang berarti performa model dalam menjelaskan keadaan data lebih baik disertai penurunan nilai RMSE disertai kenaikan nilai MAPE yang cenderung kecil, maka akan dipilih model Random Forest yang sudah dilakukan hyperparameter tuning.  
  
**Actual vs Prediction** 
![alt text](https://github.com/ChrisAntococt471/Capstone-Project-3---CLV-Prediction/blob/main/Actual%20vs%20Pred.png)  
Model terlihat dapat memprediksi dengan baik pada angka CLV yang rendah walaupun ada kecenderungan terjadinya overestimate (angka berada di atas garis diagonal). Namun seiring meningkatnya angka CLV, pola angka mulai acak (terjadinya overestimation dan underestimation).  
  
Walaupun begitu, berdasarkan nilai MAPE yang didapat, yaitu sekitar 11.6%, maka model ini masih dapat digunakan. Contoh kasus lainnya seperti pada Jablecka (2020) yang mendapatkan nilai MAPE di kisaran 15 - 30%.

*Reference: Jablecka, M (2020). Modelling CLV in the Insurance Industry Using Deep Learning Methods*  
  
**Features Importance**  
![alt text](https://github.com/ChrisAntococt471/Capstone-Project-3---CLV-Prediction/blob/main/Features%20Importance.png)  
Pada grafis feature importance, terlihat variabel Number of Policies dan Monthly Premium Auto merupakan dua variabel yang paling berpengaruh terhadap nilai CLV. Variabel Total Claim Amount dan Income juga memiliki sedikit pengaruh terhadap nilai CLV.  
Hal yang menarik dari grafis feature importance ini adalah demografi pelanggan dan juga kendaraan yang diasuransikan tidak berpengaruh terhadap nilai CLV.
  
