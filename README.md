# PermissionX

PermissionX是一个用于简化Android运行时权限用法的开源库

添加如下配置将PermissionX引入到你的项目中：

```groory
dependencies{
  ...
  implementation('com.permissionx.mashan:permissionx:1.0.0')
}
```

然后就可以使用如下语法接口来申请运行时权限了：

```kotlin
 PermissionX.request(this,
                android.Manifest.permission.CALL_PHONE,
                android.Manifest.permission.READ_CONTACTS) { allGranted, deniedList ->
            if (allGranted) {
                Toast.makeText(this, "All permission are granted", Toast.LENGTH_LONG).show()
            } else {
                Toast.makeText(this, "You denied $deniedList", Toast.LENGTH_SHORT).show()
            }
        }

```

同样，记得在Manifest.xml文件中添加权限

```xml
    <uses-permission android:name="android.permission.CALL_PHONE" />
    <uses-permission android:name="android.permission.READ_CONTACTS" />
```
