<div align="center">

![Ekran görüntüsü 2023-08-30 005243](https://github.com/burakozdemirtas/multi-person-pose-estimation/assets/33163650/a03886be-7ca9-4557-966b-90b43d391f11)
</div>


<h1 align="center"> Multi Person Pose Estimation - Çok Kişili Poz Tahmini </h1>
<p align="justify">
Bu proje, TensorFlow ve OpenCV kütüphanelerini kullanarak hareket algılama ve çoklu anahtar nokta tespiti işlemi gerçekleştiren bir örnek içerir. Proje, bir video dosyasından girdi alır ve Movenet modeli ile anahtar noktaları tespit eder.
<br><br>This project contains an example of motion detection and multi-keypoint detection performed using TensorFlow and OpenCV libraries. The project takes input from a video file and detects key points using the Movenet model
</p>

*  [:fire: Geliştirici / Developer](#fire-geliştirici-developer)
*  [:hash: Kod Nasıl Çalışır?/How does the code work?](#hash-kod-nasıl-çalışır-how-does-the-code-work)


# :fire: Geliştirici/ Developer
| Adı Soyadı / Name Surname| 
| :--- | 
| [Burak ÖZDEMİRTAŞ](https://github.com/burakozdemirtas) |


# :hash: Kod Nasıl Çalışır? How does the code work?

- Gerekli Kütüphanelerin İçe Aktarılması:
  * İlk olarak, kodun çalışması için gereken kütüphaneler (tensorflow, cv2, numpy) içe aktarılır.

- GPU Bellek Yapılandırması (İsteğe Bağlı):
  * Eğer GPU kullanılıyorsa, bellek ayarlamaları yapılır. Ancak bu kodda GPU kullanılmadığını belirttiniz.

- Model ve İmza Yükleme:
  * Önceden kaydedilmiş bir TensorFlow modeli yüklenir ve modelin varsayılan imzası alınır.

- EDGES Sözlüğü:
  * Farklı vücut bölgeleri arasındaki ilişkileri belirten bir EDGES sözlüğü tanımlanır. Bu, çizgilerin hangi renklerle çizileceğini belirlemek için kullanılır.

- Yardımcı Fonksiyonlar:
  * draw_connections fonksiyonu, tespit edilen anahtar noktaları birleştiren çizgilerin çizilmesini sağlar.
  * draw_keypoints fonksiyonu, tespit edilen anahtar noktalarının çizilmesini sağlar.

- loop_through_people Fonksiyonu:
  * Bu fonksiyon, tespit edilen her bir kişi için anahtar noktaların ve bağlantıların çizilmesini yapar. İlgili anahtar nokta ve bağlantı bilgileri parametre olarak verilir.
 
- Video Yakalama:
  * Belirtilen videonun yakalanması için cv2.VideoCapture kullanılır.


- Yeni Boyut Değerleri:
  * Videonun boyutlarını belirlemek için new_width ve new_height değerleri tanımlanır.


- Video İşleme Döngüsü:
  * Videonun her bir karesi için bir döngü başlar.

- Görüntüyü Yeniden Boyutlandırma:
  * Yakalanan görüntü, belirtilen boyutlara (1920x1080) yeniden boyutlandırılır.

- TensorFlow ile Görüntü İşleme:
  * Görüntü, TensorFlow kullanılarak işlenir. Boyutlandırma ve veri türü dönüşümü yapılır.

- Anahtar Nokta Tespiti:
  * Model ile anahtar noktaların tespiti gerçekleştirilir.

- Anahtar Noktaların İşlenmesi:
  * Algılanan anahtar noktalar, loop_through_people fonksiyonu ile çizilir.

- Sonuç Görüntüsünün Gösterilmesi:
  * İşlenmiş görüntü, cv2.imshow ile ekranda gösterilir.
 
- Çıkış Kontrolü:
  * Klavyeden 'q' tuşuna basılana kadar döngü devam eder. 'q' tuşuna basıldığında döngü sonlandırılır ve kaynaklar serbest bırakılır.
  * Kısacası, bu kod videodan kareler yakalar, görüntü işleme yapar, anahtar noktaları tespit eder ve çizimleri görüntüler. Böylece hareket algılama ve anahtar nokta tespiti işlemleri gerçekleştirilmiş olur.
  <br>
---
  <br>
- Importing Required Libraries:
  * Firstly, the necessary libraries (tensorflow, cv2, numpy) are imported for the code to work.

- GPU Memory Configuration (Optional):
  * If a GPU is being used, memory configurations are set. However, you mentioned that GPU is not used in this code.

- Model and Signature Loading:
  * A pre-saved TensorFlow model is loaded and its default signature is obtained.

- EDGES Dictionary:
  * An EDGES dictionary is defined to represent relationships between different body parts. This is used to determine the colors of lines to be drawn.

- Helper Functions:
  * The draw_connections function is used to draw lines connecting detected key points.
  * The draw_keypoints function is used to draw the detected key points.

- loop_through_people Function:
  * This function draws key points and connections for each detected individual. Relevant key point and connection information is provided as parameters.

- Video Capturing:
  * cv2.VideoCapture is used to capture the specified video.

- New Dimension Values:
  * new_width and new_height values are defined to determine the dimensions of the video.

- Video Processing Loop:
  * A loop begins to process each frame of the video.

- Resizing the Image:
  * Captured images are resized to the specified dimensions (1920x1080).

- Image Processing with TensorFlow:
  * Images are processed using TensorFlow. Resizing and data type conversion are performed.

- Keypoint Detection:
  * Keypoints are detected using the model.

- Processing Keypoints:
  * Detected keypoints are drawn using the loop_through_people function.

- Displaying Resultant Image:
  * Processed images are displayed on the screen using cv2.imshow.

- Exit Control:
  * The loop continues until the 'q' key is pressed. When 'q' is pressed, the loop ends, and resources are released.
  * In summary, this code captures frames from a video, performs image processing, detects key points, and displays the drawings. This accomplishes the tasks of motion detection and key point detection.

