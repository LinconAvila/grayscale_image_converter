# 🖼️ Multithreaded Color to Grayscale Image Converter in C++

This C++ program uses OpenCV and POSIX threads (pthreads) to convert a color image to grayscale. The conversion is parallelized by dividing the image into segments, each processed by a separate thread for improved performance.

---

## 🚀 Features

- Prompts the user for an image path via console input.
- Converts the image to grayscale using 4 threads.
- Displays both the original and the grayscale image.
- Saves the result as `output_gray.jpg`.

---

## 🧰 Requirements

- C++11 or later
- OpenCV (v4 or later)
- POSIX Threads (pthreads — available on most Unix/Linux systems)

---

## 🛠️ Compilation

Use the following command to compile (replace `image_converter.cpp` with your source file name):

```sh
g++ -o image_converter image_converter.cpp `pkg-config --cflags --libs opencv4` -pthread
```

---

## ▶️ Usage

Run the compiled program:

```sh
./image_converter
```

You will be prompted with:

```
Type image's path:
```

Enter the relative or absolute path to the image file (e.g. `images/sample.jpg`).

---

## 📄 How It Works

1. The image is loaded using OpenCV.
2. The image is split into 4 vertical sections (rows).
3. Each section is processed by a thread that converts pixels from BGR to grayscale using the formula:

   ```
   Gray = 0.11 * Blue + 0.59 * Green + 0.30 * Red
   ```

4. After all threads finish processing, the grayscale image is saved and displayed.

---

## 🪟 Output

- **Saved grayscale image:** `output_gray.jpg`
- **Two display windows:**
  - Original Color
  - Gray Scale

---

## ⚠️ Notes

- This program is built to run on **Linux** only.

## 📜 License

- This project is provided for educational and personal use.