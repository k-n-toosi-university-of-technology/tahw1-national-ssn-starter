# TA HW 1 - National SSN Detector - 35 Points

[![Grader Status](YOUR_GRADER_BADGE)](YOUR_GRADER_BADGE)

YOUR_GRADER_BADGE looks like this: https://kntu-grader.herokuapp.com/minimal?repo=<REPO_NAME>&id=<YOUR_STUDENT_ID>



# Assignment discription

<div dir="rtl" align="right">
کد ملی شماره ای است 10 رقمی که از سمت چپ سه رقم کد شهرستان محل صدور شناسنامه ، شش رقم بعدی کد منحصر به فرد برای فرد دارنده شناسنامه در شهرستان محل صدرو و رقم آخر آن هم یک رقم کنترل است که از روی 9 رقم سمت چپ بدست می آید. برای بررسی کنترل کد کافی است مجدد از روی 9 رقم سمت چپ رقم کنترل را محاسبه کنیم

از آنجایی که درسیستم کد ملی معمولا قبل از کد تعدادی صفر وجود دارد.(رقم اول و رقم دوم از سمت چپ کد ملی ممکن است صفر باشد) و در بسیاری از موارد ممکن است کاربر این صفرها را وارد نکرده باشد و یا نرم افزار این صفرها را ذخیره نکرده باشد بهتر است قبل از هر کاری در صورتی که طول کد بزرگتر مساوی 8 و کمتر از 10 باشد به تعداد لازم (یک تا دو تا صفر) به سمت چپ عدد اضافه کنید. ساختار کد ملی 
در زیر نشان داده شده است


|ساختار کد       | رقم کنترل |  |  | |   9| رقم |سمت| چپ| کد| ملی   |
|:-------------:|:---------:|:----:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:--:|
|    موقعیت     |    1      |   2  | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |



1- برای محاسبه رقم کنترل از روی سایر ارقام ، هر رقم را در موقعیت آن ضرب کرده و حاصل را با هم جمع می کنیم.

2- مجموع بدست آمده از مرحله یک را بر 11 تقسیم می کنیم

3- اگر باقیمانده کمتر از 2 باشد ، رقم کنترل باید برابر باقیمانده باشد در غیر اینصورت رقم کنترل باید برابر یازده منهای باقیمانده باشد

ساختار کد شما باید به شکل زیر باشد. امضای متد تعریف شده را نمی توانید تغییر دهید و باید منطق برنامه را درون آن بنویسید. در صورت نیاز می توانید متد های خودتان را اضافه کنید.
</div>



```java
package ir.ac.kntu;

public class NationalIDDetector{

    public static boolean isValidID(String id){
        //write your logic here
    }

    public static void main(String[] args){
        //test your method
    }

}
```


# Example

<div dir="rtl" align="right">
آیا کد 7731689951 یک کد ملی معتبر است؟

برای این منظور کد

|ساختار کد       | رقم کنترل |  |  | |   9| رقم |سمت| چپ| کد| ملی   |
|:-------------:|:---------:|:----:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:--:|
|    ارقام کد   |    1      |   5  | 9 | 9 | 8 | 6 | 1 | 3 | 7 | 7 |
|    موقعیت     |    1      |   2  | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|محاسبه حاصل ضرب|      |   10  | 27 | 36 | 40 | 36 | 7 | 24 | 63 | 70 |

حاصل جمع ضرب ارقام 2 الی 10 را در موقعیت آنها محاسبه می کنیم

$$ 7*10+7*9+3*8+1*7+6*6+8*5+9*4+9*3+5*2=313 $$

$$ \frac{313}{11} =28 , R = 5 $$

چون باقیمانده برابر 5 و بزرگتر مساوی 2 است پس باید رقم کنترل این کد برابر 6 ( یازده منهای 5 برابر 6 )باشد.

با دقت در کد متوجه می شویم که رقم کنترل ورودی برابر 1 است پس کد مورد نظر به عنوان یک کد معتبر قابل قبول نیست.


# ورودی
ورودی یک رشته 10 رقمی است.
# خروجی
در صورتی که کد صحیح و معتبر باشد چاپ کنید : VALID

در غیر اینصورت چاپ کنید : IS NOT VALID    
    
</div>
