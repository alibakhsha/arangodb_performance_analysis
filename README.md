# مقالهٔ تحلیل کارایی آرانگو‌دی‌بی (نسخهٔ فارسی)

## نمای کلی

این مخزن شامل نسخهٔ فارسی یک مقالهٔ پژوهشی است که کارایی پایگاه‌دادهٔ چندمدلی NoSQL به نام ArangoDB را در مقایسه با پایگاه‌داده‌های NoSQL تخصصی از جمله MongoDB، Neo4j، Redis و Apache Cassandra تحلیل می‌کند.

## محتویات

- `arangodb_performance_analysis_fa.tex` - فایل اصلی LaTeX برای نسخهٔ فارسی
- `references.bib` - فایل کتاب‌نامه با مراجع IEEE و کتاب‌های مرتبط
- `README.md` - این فایل

## پیش‌نیازها

برای کامپایل نسخهٔ فارسی، به **XeLaTeX** و بستهٔ `xepersian` نیاز دارید:

- **Linux (TeX Live)**:  
  ```bash
  sudo apt-get install texlive-full
  ```
  مطمئن شوید بسته‌های `xetex` و `xepersian` نصب هستند.
- **macOS (MacTeX)**:  
  MacTeX معمولاً `xelatex` و `xepersian` را به‌همراه دارد.
- **Windows (MiKTeX)**:  
  `xelatex` و بستهٔ `xepersian` را از طریق Package Manager نصب کنید.

## دستورالعمل کامپایل

### روش ۱: XeLaTeX + BibTeX (پیشنهادی)

```bash
xelatex arangodb_performance_analysis_fa.tex
bibtex arangodb_performance_analysis_fa
xelatex arangodb_performance_analysis_fa.tex
xelatex arangodb_performance_analysis_fa.tex
```

اجرای چندباره برای برطرف‌شدن ارجاعات و استنادات لازم است.

### روش ۲: latexmk (خودکار)

```bash
latexmk -xelatex arangodb_performance_analysis_fa.tex
```

### روش ۳: استفاده از Overleaf (آنلاین)

1. حساب کاربری در https://www.overleaf.com بسازید.
2. «New Project» → «Upload Project».
3. همهٔ فایل‌ها را آپلود کنید (`arangodb_performance_analysis_fa.tex` و `references.bib`).
4. از منوی «Menu» موتور را روی **XeLaTeX** تنظیم کنید.
5. روی «Recompile» کلیک کنید.

### خروجی

پس از کامپایل، فایل `arangodb_performance_analysis_fa.pdf` تولید خواهد شد.

## ساختار سند

1. چکیده
2. مقدمه
3. مروری بر ادبیات و کارهای مرتبط
4. معماری و ویژگی‌های ArangoDB
5. روش‌شناسی آزمایش‌ها
6. تحلیل کارایی و نتایج
7. کاربردها و سناریوهای عملی
8. بحث و تحلیل موازنه‌ها
9. نتیجه‌گیری
10. مراجع (سبک IEEE)

## سفارشی‌سازی

1. **اطلاعات نویسنده**: در بخش `\author{...}` در فایل `.tex` (نسخهٔ فارسی) نام و وابستگی خود را جایگزین کنید.
2. **افزودن شکل‌ها**: تصاویر را در همان پوشه قرار دهید و از الگوی زیر استفاده کنید:
   ```latex
   \begin{figure}[h]
   \centering
   \includegraphics[width=0.8\columnwidth]{filename.png}
   \caption{توضیح شکل}
   \label{fig:label}
   \end{figure}
   ```
3. **افزودن مراجع**: مدخل‌های جدید را به `references.bib` اضافه کنید.
4. **گسترش محتوا**: در صورت نیاز فصل‌ها و زیرفصل‌های بیشتری اضافه کنید.

## سبک استناد

این مقاله از سبک استناد IEEE استفاده می‌کند. نمونه‌ها:

- در متن: `\cite{key}`
- چند مرجع: `\cite{key1, key2, key3}`

## نکات مربوط به زبان فارسی

- از `xelatex` به‌همراه بستهٔ `xepersian` استفاده می‌شود.
- یک فونت فارسی متداول مانند `XB Niloofar`، `IRNazanin`، `XB Zar` یا هر فونت موجود روی سیستم شما باید در دستور `\settextfont` تنظیم شود.
- در صورت بروز خطا در مورد فونت، نام فونت را به فونتی که روی سیستم شما نصب است تغییر دهید.