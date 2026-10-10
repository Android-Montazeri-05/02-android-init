
# جزوه آموزشی: مقدمه برنامه‌نویسی موبایل با کاتلین و کامپوز

## ۱. مقدمه برنامه‌نویسی موبایل با کاتلین و کامپوز

کاتلین (`Kotlin`) زبان برنامه‌نویسی رسمی اندروید است که توسط شرکت JetBrains توسعه یافته و به دلیل ترکیب قدرت، سادگی، ایمنی در برابر خطاهای رایج (مثل Null Safety) و خوانایی بالا، جایگزین جاوا شده است.
از سوی دیگر، **Jetpack Compose** فریمورک مدرن و بومی گوگل برای ساخت رابط کاربری (UI) در اندروید است که به صورت کاملاً اعلامی (Declarative) با کاتلین نوشته می‌شود؛ یعنی به جای نوشتن کدهای پیچیده و سنتی XML، رابط کاربری را به کمک توابع کاتلین و به صورت بسیار ساده‌تر و سریع‌تر طراحی می‌کنید.

---

## ۲. معرفی اندروید استودیو (Android Studio)

اندروید استودیو محیط توسعه یکپارچه (IDE) رسمی برای ساخت برنامه‌های اندروید است که توسط گوگل و JetBrains بر پایه IntelliJ IDEA ساخته شده است. این محیط تمام ابزارهای لازم برای کدنویسی، طراحی UI، تست و دیباگ را در اختیار شما می‌گذارد.

### اجزای اصلی اندروید استودیو:

* **Editor (ویرایشگر کد):** محلی برای نوشتن و ویرایش کدهای Kotlin.


* **Layout Editor:** ابزار گرافیکی برای پیش‌نمایش و طراحی رابط کاربری (در کامپوز بیشتر کد UI نوشته می‌شود).


* **Project Structure:** درختار نمایشی فایل‌ها و پوشه‌های پروژه.


* **Build System (Gradle):** ابزاری قدرتمند برای مدیریت کتابخانه‌ها، کامپایل و بسته‌بندی اپلیکیشن.


* **Emulator (شبیه‌ساز):** اجرای برنامه در یک محیط مجازی شبیه‌سازی‌شده از گوشی روی کامپیوتر.


* **Logcat:** پنجره‌ای برای نمایش لاگ‌ها، خطاها (Errors) و اطلاعات اجرایی برنامه.


* **Android SDK Manager:** ابزاری برای دانلود و مدیریت نسخه‌های مختلف اندروید SDK.



---

## ۳. مفاهیم پایه: SDK و شبیه‌ساز (Emulator)

* **SDK (Software Development Kit):** مجموعه‌ای از ابزارها، کتابخانه‌های پایه، کامپایلرها و APIهایی است که اندروید استودیو برای تبدیل کدهای شما به یک فایل اجرایی (`.apk`) و تعامل با سخت‌افزار گوشی به آن‌ها نیاز دارد.


* **Emulator (شبیه‌ساز):** نرم‌افزاری است که سخت‌افزار و سیستم‌عامل اندروید را روی کامپیوتر شما بازسازی می‌کند تا بتوانید بدون نیاز به دستگاه فیزیکی، برنامه‌تان را در اندازه‌ها و نسخه‌های مختلف تست کنید.



---



## ۴. شروع کار با پروژه در اندروید استودیو

1. **ایجاد پروژه جدید:** انتخاب قالب **Empty Compose Activity** برای ساخت پروژه‌ای بر پایه Jetpack Compose.


2. **ساختار پوشه‌ها:**
* پوشه `src/main/java` یا `src/main/kotlin` برای کدهای منطقی کاتلین.


* پوشه `res` برای منابع غیرکدی مانند تصاویر، آیکون‌ها و رنگ‌ها.


* فایل `build.gradle` برای تنظیمات وابستگی‌ها (Dependencies) و نسخه‌های پروژه.




3. **نوشتن UI با Compose:** استفاده از توابع `@Composable` برای توصیف ظاهر برنامه.


4. **اجرا و دیباگ:** زدن دکمه‌ی سبز رنگ Run برای اجرا روی شبیه‌ساز و بررسی خروجی در Logcat.



---



## ۵. آشنایی با اجزای اصلی Jetpack Compose (به همراه مثال)

در کامپوز، رابط کاربری با ترکیب کامپوننت‌های مختلف ساخته می‌شود. در ادامه با پرکاربردترین عناصر یعنی `Text`، `Button`، `Row`، `Column` و `Modifier` آشنا می‌شوید.

### الف) کامپوننت متن (`Text`)

برای نمایش متن روی صفحه استفاده می‌شود.


```kotlin
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.unit.sp

@Composable
fun GreetingText() {
    Text(
        text = "سلام، خوش آمدید!",
        fontSize = 24.sp,
        color = Color.Blue
    )
}

```

### ب) کامپوننت دکمه (`Button`)

برای دریافت کلیک از کاربر و انجام یک عملیات استفاده می‌شود.

```kotlin
import androidx.compose.material3.Button
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable

@Composable
fun SimpleButton() {
    Button(onClick = {
        // کارهایی که هنگام کلیک روی دکمه انجام می‌شود
        println("دکمه فشرده شد!")
    }) {
        Text(text = "ورود به حساب")
    }
}

```

### ج) چیدمان عمودی و افقی (`Column` و `Row`)

برای مرتب‌سازی المان‌ها به صورت ستونی (بالا به پایین) یا سطری (چپ به راست) استفاده می‌شوند.

```kotlin
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable

@Composable
fun ProfileLayout() {
    // چیدمان ستونی
    Column {
        Text(text = "نام کاربری: علی")
        
        // چیدمان سطری در داخل ستون
        Row {
            Text(text = "وضعیت: ")
            Text(text = "آنلاین")
        }
    }
}

```

### د) اصلاح‌گر (`Modifier`)

مودیفایر ابزاری قدرتمند در کامپوز است که با آن می‌توانید ظاهر و رفتار کامپوننت‌ها (مثل اندازه، فاصله، رنگ پس‌زمینه، حاشیه و قابلیت کلیک‌پذیری) را تغییر دهید.

```kotlin
import androidx.compose.foundation.background
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.unit.dp
import androidx.compose.runtime.Composable

@Composable
fun BoxExample() {
    Box(
        modifier = Modifier
            .size(100.dp) // تعیین عرض و ارتفاع
            .background(Color.Red) // رنگ پس‌زمینه
            .padding(16.dp) // ایجاد فاصله داخلی
    )
}

```
