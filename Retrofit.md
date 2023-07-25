# Retrofit2, 사진 업로드 기능을 이용한 post 앱 개발하기

- Retrofit2는 안드로이드 앱에서 네트워크 통신을 쉽게 처리하기 위한 라이브러리입니다.



## 환경설정하기
- 먼저 Volley 작업때 사용했던 네트워크 연결 xml 파일과, 안드로이드매니패스트, build.gradle을 추가합니다.

  - 이후 앱(폰)에서 사진을 업로드하기 위해 파일 경로 설정 fileprovieder.xml 파일을 만들어줍니다
  - 
 ```Java
    <?xml version="1.0" encoding="utf-8"?>
<paths>
    <root-path
        name="root"
        path="." />

    <cache-path
        name="cache"
        path="." /> <!--Context.getCacheDir() 내부 저장소-->
    <files-path
        name="files"
        path="." /> <!--Context.getFilesDir() 내부 저장소-->

    <external-path
        name="external"
        path="."/>  <!--  Environment.getExternalStorageDirectory() 외부 저장소-->
    <external-cache-path
        name="external-cache"
        path="."/> <!--  Context.getExternalCacheDir() 외부 저장소-->
    <external-files-path
        name="images"
        path="Pictures" /> <!--  Context.getExternalFilesDir() 외부 저장소-->
</paths>
```

- 안드로이드매니패스트 작업도 실행합니다

![image](https://github.com/ijd1236/Android/assets/130967884/8cf3860a-b1c0-432a-997b-fbe392ea3286)

![image](https://github.com/ijd1236/Android/assets/130967884/0036a1a9-6926-4d6e-97e4-8f8dca580c38)








