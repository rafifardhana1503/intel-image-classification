# Klasifikasi Gambar dengan CNN - Dataset Intel Image

**Deskripsi**
Proyek ini merupakan Proyek ini merupakan model deep learning klasifikasi gambar yang dilatih menggunakan Intel Image Classification dataset, yang berisi gambar-gambar pemandangan alam yang diklasifikasikan ke dalam enam kategori: buildings, forest, glacier, mountain, sea, dan street.

Link Dataset: https://www.kaggle.com/datasets/puneet6060/intel-image-classification

**Struktur Proyek**
submission
├───tfjs_model
| ├───group1-shard1of3.bin
| ├───group1-shard2of3.bin
| ├───group1-shard3of3.bin
| └───model.json
├───tflite
| ├───model.tflite
| └───label.txt
├───saved_model
| ├───saved_model.pb
| └───variables
├───notebook.ipynb
├───README.md
└───requirements.txt

**Informasi Dataset**
- Jumlah total gambar: ±25.000
- Kelas:
    - Buildings
    - Forest
    - Glacier
    - Mountain
    - Sea
    - Street

**Arsitektur Model**
Model ini menggunakan arsitektur Tranfer Learning + Convolutional Neural Network (CNN) Sequential dengan TensorFlow & Keras, terdiri dari:
- Base model:
    - MobileNetV2

- 2 blok:
    - Conv2D + MaxPooling2D

- Diikuti oleh:
    - GlobalAveragePooling2D
    - Dense + Dropout
    - Output layer dengan aktivasi Softmax

- Callback yang digunakan:
    - CustomEarlyStopping
    - ReduceLROnPlateau

**Peforma Model**
| Metric        | Value     |
|---------------|-----------|
| Training Acc. | 96.29%    |
| Val. Accuracy | 91.05%    |
| Test Accuracy | 89.36%    |


**Penyimpanan Model**
Model di simpan ke dalam format:
- SavedModel
- TFLite
- TFJS