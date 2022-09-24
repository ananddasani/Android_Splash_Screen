# Android_Splash_Screen
App With Splash Screen

This topic is a part of [My Complete Andorid Course](https://github.com/ananddasani/Android_Apps)

# Code

## Method 1 (Using Thread)

#### 1st Activity 
```
        //Make a Thread and use sleep for some 2000 milliseconds
        Thread thread = new Thread(){

            @Override
            public void run() {
                super.run();

                try {
                    sleep(4000);
                } catch (Exception e) {
                    e.printStackTrace();
                } finally {
                    Intent intent = new Intent(SplashScreen.this, MainActivity.class);
                    startActivity(intent);
                }
            }
        };
        thread.start();
```


## Method 2 (Using Handler)

#### SplashScreen.java
```
ImageView logo;
TextView appName, developerName;
public static int SPLASH_SCREEN_TIME = 3000;
    
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        //hide status bar before setting content view
        requestWindowFeature(Window.FEATURE_NO_TITLE);
        this.getWindow().setFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN, WindowManager.LayoutParams.FLAG_FULLSCREEN);

        setContentView(R.layout.activity_splash_screen);

        intiUI();

        new Handler().postDelayed(() -> {
            startActivity(new Intent(SplashScreen.this, MainActivity.class));
            finish();
        }, SPLASH_SCREEN_TIME);
    }

    private void intiUI() {
        logo = findViewById(R.id.logo);
        appName = findViewById(R.id.appName);
        developerName = findViewById(R.id.developerName);

        //Making Animation
        new CountDownTimer(1000, 1000) {
            @Override
            public void onTick(long millisUntilFinished) {
            }

            @Override
            public void onFinish() {
                developerName.setVisibility(View.VISIBLE);
                developerName.startAnimation(AnimationUtils.loadAnimation(SplashScreen.this, android.R.anim.slide_in_left));
            }
        }.start();
    }
```

# App Highlight
![Splash Screen App1](https://user-images.githubusercontent.com/74413402/192093337-f8695e01-6e79-48e1-8880-525ac578b6ee.png)
![Splash Screen App2](https://user-images.githubusercontent.com/74413402/192093341-030a97ac-539b-4bd5-9d5a-d39ac6f7a6ab.png)
![Splash Screen Code](https://user-images.githubusercontent.com/74413402/192093343-51128db9-5ec0-430b-8046-f443250f40bf.png)

