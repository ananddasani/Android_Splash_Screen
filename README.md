# Android_Splash_Screen
App With Splash Screen

# Code

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

# App Highlight

<img src="app_images/Splash Screen Code.png" width="1000" /><br>

<img src="app_images/Splash Screen App1.png" width="300" /><br>

<img src="app_images/Splash Screen App2.png" width="300" /><br>
