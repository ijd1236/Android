1. 앱 이름 바꾸는 방법
2. 안드로이드에서 로그 남기는 방법
3. 화면의 UI 위젯들을, 액티비티에서 가져다 사용하기 위한 방법
   a. UI위젯의 ID 값, 액티비티 클래스에서의 findViewByld 함수
4. 오픈소스 라이브러리를 안드로이드 스튜디오에 적용하는 방법
   a. build.grandle 의 dependencies 항목
5. TextView 의 속성들
  a. text, textColor, background, layout_margin, visibility, padding, gravity 등


# 안드로이드

## 안드로이드 설치

https://developer.android.com/studio

![image](https://github.com/ijd1236/Android/assets/130967884/eb6a855a-675a-483c-88a5-4ef9d37da505)

- 위의 링크에 들어가 안드로이드를 설치해줍니다.

## 프로젝트 만들기

- 설치가 완료되면

![20230705_103249](https://github.com/ijd1236/Android/assets/130967884/f71d64bc-6a42-456c-a44b-3231b67e5d50)

- 사용할 SDK Tools 를 클릭하고 설치해줍니다.

![image](https://github.com/ijd1236/Android/assets/130967884/cd396675-fada-4421-8416-23241bce515d)

- 설치가 완료되면 프로젝트를 생성해줍니다
  ![image](https://github.com/ijd1236/Android/assets/130967884/705d0259-460a-4745-8947-673988881452)

![image](https://github.com/ijd1236/Android/assets/130967884/b36b1cf7-44f5-4a78-88be-cdc74b077f4e)

- No Activity 선택 , 자바를 선택하고 finish로를 눌러만들어줍니다.
- 
![image](https://github.com/ijd1236/Android/assets/130967884/b5b304e7-61c1-4ca3-b908-df1adc7c7b0c)

- 프로젝트가 만들어졌습니다.

##  앱 작동을 위한 매니페스트 파일설정

- 매니페스트(manifests)는 안드로이드 애플리케이션의 구성 요소 및 애플리케이션에 대한 정보를 담고 있는 XML 파일입니다.
```Java
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Test"
        tools:targetApi="31" />

</manifest>
```

- 앱을 처음 만들면 다음과 같이 구성되어 있습니다.

- 앱을 동작하는 

- 


## 앱 이름 바꾸기

- 앱의 이름을 변경할 수 있습니다


![image](https://github.com/ijd1236/Android/assets/130967884/b2353e39-15bd-46f8-8c1a-8ffdb5432aed)


- app에 manifests -> AndroidManifest.xml 에서 android:label을 클리하고 컨트롤+엔터를 눌러들어갑니다.
 
![image](https://github.com/ijd1236/Android/assets/130967884/73741203-e7a8-4f77-814a-c2b1ef8cf329)

- 해당 부분이 앱 이름입니다. 초기 값은 프로젝트 이름으로 되어있으나 앱 이름을 수정해 줄 수 있습니다.



## 설정

## 화면 개발

- 안드로이드 순서는 화면(XML)-로직개발(JAVA)순으로 진행됩니다
- 화면 개발을 위해 사용할 폴더와 파일들을 넣어줍니다
  
![image](https://github.com/ijd1236/Android/assets/130967884/834fa40c-41f4-4384-a5e2-dd5d6403ef9a)

- 화면 개발은 res 폴더에서 진행됩니다.

- drawable에서는 화면에서 사용할 그림들을 넣습니다
- layout폴더의 activity_main 에서 에서 화면을 보면서 여러가지 설정할 수 있습니다
- raw는 새로만든 폴더로 지금은 음향 데이터가 저장됐습니다.
- values에서는 설정한 색, 이름 등이 저장됩니다

- res - > layout 폴더에 acctivity_main.xml에서 눈으로 보며 화면을 개발하고 여러 기능을 넣을 수 있습니다

  ![image](https://github.com/ijd1236/Android/assets/130967884/bddefe5d-c064-4435-944a-e0cfe88570f7)

![image](https://github.com/ijd1236/Android/assets/130967884/b7b269e3-1507-4929-aabd-6961f3228453)

- 좌측 Palette 에서 여러 기능들을 추가할 수 있습니다

![image](https://github.com/ijd1236/Android/assets/130967884/e7fa0653-31ba-4e8f-a7f1-80be3843c52c)

- 우측 Attribute에서는 추가한 기능들의 세부 설정을 할 수 있습니다

- 택스트를 설정해보겠습니다

![image](https://github.com/ijd1236/Android/assets/130967884/b73750fc-8b58-425a-89dd-caa880db063b)

- Palette 의 Text -> TextView를 드래그해서 앱 화면에 넣으면 다음과 같이 추가됩니다.

![image](https://github.com/ijd1236/Android/assets/130967884/686a0cbd-66ad-4d9f-95b6-ad61db9a299b)

- 생성한 TextView를 선택하고 우측 Attribute에서 해당 기능을 설정합니다
-  Layout에서 기+ 버튼을 눌러 해당 기능을 연결하고, 크기를 설정해줄 수 있습니다 (기능 키그 설정은 dp를 붙여야합니다.)
- 그리고 크기를 설정할때 wrap_content와 match_parent 라는게 있는데 wrap_content는 폭과 높이가 글자가 꼭 들어갈 정도로 설정하고
- match_parent는 화면 전체 길이에 맞춥니다.

![image](https://github.com/ijd1236/Android/assets/130967884/9adf6064-465d-46e7-8e93-8c58eca65fc4)

- CommonAttributes에서 텍스트 내용을 수정할 수 있습니다.

- 이외 여러가지 화면 설정이 가능합니다.


  ## 로직 개발

  



## 여러화면 구현하기


- 앱에서 여러 화면을 구현하게합니다 예를들어 버튼을 누르면 다른 화면으로 넘어가고 뒤로가기를 누르면 다시 이전 화면으로 돌아오게 합니다.

- 그러기 위해선 앱을 작동했을 때 어떻게 작동하는지 알아야합니다

- 우리가 앱을 작동했을때 액티비티에서 실행되는 메서드들이 있는데 이를 생명주기(Lifecycle) 메서드라고 합니다

![image](https://github.com/ijd1236/Android/assets/130967884/498f8ffc-2346-4748-915f-ac9670008a9d)  
구성



- 우리가 앱을 실행하면 onCreate, onStart, onResume 메서드가 작동합니다

- onCreate()는 액티비티가 처음 생성될 때 호출됩니다. 일반적으로 액티비티의 초기화 작업이나 UI 구성 요소의 설정 등을 수행합니다

- onStart()는 액티비티가 사용자에게 보여지기 전에 호출됩니다. 액티비티가 뷰를 생성하고 사용자에게 보여지기 직전에 필요한 작업을 수행할 수 있습니다

- onResume()은 액티비티가 전면에 나타나고 사용자와 상호작용하기 시작할 때 호출됩니다. 액티비티가 활성화된 상태이며 사용자 입력을 처리하거나 외부 리소스를 가져올 수 있는 위치입니다.

- 위의 세 메서드가 앱을 실행햇을때 실행되는 메서드들입니다.

- 앱에서 다른 화면으로 넘어가거나 앱을 잠시 내리거나 종료했을 때 실행되는 메서드들도 있습니다.

- onPause()는 액티비티가 일시적으로 중지되고 다른 액티비티가 화면을 가릴 때 호출됩니다. 현재 상태를 저장하거나 사용자 입력을 중지하는 등의 작업을 수행합니다.

- onStop()은 티비티가 더 이상 사용자에게 보여지지 않을 때 호출됩니다. 일반적으로 액티비티의 리소스를 정리하거나 실행 중인 애니메이션 등을 중지하는 작업을 수행합니다.

- 보통 앱에서 다른 화면으로 넘어갈 때 이 두 메서드가 실행됩니다

- onDestroy()는 액티비티가 소멸될 때 호출됩니다. 액티비티와 관련된 모든 리소스를 해제하고 메모리를 정리하는 작업을 수행합니다.

-  위의 세 메서드가 다른 화면으로 이동하거나 앱을 종료할 때 실행되는 메서스들입니다.

### 구현 예시

![image](https://github.com/ijd1236/Android/assets/130967884/d22abd25-3c3f-45b5-a8b0-fd5a03b69f1b)

![image](https://github.com/ijd1236/Android/assets/130967884/db4e5fdd-49db-4a09-8ef8-1608bf8c099c)


- 첫번째 화면에서 버튼을 누르면 두번째 화면으로 넘어가게 구현을 하려고 합니다

- 이 작업을 위해선 첫번째 액티비티에서 애플리케이션 구성 요소 간에 통신하고 작업을 수행하기 위한 메시지 객체인 Intent를 사용할 필요가 있습니다.
  

```Java
    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);


        button =findViewById(R.id.button);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                // SecondActivity를 실행시키고 싶다.

                // 새로운 액티비티를 실행시키고 싶으면
                // 인텐트를 만들어야 한다.
                // 이 액티비티가 다른 액티비티를 실행시킨다 라는 의미로
                // 파라미터를 설정해준다
                Intent intent = new Intent(MainActivity.this, SecondActivity.class);
                startActivity(intent);

            }
        });
```
- 다음과 같이 Intent를 이용한 코드를 작성하면
- 첫번째 화면에서 버튼을 누르면 두번째 화면으로 넘어갈 수 있습니다.
  
- 위에서 언급한 생명주기(Lifecycle) 메서드를 입력한 상태라면
- 첫번째 화면에서 버튼을 눌러 두번째 화면으로 넘어갈때
- 첫번째 액티비티(화면)는 onPause(정지)메서드가 실행되고
- 두번째 메서드의 화면을 나타낼때 실행되는 세개의 메서드 Create, Start, Resume 메서드가 실행된후 첫번째 메서드에
- 화면이 보여지지 않을때 실행되는 Stop() 메서드가 실행됩니다.
 
- 뒤로가기 버튼을 눌러 첫번째 화면으로 돌아오면
- 두번째 액티비티에서 onPause(정지), Stop()가 실행되고 
- 첫번째 액티비티에  Start, Resume메서드가 실행된후(Create는 처음 화면 구현때만 실행됩니다.)
- 두번째 액티비티를 완전히 소멸시키는 onDestroy()가 실행됩니다.
  
- 앱을 완전히 종료하면 첫번째 액티비티에 onPause(정지), Stop(), onDestroy() 가 실행되며 앱이 완전 종료됩니다.

### 데이터 전달하기

- 첫번째 액티비티(화면)에서 입력한 값을 두번째 화면에 전달하도록 하는 작업을 수행합니다.
- intent 객체에 데이터를 전달하는 메서드 putExtra()를 사용합니다.
  
![image](https://github.com/ijd1236/Android/assets/130967884/e2f1bfae-e332-489a-bdfa-42f3f9c1a6da)

- 첫번째 액티비티에 이름과 나이를 입력하면 두번째 액티비티에 그 내용을 출력하도록 합니다.

```Java
// 첫번째 액티비티
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                String name = editName.getText().toString().trim();
                String strAge = editAge.getText().toString().trim();

                Intent intent = new Intent(MainActivity.this, SecondActivity.class);
                int intAge=  Integer.parseInt(strAge);

                // 데이터를 전달하기 위해서, 인텐트에 담아줍니다.

                intent.putExtra("name",name);

                intent.putExtra("age",intAge);
            }
        });


```Java

// 두번째 액티비티
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);



        Log.i("LIFE SECOND", "두번째 액티비티의 onCreate 실행");

        // 받아오는 데이터가 있으면, 데이터를 받아온다.
        String name = getIntent().getStringExtra("name");  // getIntent() 첫번째 액티비티에서 intent에 설정한 키값을 이용해서 데이터를 가져옵니다
        int age = getIntent().getIntExtra("age", 0);       // get(형태)Extra를 사용할땐 형식을 맞춰줘야합니다.
        txtContent = findViewById(R.id.txtContent);
        txtFuture = findViewById(R.id.txtFuture);
        txtContent.setText("이름은"+name+"이고, 나이는"+age+"입니다");

        txtFuture.setText("10년후는"+(age+10)+"입니다");

    }
```

- 다음과 같은 코드를 입력하면

![image](https://github.com/ijd1236/Android/assets/130967884/f5955dd5-86ea-4e8a-8503-7172c60f02e7)

- 첫번째 액티비티에 정보를 입력하고 버튼을 누르면


![image](https://github.com/ijd1236/Android/assets/130967884/307dbd2e-7c56-4dbd-88f5-d24ebcd7cbf3)

- 두번째 액티비티에 다음과 같이 출력됩니다.

### 양방향 데이터 전달하기

- 단반향 데이터 전달이 아닌 양방향으로 데이터를 전달하는 방식입니다
```Java
    ActivityResultLauncher<Intent> launcher =
            registerForActivityResult(new ActivityResultContracts.StartActivityForResult(),
                    new ActivityResultCallback<ActivityResult>() {
                        @Override
                        public void onActivityResult(ActivityResult result) {
                            // 데이터를 받아오는 코드는, 여기에다만 작성하면된다.
                            if(result.getResultCode()  == 1){
                                int futuerAge = result.getData().getIntExtra("data", 0);
                                txtResult.setText(""+ futuerAge);

                            }

                        }
                    });

```
- 다음과 같은 코드를 사용합니다
- ActivityResultLauncher를 생성하고  registerForActivityResult() 메서드를 사용하여 이를 등록하는 코드입니다.
- ActivityResultLauncher는 액티비티나 프래그먼트에서 다른 액티비티나 프래그먼트를 시작하고 그 결과를 처리하는 데 사용됩니다.
- ActivityResultContracts.StartActivityForResult()를 사용하여 다른 액티비티를 시작하고, 그 결과를 처리하는 콜백인 ActivityResultCallback을 정의하여 등록합니다.
- registerForActivityResult() 메서드는 내부적으로 새로운 인스턴스를 생성하고, 해당 인스턴스를 반환하여 ActivityResultLauncher를 초기화합니다.
- new 키워드를 사용하여 새로운 인스턴스를 생성하는 것은 이 초기화 작업을 진행하는 과정입니다
- startActivity(intent) 가 아닌 launcher.launch(intent)를 사용해 실행해야합니다.

```java
    @Override
    public void onBackPressed() {

        // 백버튼을 눌렀을때 처리해주는 함수

        Log.i("LIFE SECOND", "두번째 액티비티의 onBackPressd 실행");

        // 나이를 10 더한 후에, 이 액티비티를 실행한 액티비티에게 데이터를 전달

        int data = age +10;

        Intent intent = new Intent();
        intent.putExtra("data",data);


        setResult(1, intent);

        super.onBackPressed();
```


### 데이터를 저장하고 가져오기

- 데이타를 전달하는게 아니라저장하고 가져오는 방식을 쓸 수 있습니다
- 이땐 SharedPreferences API를 사용합니다

```Java
                SharedPreferences sp = getSharedPreferences("Register_App",MODE_PRIVATE);
                SharedPreferences.Editor editor =sp.edit();
                editor.putString("email", email);
                editor.putString("password", password1);
```

- 다음과 같이 코드를 입력해서 객체를 생성하고 (이미 만들어진 메서드가 있기 때문에 new를 사용하지 않습니다)
- 객체 안에 데이터를 저장합니다 

```Java

        SharedPreferences sp = getSharedPreferences("Register_App", MODE_PRIVATE);
        String email =sp.getString("email","");

```

- 이후 저장된 데이터를 불러올 액티비티에서 다음과 같은 코드를 입력해 저장된 데이터를 불러옵니다.

1. SQLite3 데이터베이스 활용하는 방법
  a. SQLiteOpenHelper 클래스를 상속받아 처리하는 방법
3. 메뉴 아이콘 이미지 만드는 방법
4. RecyclerView 와 Adapter 를 이용하여 리스트를 화면에 표시하는 방법
5. 리사이클러뷰 어댑터에서, 새로운 액티비티를 실행하는 방법 a. Context
6. 리사이클러뷰에서, 몇번째 행을 눌렀는지 알 수 있는, 어댑터의 함수
a. getAdapterPosition()
7. 다른 액티비티로 데이터 전달시, 클래스의 객체를 전달하는 방법.
a. Serializable, putExtra(), getSerializableExtra()

## RecyclerView 사용하기

- RecyclerView는 안드로이드에서 리스트나 그리드와 같은 아이템 목록을 표시하기 위해 사용되는 위젯입니다. RecyclerView는 뷰의 재활용, 스크롤링 최적화, 유연한 레이아웃 관리 등 다양한 기능을 제공합니다.

![image](https://github.com/ijd1236/Android/assets/130967884/4427283d-3b4d-461b-88be-7f987fa2ba93)

- 다음과 같이 저장한 리스트를 출력 할 수 있게 만듭니다.



## 액션바 수정하기

![image](https://github.com/ijd1236/Android/assets/130967884/bd4ee546-01a5-4fdd-8b6d-6c28fa410f2c)

- 앱의 맨위 이름을 액션바라고 합니다.

- 기본은 앱의 이름과 동일하지만

- onCreate함수 부분에 getSupportActionBar().setTitle() 를 사용하여 액션바 이름을 수정할 수 있습니다.

## 액션바에 아이콘만들기

- 액션바에 아이콘을 만들고 아이콘을 클릭하면 입력한 기능을 수행하도록 합니다.
![image](https://github.com/ijd1236/Android/assets/130967884/183a1fbe-3d14-4b0a-89f5-a0054748a65e)

- 먼저 res에서 폴더를 하나 생성한 다음에 resource 파일도 생성해줍니다

![image](https://github.com/ijd1236/Android/assets/130967884/7b3bb63f-05e3-4ff1-82fb-7cde5ebe67d6)

- 여기서 메뉴 아이디 설정, 타이틀 설정, 아이콘 설정, 언제보일지 설정을 할 수 있습니다.

### 아이콘 기능 설정
```Java
    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // 액션바에 메뉴가 나오도록 설정한다.
        getMenuInflater().inflate(R.menu.main, menu);
        return true;


    }
```

- 다음 코드로 액션바에 메뉴(아이콘))이 나오게 합니다.

```Java
    @Override
    public boolean onOptionsItemSelected(@NonNull MenuItem item) {
        // 유저가 누른것이 +아이콘인 경우, AddActivity실행
        int itemId = item.getItemId();
        if(itemId == R.id.menuAdd){
            Intent intent = new Intent(MainActivity.this, AddActivity.class);
            launcher.launch(intent);
        }else if(itemId == R.id.menuAbout){

        }else if(itemId == R.id.menuShare){

        }
        return super.onOptionsItemSelected(item);
    }
}
```

- 다음과 같은 코드로 아이콘을 클릭시 실행될 코드들을 설정합니다.
  

   






