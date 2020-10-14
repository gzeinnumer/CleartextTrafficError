<p align="center">
  <img src="https://images2.minutemediacdn.com/image/upload/c_crop,h_1351,w_2400,x_0,y_0/v1571796144/shape/mentalfloss/604599-gettyimages-1083893950.jpg?itok=om3ZU-xi" width="400"/>
</p>

<h1 align="center">
    CleartextTrafficError
</h1>

This error will happen if you using Android 9(SDK >= 28) and lastest.

#
#### Step 1.
**Manifest.** add permission ke file manifest. I recommend to use minimal SDK 21 on your `gradle`.

```xml
<manifest >

    <uses-permission android:name="android.permission.INTERNET" />

    <application
        android:networkSecurityConfig="@xml/network_security_config">

    </application>

</manifest>
```

#### Step 2.
Make directory `xml` on `res`.

<p align="center">
  <img src="![](https://github.com/gzeinnumer/CleartextTrafficError/blob/master/preview/CleartextTrafficError_1.JPG)" width="400"/>
</p>

#### Step 3.
Make file `network_security_config.xml` inside `res->xml`.

<p align="center">
  <img src="![](https://github.com/gzeinnumer/CleartextTrafficError/blob/master/preview/CleartextTrafficError_2.JPG)" width="400"/>
</p>

```xml
<?xml version="1.0" encoding="utf-8"?>
<network-security-config>
    <domain-config cleartextTrafficPermitted="true">
        <domain includeSubdomains="true">192.168.1.1</domain>
        <domain includeSubdomains="true">192.168.2.1</domain>
        <domain includeSubdomains="true">192.168.3.1</domain>
    </domain-config>
</network-security-config>
```
---

```
Copyright 2020 M. Fadli Zein
```