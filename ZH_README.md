# AndroidBasicLibs

#简书说明：http://www.jianshu.com/p/06d417b554ef

AndroidBasicLibs是一套android应用层依赖开发框架。将业务层无关的依赖进行了拆分。对第三方依赖进行二次封装解耦操作。系统架构采用了MVP模式+RxJava。具有快速集成、支持扩展和可维护性的特点。包含了（网络，图片加载，检查,IO，ect）和自定义控件。


# 你需要添加到项目中的话只需要如下集成。

```
  allprojects {
  	repositories {
		...
		maven { 
			url 'https://jitpack.io' 
		}
	}
}
```
  
  添加 dependency：

```
  dependencies {
       compile 'com.github.wwah.AndroidBasicLibs:basekit:0.3.3'
  }
```
添加 AndroidManifes:
```

    <application
      >
      ....
            <meta-data
            android:name="design_width"
            android:value="1280" />
        <meta-data
            android:name="design_height"
            android:value="800" />
    </application>

</manifest>


```
build.gradle:

```
build.gradle
 defaultConfig {
        minSdkVersion 19
        ....
        ｝
```
# tips

- 框架使用中集成了百分比布局所以在配置文件中要设定你的应用参考尺寸。参考尺寸的意思是设计师已px为单位切图的尺寸。
- 你可以选择是否要继承BaseKitApp到你的application中。它与原生的区别只是做了日志崩溃收集操作。
- 如果你打算使用本框架作为项目依赖最好将所有的Activity类继承BaseActivity ,该类已经解决了rxjava引起的内存泄漏的问题和全屏应用。 否则你也可以选择将BaseActivity的代码copy至自己的基类中实现。
- 业务的拆分模式可以参考APP中Module中的simpe,我们推荐你可以对业务模块进行拆分。每个模块中的活动、适配器、实体等是不相互干扰的。这样也方便后期的维护成本。
- 如果你觉得本框架依赖了太多你不需要的第三方框架，你可以clone本项目，在名称为common的Module中将不需要的依赖剔除。如果是商用项目我建议你最好不要直接依赖本框架。而是选择clone下来后改造。因为重度依赖会导致你不方便及时修改bug。



# 其他

- 目前而言这个项目缺少维护者，如果你有使用本项目，并在项目中发现了问题和你的好想法可以pull过来。
- 如果你有时间来维护本项目文档工作，我想也是极好的。
