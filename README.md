# Android_Splash_Screen
App With Splash Screen

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


## Method 1 (Using Handler)

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

<img src="app_images/Splash Screen Code.png" width="1000" /><br>

<img src="app_images/Splash Screen App1.png" width="300" /><br>

<img src="app_images/Splash Screen App2.png" width="300" /><br>
