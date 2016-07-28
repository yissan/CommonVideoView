# CommonVideoView

a common view that can play videos


支持全屏切换，滑动快进快退、拖动加载。。


使用方法:

1、布局文件中声明控件 

~~~
<com.qiangyu.test.commonvideoview.CommonVideoView
        android:id="@+id/common_videoView"
        android:layout_width="match_parent"
        android:layout_height="300dp" />

~~~

2、获取到控件设置视频地址

~~~
public class MainActivity extends AppCompatActivity {

    CommonVideoView videoView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.content_main);
        Toolbar toolbar = (Toolbar) findViewById(R.id.toolbar);
        setSupportActionBar(toolbar);
        videoView = (CommonVideoView) findViewById(R.id.common_videoView);
        videoView.start("你的服务器视频地址");
    }



    @Override public void onConfigurationChanged(Configuration newConfig) {
        super.onConfigurationChanged(newConfig);
        if (newConfig.orientation == Configuration.ORIENTATION_LANDSCAPE) {
            videoView.setFullScreen();
        }else {
            videoView.setNormalScreen();
        }
    }
}
~~~

3、最后为了防止你的Activity在横竖屏切换的时候重新创建别忘记在AndroidManifest.xml文件里面配置 
Android:configChanges=”orientation|screenSize|screenLayout”


