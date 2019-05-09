# 原文地址

<a href="https://www.cnblogs.com/a418120186/p/5856371.html">https://www.cnblogs.com/a418120186/p/5856371.html</a>

#  一、 config.xml配置

    1.在cordova5.0版本以后，需要安装cordova-plugin-splashscreen插件以后才能修改和设置App的启动页面。

    2.安装splashscreen插件：
        cordova plugin add cordova-plugin-splashscreen
        或
        cordova plugin add https://github.com/apache/cordova-plugin-splashscreen.git

# 二、  基本配置
    
    1.然后在你的config.xml文件中，添加以下代码

--------------------------------------------------------------------------------------------------------------------------------------

    <platform name="android">  
        <icon density="ldpi" src="res/icon/android/drawable-ldpi/icon.png" />
        <icon density="mdpi" src="res/icon/android/drawable-mdpi/icon.png" />
        <icon density="hdpi" src="res/icon/android/drawable-hdpi/icon.png" />
        <icon density="xhdpi" src="res/icon/android/drawable-xhdpi/icon.png" />
        <icon density="xxhdpi" src="res/icon/android/drawable-xxhdpi/icon.png" />
        <!-- 以下是欢迎页面，可根据需要进行添加 -->
        <splash density="land-hdpi" src="res/screen/android/splash-land-hdpi.png" />  
        <splash density="land-ldpi" src="res/screen/android/splash-land-ldpi.png" />  
        <splash density="land-mdpi" src="res/screen/android/splash-land-mdpi.png" />  
        <splash density="land-xhdpi" src="res/screen/android/splash-land-xhdpi.png" />  
        <splash density="port-hdpi" src="res/screen/android/splash-port-hdpi.png" />  
        <splash density="port-ldpi" src="res/screen/android/splash-port-ldpi.png" />  
        <splash density="port-mdpi" src="res/screen/android/splash-port-mdpi.png" />  
        <splash density="port-xhdpi" src="res/screen/android/splash-port-xhdpi.png" />  
    </platform>  
    <platform name="ios">  
        <!-- iOS 8.0+ -->  
        <!-- iPhone 6 Plus  -->  
        <icon src="res/icon/ios/icon-60@3x.png" width="180" height="180" />  
        <!-- iOS 7.0+ -->  
        <!-- iPhone / iPod Touch  -->  
        <icon src="res/icon/ios/icon-60.png" width="60" height="60" />  
        <icon src="res/icon/ios/icon-60@2x.png" width="120" height="120" />  
        <!-- iPad -->  
        <icon src="res/icon/ios/icon-76.png" width="76" height="76" />  
        <icon src="res/icon/ios/icon-76@2x.png" width="152" height="152" />  
        <!-- iOS 6.1 -->  
        <!-- Spotlight Icon -->  
        <icon src="res/icon/ios/icon-40.png" width="40" height="40" />  
        <icon src="res/icon/ios/icon-40@2x.png" width="80" height="80" />  
        <!-- iPhone / iPod Touch -->  
        <icon src="res/icon/ios/icon.png" width="57" height="57" />  
        <icon src="res/icon/ios/icon@2x.png" width="114" height="114" />  
        <!-- iPad -->  
        <icon src="res/icon/ios/icon-72.png" width="72" height="72" />  
        <icon src="res/icon/ios/icon-72@2x.png" width="144" height="144" />  
        <!-- iPhone Spotlight and Settings Icon -->  
        <icon src="res/icon/ios/icon-small.png" width="29" height="29" />  
        <icon src="res/icon/ios/icon-small@2x.png" width="58" height="58" />  
        <!-- iPad Spotlight and Settings Icon -->  
        <icon src="res/icon/ios/icon-50.png" width="50" height="50" />  
        <icon src="res/icon/ios/icon-50@2x.png" width="100" height="100" />  
        <!-- 以下是欢迎页面，可根据需要进行添加 -->
        <splash src="res/screen/ios/Default~iphone.png" width="320" height="480"/>  
        <splash src="res/screen/ios/Default@2x~iphone.png" width="640" height="960"/>  
        <splash src="res/screen/ios/Default-Portrait~ipad.png" width="768" height="1024"/>  
        <splash src="res/screen/ios/Default-Portrait@2x~ipad.png" width="1536" height="2048"/>  
        <splash src="res/screen/ios/Default-Landscape~ipad.png" width="1024" height="768"/>  
        <splash src="res/screen/ios/Default-Landscape@2x~ipad.png" width="2048" height="1536"/>  
        <splash src="res/screen/ios/Default-568h@2x~iphone.png" width="640" height="1136"/>  
        <splash src="res/screen/ios/Default-667h.png" width="750" height="1334"/>  
        <splash src="res/screen/ios/Default-736h.png" width="1242" height="2208"/>  
        <splash src="res/screen/ios/Default-Landscape-736h.png" width="2208" height="1242"/>  
    </platform>


--------------------------------------------------------------------------------------------------------------------------------------


# 其他配置

* 自动隐藏启动页面AutoHideSplashScreen（默认为：true）
    
    <preference name="AutoHideSplashScreen" value="true" />

* 显示启动页面的时间长度SplashScreenDelay(默认为：3000) 

    <preference name="SplashScreenDelay" value="3000" />
    
    *** 若想禁用启动页面，可设置为： ***
    <preference name="SplashScreenDelay" value="0"/>
    
    *** 如果是iOS平台上想禁止启动页面，还需要添加 ***
    <preference name="FadeSplashScreenDuration" value="0"/>

* 启动页面淡入淡出的效果，是否显示淡入淡出效果FadeSplashScreen(默认为：true)

    <preference name="FadeSplashScreen" value="false"/>

    *** 淡入淡出效果的执行时间长度FadeSplashScreenDuration(默认为：500) ***
    <preference name="FadeSplashScreenDuration" value="750"/>
    *** 注意：FadeSplashScreenDuration时间是包含在SplashScreenDelay的时间里的。 ***

* 启动页面是否允许旋转（默认为：true）
     <preference name="ShowSplashScreenSpinner" value="false"/>
     *** 插件还可以通过js代码调用，提供有以下两个方法： ***
        navigator.splashscreen.hide();//隐藏启动页面

        navigator.splashscreen.show();//显示启动页面

    在Android平台下的特殊设置
        <preference name="SplashMaintainAspectRatio" value="true|false" />
        <preference name="SplashShowOnlyFirstTime" value="true|false" />
         *** SplashMaintainAspectRatio：选填项，默认为false。当设置为true时，则不会拉伸图片来填充屏幕，会以图片原始比例显示图片。 ***
         *** SplashShowOnlyFirstTime：选填项，默认为true。当设置为false时，APP通过navigator.app.exitApp()代码退出app后，在下次打开APP时，还会显示启动页面。若为true时，就不会出现。 ***

# 三、图标文件夹内容

    1.根据上面的配置信息，你需要准备好你自己的app图标和启动画面png文件：
        
        *** 存放路径不是以www文件夹为依据，而是以当前项目文件夹为依据 ***

        projectRoot
            hooks
            platforms
            plugins
            www
                css
                img
                js
            res
                screen
                    android
                    ios
                icon
                    android
                    ios




