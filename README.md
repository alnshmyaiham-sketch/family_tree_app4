workflows:
  android-debug:
    name: Build Debug APK
    max_build_duration: 60
    environment:
      flutter: stable
      xcode: latest
      cocoapods: default
      java: 17
    scripts:
      - name: Install dependencies
        script: |
          flutter pub get
      - name: Build debug APK
        script: |
          flutter build apk --debug
    artifacts:
      - build/app/outputs/flutter-apk/app-debug.apk
