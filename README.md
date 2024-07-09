# Yolov8-AndroidApp-NCNN

This is a sample NCNN Android project utilizing Yolov8 for object detection. It depends on the NCNN library and OpenCV.

- [NCNN](https://github.com/Tencent/ncnn)
- [OpenCV Mobile](https://github.com/nihui/opencv-mobile)

## How to Build and Run

### Step 1: Set Up NCNN
1. Download the latest `ncnn-YYYYMMDD-android-vulkan.zip` from the [NCNN releases page](https://github.com/Tencent/ncnn/releases).
2. Extract the contents into `app/src/main/jni`.
3. Update the `ncnn_DIR` path in `app/src/main/jni/CMakeLists.txt`:
    ```cmake
    set(ncnn_DIR "${CMAKE_SOURCE_DIR}/app/src/main/jni/ncnn-YYYYMMDD-android-vulkan")
    ```

### Step 2: Set Up OpenCV
1. Download `opencv-mobile-XYZ-android.zip` from the [OpenCV Mobile releases page](https://github.com/nihui/opencv-mobile).
2. Extract the contents into `app/src/main/jni`.
3. Update the `OpenCV_DIR` path in `app/src/main/jni/CMakeLists.txt`:
    ```cmake
    set(OpenCV_DIR "${CMAKE_SOURCE_DIR}/app/src/main/jni/opencv-mobile-XYZ-android")
    ```

### Step 3: Build the Project
1. Open the project in Android Studio.
2. Sync the project with Gradle files.
3. Build the project (`Build > Make Project`).
4. Run the app on an Android device with Vulkan support.

## Notes
- **Camera Efficiency**: Uses Android NDK camera for optimal performance.
- **Compatibility**: May crash on older devices lacking HAL3 camera interface.
- **Model Input Shape**: All models are modified to accept dynamic input shapes.
- **Performance**: Smaller models might run slower on GPU than on CPU.
- **FPS Considerations**: Lower frame rates in low light due to longer exposure times.

## References
- [ncnn-android-nanodet](https://github.com/nihui/ncnn-android-nanodet)
- [NCNN](https://github.com/Tencent/ncnn)
- [Ultralytics Assets Releases](https://github.com/ultralytics/assets/releases/tag/v0.0.0)
