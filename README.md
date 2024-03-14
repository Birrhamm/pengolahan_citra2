# TUGAS

Impor pustaka yang diperlukan:

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

Baca gambar masukan menggunakan OpenCV:


```
img = cv2.imread("upb.jpg")
```

Tampilkan gambar asli menggunakan Matplotlib:

[:,:,::-1] digunakan untuk mengonversi format BGR (digunakan oleh OpenCV) menjadi format RGB (digunakan oleh Matplotlib).

```
plt.imshow(img[:,:,::-1])
plt.show()
```



Tentukan empat titik masukan (inputPts) dan titik destinasi yang sesuai (outputPts) untuk transformasi perspektif:

```
inputPts = np.float32([[4,381],
                      [266,429],
                      [329,68],
                      [68,20]])

outputPts = np.float32([[0,300],
                       [300,300],
                       [300,0],
                       [0,0]])
```
                       
Hitung matriks transformasi perspektif (M) menggunakan cv2.getPerspectiveTransform():

```
M = cv2.getPerspectiveTransform(inputPts, outputPts)

```

Terapkan transformasi perspektif pada gambar masukan menggunakan cv2.warpPerspective():

```
dst = cv2.warpPerspective(img, M, (300,300))
  
```
Gambar hasil (dst) akan menjadi versi gambar yang telah mengalami transformasi perspektif.

Simpan gambar yang telah diubah menggunakan plt.savefig() milik Matplotlib:

Kembali, [:,:,::-1] digunakan untuk mengonversi format BGR menjadi RGB sebelum menyimpan gambar.

```
plt.imshow(dst[:,:,::-1])
plt.savefig("output_image.png")
plt.show()

```

# HASIL
![Screenshot (273)](https://github.com/Birrhamm/pengolahan_citra2/assets/115520530/a1c22f80-8408-4c44-a357-9732f8f6f1a9)

![Screenshot (274)](https://github.com/Birrhamm/pengolahan_citra2/assets/115520530/47e31b14-68dd-4007-b7b8-415ff088fe7f)

![Screenshot (275)](https://github.com/Birrhamm/pengolahan_citra2/assets/115520530/0598213d-5d63-49ae-93f3-5f947e980c7d)



