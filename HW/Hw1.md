
# سؤال 0

بعد از مطالعه [آداب‌نامه انجام تمرین‌های درسی](https://docs.ce.sharif.edu/rules/ethics)، علت نقض یا عدم نقض آداب‌نامه را در هر یک موارد زیر **به طور مختصر** بیان کنید.

1. الیاس و بابک برای حل یک سؤال با هم مشورت کرده و به یک پاسخ مشترک رسیده‌اند. آن‌ها این پاسخ را ارسال می‌کنند و مشورت خود را نیز در آن اعلام می‌کنند.
1. کیانا پاسخ خود به سؤالات تمرین را در گروهی با دیگران به اشتراک می‌گذارد و تأکید می‌کند از آن کپی نشود و تنها برای چک کردن و ایده کلی استفاده شود.
1. هوشنگ، ناراحت از اینکه پاسخ یک سؤال در اسلایدهای درس نیست، آن را از یک چت‌بات می‌پرسد و بعد از اینکه جواب را به طور کامل متوجه شد، پاسخ خود را مشابه آن می‌نویسد، بدون اینکه عیناً آن را کپی کرده باشد.
1. مانا و مونا در مورد تمرین درس با هم صحبت می‌کنند و مونا رویکرد خود برای حل یک سؤال را توضیح می‌دهد. مانا با الهام گرفتن از ایده مونا، به طور مستقل پاسخ خود را می‌نویسد و همفکری خود با مونا را نیز ذکر می‌کند.

----------

# سؤال 1

فرض کنید
$h:\{0,1\}^*\rightarrow \{0,1\}^n$
یک تابع چکیده‌ساز برخوردتاب(Collision-resistant) دلخواه است. در هر یک از موارد زیر، برخوردتاب بودن $g$ را بررسی و ادعای خود را اثبات کنید.
> راهنمایی: برای اثبات برخوردتاب بودن، از برهان خلف و برای اثبات برخوردتاب نبودن، از مثال نقض استفاده کنید.
1. $g(x)=h(x) \oplus h(\bar{x})$

	$\bar{x}:$ مکمل دودویی
1. $g(x_1\dots x_m)=x_1 \| h(x_2\dots x_m)$

	$x_i\in \{0,1\}, m \ge 2$
1. $g(x_1\dots x_{2m})=h((x_1\dots x_m) \oplus (x_{m+1}\dots x_{2m}))$

	$x_i\in \{0,1\}, m \ge 1$
1. $g(x)=h(0\| x) \oplus h(1 \| x)$
1. $g(x)=h(h(x))$

----------
# سؤال 2

برای امضای تراکنش در بیتکوین از الگوریتم ECDSA استفاده می‌شود. توضیح این الگوریتم را می‌توانید در [این لینک](https://en.bitcoin.it/wiki/Elliptic_Curve_Digital_Signature_Algorithm) مطالعه کنید.

1. اگر $(r,s)$ یک امضای معتبر باشد، نشان دهید $(r,-s)$ هم معتبر است.
1. توضیح دهید اگر از مقدار یکسان $k$ برای امضای دو پیام متفاوت استفاده شود، چگونه می‌توان کلید خصوصی را از این دو امضاء استخراج کرد.
> راهنمایی: اختلاف مقدار $s$ از دو امضاء را محاسبه کنید.
1. اگر پیام امضاشده را با $m$ نشان دهیم، طبق تعریف اصلی الگوریتم، مقدار $s$ در امضاء به صورت زیر محاسبه می‌شود:
$$s=k^{-1}(\textrm{dSHA256}(m)+r\times d_A) \mod n$$
حال فرض کنید $m$ را یک عدد در نظر  گرفته و الگوریتم را به صورت زیر تغییر دهیم:
$$s=k^{-1}(m+r\times d_A)\mod n$$
نشان دهید در این نسخه تغییر یافته، بدون داشتن کلید خصوصی $d_A$، می‌توان امضای معتبر برای یک پیام ساخت.
> راهنمایی: فرض کنید برای $\alpha$ دلخواه داریم: $k=d_A+\alpha$؛ سپس مقدار $m$ را طوری انتخاب کنید که $r,s$ معتبر بدون دانستن $d_A$ قابل تعیین باشند.

----------
# سؤال 3
جدول زیر ویژگی‌های 3 نمایش متفاوت پول را با هم مقایسه می‌کند. ثابت یا متغیر بودن هر ویژگی در طی انجام تراکنش تعیین می‌شود.

| نمایش پول | شناسه | ارزش | صاحب |
|:---:|:---:|:---:|:---:|
| UTxO | متغیر | دلخواه | متغیر |
| اسکناس | ثابت | ثابت | متغیر |
| حساب بانکی | ثابت | دلخواه | ثابت |

این سه روش را بر اساس هر یک معیارهای آورده شده در ادامه با هم مقایسه کنید. برای هر مقایسه، توجیه خود را ارائه دهید.

1. حجم ذخیره‌سازی سمت کاربر و سرور
1. امکان انجام تراکنش همزمان
1. سربار هماهنگی انجام تراکنش در محیط توزیع شده(پول‌ها در سرورهای متفاوت مدیریت شوند)
1. حریم خصوصی کاربران(امکان پیوند و ردگیری تراکنش‌ها)

----------

# سؤال 4

با مراجعه به [کد منبع آخرین نسخه کلاینت بیتکوین](https://github.com/bitcoin/bitcoin/blob/master/src/kernel/chainparams.cpp#L137)، به سؤالات زیر پاسخ دهید.
1. پاسخ‌های یکی از DNS Seed ها به درخواست‌های مکرر را بررسی کنید. آیا آدرس‌های برگردانده شده یکسان و متناسب با موقعیت جغرافیایی هستند؟ این رفتار را با عملکرد متداول DNS ها مقایسه و توجیه کنید.
1. فرض کنید یک مهاجم  با انجام حمله مرد میانی، تمام پاسخ‌های DNS Seed ها را طوری تغییر دهد که تنها گره‌های تحت کنترل مهاجم به عنوان پاسخ برگردانده شوند. گره‌های تحت کنترل مهاجم طوری وانمود می‌کنند که طول زنجیره بلوکی بسیار کوتاه‌تر از اندازه واقعی آن است؛ بدین ترتیب یک نسخه کوچک از شبکه بیتکوین ایجاد می‌شود. با این نوع حملات چطور مقابله شده است؟
1. شرایط مشابه قسمت قبل را در نظر بگیرید، با این تفاوت که مهاجم قصد تغییر در زنجیره بیتکوین را ندارد و تنها قصد شناسایی و نقض حریم خصوصی افراد را داشته باشد. آیا استفاده از الگوریتم Perigee در این شرایط کمک می‌کند؟ الگوریتم Dandelion چطور؟


----------

# سؤال 5

با استفاده کاوشگر [BTC mempool](https://btcmempool.org/) به سؤالات زیر پاسخ دهید.

1. حداقل چند استخر استخراج باید همکاری کنند تا حمله %51 انجام شود؟
1. با مشاهده نمودار میزان سختی و قدرت پردزشی شبکه در یک سال گذشته، ارتباط میان این دو را به طور مختصر توضیح دهید.
1. با توجه به میزان سختی بلوک 883008، حداقل تعداد صفر ابتدایی مورد انتظار در نمایش دودویی چکیده بلوک را بدست آورید و با مقدار چکیده مقایسه کنید. آیا اختلاف موجود نشان دهنده اتلاف قدرت پردازشی است؟
1. متوسط قدرت پردازشی شبکه را در بازه زمانی بین دو بلوک 883008 و 885023 تخمین بزنید.
>راهنمایی: میزان سختی در این بازه زمانی ثابت است و با در نظر گرفتن تعداد بلوک استخراج شده، می‌توان قدرت شبکه را تخمین زد.
1. باتوجه به اینکه میزان سختی طوری تنظیم می‌شود که به طور میانگین هر بلوک در 600 ثانیه تولید شود، سختی بلوک 885024 را از طریق محاسبه به دست آورید و با مقدار ثبت شده در کاوشگر مقایسه کنید.
>راهنمایی: از نسبت زمان مورد انتظار برای تولید یک بلوک به متوسط زمان صرف شده برای تولید هر بلوک در بازه بین دو بلوک اشاره شده در بخش قبل استفاده کنید. 
1. اگر سختی را طوری تعیین کنیم که به طور میانگین هر ثانیه یک بلوک تولید شود، چه مشکلی ممکن است پیش بیاید؟ آیا این کار مزیتی هم دارد؟

----------

# سؤال 6
با استفاده از [مستندات بیتکوین](https://en.bitcoin.it/wiki/Script) به سؤالات زیر پاسخ دهید.

1. گواه(Witness) معتبری برای اسکریپت زیر ارائه دهید. برای خوانایی بهتر، اسکریپت در چند خط نوشته شده است.
```
OP_TUCK OP_OVER
OP_DUP OP_ADD OP_SWAP OP_SUB OP_15 OP_EQUALVERIFY
OP_SUB OP_5 OP_EQUAL
```

1. اسکریپت معادل برای امضای چندگانه زیر، بدون استفاده از دستور `OP_CHECKMULTISIG` بنویسید؛ سپس با فرض داشتن امضای معتبر برای کلیدهای `pk1` و `pk3`، گواه معتبری برای هر دو اسکریپت اصلی و معادل ارائه کنید.
> راهنمایی: از `OP_ROT` و `OP_ADD`و `OP_SWAP` استفاده کنید.
```
OP_2 <pk4> <pk3> <pk2> <pk1> OP_4 OP_CHECKMULTISIG
```

1. یک مادربزرگ می‌خواهد به نوه‌اش بیتکوین بدهد؛ امّا می‌خواهد تا قبل از 18 سالگی، نوه‌اش نتواند آن را خرج کند. برای این کار دو روش وجود دارد:
	- تراکنش انتقال بیتکوین به نوه با قفل زمانی(timelock) امضاء شده و به او داده شود.
	- بیتکوین‌های هدیه به یک UTxO منتقل شوند که فقط بعد از روز تولد 18 سالگی و فقط توسط نوه قابل خرج کردن باشد.

 روش اوّل مناسب نیست و از آن استفاده نمی‌شود. حداقل دو ضعف این روش را بیان کنید. سپس اسکریپت قفل کننده UTxO مقصد در روش دوم را با فرض اینکه تولد 18 سالگی نوه روز 1 ژانویه 2026 است، بنویسید و گواه معتبری نیز برای آن ارائه دهید.

----------

# سؤال 7
نوع چکیده امضاء(Signature Hash Type) برای مشخص کردن بخش‌های امضاشده در یک تراکنش استفاده می‌شود. می‌توانید در [این لینک](https://wiki.bitcoinsv.io/index.php/SIGHASH_flags) در مورد آن مطالعه کنید. در هر یک از شرایط زیر، راهکاری با استفاده از نوع چکیده امضای مناسب پیشنهاد دهید و انتخاب خود را توجیه کنید.

1. نوه مادربزرگِ سؤال قبل نگران است تا زمانی که 18 ساله شود ممکن است کلید خصوصی کیف پول خود را گم کرده و هدیه از دست برود؛ در نتیجه تصمیم می‌گیرد یک کیف پول حضانتی مبتنی بر خدمات ابری گرفته و با استفاده از یک تراکنش، هدیه را به کیف پول جدید خود انتقال دهد. این تراکنش در حال حاضر به دلیل قفل زمانی، در شبکه پذیرفته نمی‌‎شود ولی نوه حاضر است در ازای پرداخت مقدار مشخصی از هدیه خود، این تراکنش توسط سایرین نگهداری و بعد از 18 سالگی‌اش ثبت شود. این کار چگونه قابل انجام است؟
1. مغازه‌داری از یک کیف پول گرم برای نگهداری درآمدهای روزانه و از یک کیف پول سخت‌افزاری سرد برای پس‌انداز استفاده می‌کند. او تصمیم به خرید ماشین می‌گیرد، امّا نمی‌خواهد کیف پول سرد را از محل نگهداری آن خارج کند. همچنین با توجه به اینکه ممکن است جست‌وجو برای ماشین و خرید آن چند روز طول بکشد، نمی‌خواهد مقدار زیادی بیتکوین در کیف پول گرم خود نگهداری کند؛ در نتیجه او می‌خواهد تا زمان قطعی شدن معامله، بیتکوین در کیف پول سرد باقی بماند. دقت کنید مغازه‌دار، قیمت ماشین و آدرس فروشنده را از قبل **نمی‌داند**. این مغازه‌دار محتاط چطور ماشین بخرد؟
1. اگر مغازه‌دار بخش قبل، قیمت دقیق ماشین را از قبل **بداند** امّا آدرس فروشنده را فقط پای معامله بفهمد، چگونه می‌تواند نسبت به بخش قبل بهتر عمل کند؟


#  قسمت عملی

در این سؤال یک پروتکل معامله با کمک امین(Escrow) پیاده‌سازی و با استفاده از شبکه محلی تست بیتکوین، اجرا می‌شود. به نکات زیر در تحویل و پاسخ‌دهی توجه کنید:

- نسخه کامل و قابل اجرای کد (بدون خطای اظهار) را به عنوان پاسخ ارسال کنید. می‌توانید پاسخ هر بخش را در فایل جداگانه یا تمام آن‌ها را در یک فایل پیاده‌سازی کنید.
- پاسخ خود را می‌توانید به صورت اسکریپت پایتون(py.) یا دفترچه ژوپیتر(ipynb.) ارسال کنید.
- پاسخ به سؤالاتی که در میان مراحل پیاده‌سازی مطرح شده و همچنین خروجی اجرای هر بخش را به صورت تصویر یا متن ارائه دهید.
- پاسخ این سؤال را به همراه پاسخ سؤالات نظری، در یک فایل Zip ارسال کنید. 

---

# راه‌اندازی محیط اجرا

ابتدا 28.1 Bitcoin Core متناسب با سیستم عامل خود را از [این لینک](https://bitcoincore.org/bin/bitcoin-core-28.1/) دریافت و در محل دلخواه `BITCOIN_ROOT` نصب کنید. سپس [این فایل Zip](https://my.sharif.edu/s/EfsmCy7RF2doSqx) را که حاوی کد محیط تست بیتکوین است، دریافت و در `BITCOIN_ROOT` قرار دهید. در نهایت نام پوشه `BITCOIN_ROOT/bin` را به `BITCOIN_ROOT/src` تغییر دهید. اکنون ساختار کلی محل نصب بیتکوین به صورت زیر است:
```
BITCOIN_ROOT
└─ src
|     bitcoind,bitcoin-cli,...
└─ test
|  |  config.ini
|  └─ functional 
└─ share
```

در فایل `config.ini` آدرس مطلق(Absolute path) معادل `BITCOIN_ROOT` را جایگزین کنید. برای اطمینان از صحت انجام تمام مراحل، قطعه کد زیر را در محیط پایتون اجرا کنید.

```python
import sys
PATH_BITCOIN_TEST = BITCOIN_ROOT + "/test/functional"
sys.path.insert(0, PATH_BITCOIN_TEST)

from test_framework.test_shell import TestShell

test = TestShell().setup(num_nodes=1, setup_clean_chain=True)
test.shutdown()
```

در صورت اجرای صحیح، عبارت `Tests successful` در انتهای خروجی خواهد بود. لازم به ذکر است کدهای تست از [مخزن گیتهاب Bitcoin Core](https://github.com/bitcoin/bitcoin) برداشته شده است. در صورتی که خودتان با استفاده از مخزن کامپایل کنید، نیازی به تغییر فایل `config.ini` نیست. اجرای دستور `test.shutdown()` در انتهای کار برای اتمام اجرا انجام می‌شود و در پیاده‌سازی خود می‌توانید با ساختار `try-catch` آن را انجام دهید.

---

# پیاده‌سازی نسخه 1 پروتکل معامله
نسخه اولیه پروتکل از یک امضای چندگانه برای وابسته کردن نتیجه پرداخت به توافق اکثریت استفاده می‌کند. تصویر زیر فرایند کلی معامله با کمک امین را در شرایطی که هر دو طرف معامله به تعهد خود عمل کردند و نزاعی رخ نداده، نشان می‌دهد.

![توضیح تصویر](https://my.sharif.edu/s/CwqsxjEXEdqSDLE/preview)

برای پیاده‌سازی از کتابخانه `python-bitcoin-utils` استفاده شده است که برای نصب و مطالعه مستندات آن می‌توانید به این [مخزن گیتهاب](https://github.com/karask/python-bitcoin-utils) مراجعه کنید. همچنین برای مطالعه در مورد واسط برنامه‌نوسی گره بیتکوین می‌توانید از [این لینک](https://developer.bitcoin.org/reference/rpc/index.html) استفاده کنید. جهت سادگی پیاده‌سازی، کدهای ارائه شده در این تمرین بر اساس نسخه اولیه و منسوخ(Legacy) تراکنش‌ها هستند. نیازی به پیاده‌سازی با SegWit یا Taproot وجود ندارد.

قطه کد زیر، پیاده‌سازی حالت نمایش داده‌شده در شکل فوق را نشان می‌دهد. در این کد، الیس(خریدار) با استخراج در شبکه، 50 بیتکوین بدست آورده و مقدار 0.11 از آن را به امضای چندگانه منتقل کرده است. سپس با فرض اینکه کوله‌پشتی خریداری شده به دست الیس رسیده است، او و باب(فروشنده) با امضای خود این موضوع را تأیید کردند و پول به باب منتقل شده است.
```python
import sys, random
from bitcoinutils.keys import PrivateKey
from bitcoinutils.script import Script
from bitcoinutils.utils import to_satoshis
from bitcoinutils.transactions import Transaction, TxInput, TxOutput

PATH_BITCOIN_TEST = BITCOIN_ROOT + "/test/functional"
sys.path.insert(0, PATH_BITCOIN_TEST)

from test_framework.test_shell import TestShell

random.seed(14032)
test = TestShell().setup(num_nodes=1,
                         setup_clean_chain=True,
                         randomseed=14032)
node = test.nodes[0]

alice_privkey = PrivateKey(b=random.randbytes(32))
alice_pubkey = alice_privkey.get_public_key()
alice_address = alice_pubkey.get_address()
bob_privkey = PrivateKey(b=random.randbytes(32))
bob_pubkey = bob_privkey.get_public_key()
bob_address = bob_pubkey.get_address()
judge_privkey = PrivateKey(b=random.randbytes(32))
judge_pubkey = judge_privkey.get_public_key()
judge_address = judge_pubkey.get_address()

fund_block = node.generatetoaddress(nblocks=100,
                                    address=alice_address.to_string(),
                                    invalid_call=False)[0]
fund_txid = node.getblock(blockhash=fund_block, verbosity=1)['tx'][0]

escrow_script = Script()
escrow_input = TxInput(fund_txid, 0)
escrow_tx = Transaction([escrow_input],
                        [TxOutput(to_satoshis(.11), escrow_script),
                         TxOutput(to_satoshis(50 - .12),
                                  alice_address.to_script_pub_key())])
escrow_input.script_sig = Script()
result = node.testmempoolaccept(rawtxs=[escrow_tx.serialize()])[0]
assert result['allowed'], f"escrow1 failed: {result['reject-reason']}"
print('escrow1', result)
escrow_txid = node.sendrawtransaction(escrow_tx.serialize())

payment_input = TxInput()
payment_tx = Transaction([payment_input],
                         [TxOutput(to_satoshis(.1099),
                                   bob_address.to_script_pub_key())])
payment_input.script_sig = Script()
result = node.testmempoolaccept(rawtxs=[payment_tx.serialize()])[0]
assert result['allowed'], f"payment1 failed: {result['reject-reason']}"
print('payment1', result)
```

> **وظیفه 1**: تراکنش ساخت وجه امانی را تکمیل کنید.

>  **وظیفه 2**: تراکنش پرداخت به فروشنده را، وقتی که الیس و باب هر دو موافق هستند، تکمیل کنید.

> **سؤال 1**: در ابتدا 100 بلوک توسط الیس استخراج شده است. این تعداد را به مقدار کمتری تغییر دهید. علت وقوع خطا بعد از این تغییر چیست؟ چرا چنین قانونی در بیتکوین تعریف شده است؟

>**سؤال 2**: کارمزد هر یک از دو تراکنش `fund_tx` و `payment_tx`، بدون در نظر گرفتن سوبسید بیتکوین، چقدر است؟


دو طرف معامله همیشه به تعهدات خود عمل نمی‌کنند. فرض کنید الیس بعد از دریافت کوله‌پشتی، از پرداخت امتناع کند. در قطعه کد زیر، باب با همکاری داور معامله، مبلغ پرداختی را دریافت می‌کند. داور معامله هم بخشی از مبلغ را به عنوان کارمزد دریافت می‌کند.

```python
dispute_input = TxInput()
dispute_tx = Transaction([dispute_input], [])
dispute_input.script_sig = Script()
result = node.testmempoolaccept(rawtxs=[dispute_tx.serialize()])[0]
assert result['allowed'], f"dispute1 failed: {result['reject-reason']}"
print('dispute1', result)
```

>**وظیفه 3**: تراکنش رسیدگی به نزاع را تکمیل کنید، طوری که 0.002 بیتکوین کارمزد داور و 0.001 بیتکوین کارمزد تراکنش باشد.

>**سؤال 3**: با تغییر در ترتیب انجام عملیات‌های پروتکل، این امکان را فراهم کنید که باب بدون نیاز به آنلاین بودن در زمان رسیدگی به نزاع، در صورت تأیید داور، وجه امانی را دریافت کند.

---
# پیاده‌سازی نسخه 2 پروتکل معامله
یکی از ضعف‌های نسخه 1 پروتکل، عدم اختصاص کارمزد به داور در صورت عدم رخ‌دادن نزاع است. این امر باعث انگیزه برای تبانی داور است. همچنین مطلوب است پرداخت کارمزد تنها بعد از اتمام معامله انجام شود. یک راهکار استفاده از [قفل چکیده(Hashlock)](https://en.bitcoin.it/wiki/Hashlock) است. برای این کار، اسکریپت وجه امانی طوری طراحی می‌شود که برای خرج کردن آن، علاوه بر امضای چندگانه، نیاز به رمز یک‌بار مصرف نیز وجود داشته باشد. دو طرف معامله، قبل از ثبت آن توسط خریدار، با استفاده فرایندی مانند [توافق کلید دیفی هلمن](https://en.wikipedia.org/wiki/Elliptic-curve_Diffie%E2%80%93Hellman) بر سر این رمز توافق می‌کنند. چنانچه از رمز یکسان برای قفل کردن کارمزد داور هم استفاده شود، بعد از اتمام معامله و پرداخت وجه امانی به فروشنده یا عودت آن به خریدار، رمز می‌تواند به داور داده شود تا کارمزد خود را تحویل بگیرد.

قطعه کد زیر پیاده‌سازی این نسخه از پروتکل را نشان می‌دهد. معامله انجام شده مشابه بخش قبل است، با ین تفاوت که کارمزد داور به یک UTxO جداگانه منتقل شده و به دلیل  غیر استاندارد بودن اسکریپت نسخه 2، از [P2SH](https://en.bitcoin.it/wiki/Pay_to_script_hash) استفاده شده است. همچنین برای وجه امانی، از باقی‌مانده موجودی الیس در تراکنش `escrow_tx` بخش قبل استفاده شده است.

```python
otp = random.randbytes(4)
escrow2_script = Script()
fee2_script = Script()
escrow2_input = TxInput(escrow_txid, 1)
escrow2_tx = Transaction([escrow2_input], [
  TxOutput(to_satoshis(.11), escrow2_script.to_p2sh_script_pub_key()),
  TxOutput(to_satoshis(.002), fee2_script.to_p2sh_script_pub_key()),
  TxOutput(to_satoshis(50 - .24), alice_address.to_script_pub_key())])
escrow2_input.script_sig = Script()
result = node.testmempoolaccept(rawtxs=[escrow2_tx.serialize()])[0]
assert result['allowed'], f"escrow2 failed: {result['reject-reason']}"
print('escrow2', result)
escrow2_txid = node.sendrawtransaction(escrow2_tx.serialize())

payment2_input = TxInput()
fee2_input = TxInput()
payment2_tx = Transaction([payment2_input, fee2_input], [
   TxOutput(to_satoshis(.1099), bob_address.to_script_pub_key()),
   TxOutput(to_satoshis(.002), judge_address.to_script_pub_key())
])
payment2_input.script_sig = Script()
fee2_input.script_sig = Script()
result = node.testmempoolaccept(rawtxs=[payment2_tx.serialize()])[0]
assert result['allowed'], f"payment2 failed: {result['reject-reason']}"
print('payment2', result)
```


>**وظیفه 4**: تراکنش ساخت نسخه 2 وجه امانی را تکمیل کنید.

>**وظیفه 5**: تراکنش پرداخت به فروشنده و برداشت کارمزد توسط داور را، در شرایطی که رمز یک‌بار مصرف به او داده شده است، تکمیل کنید.

>**سؤال 4**: آیا ممکن است رمزعبور استفاده شده برای وجه امانی معامله با رمز عبور کارمزد داور متفاوت باشد و داور نتواند کارمزد خود را دریافت کند؟

>**سؤال 5**: اگر پرداخت وجه امانی با توافق دو طرف به فروشنده انجام شود و معامله بدون ارسال رمز به داور تمام شود، داور چگونه می‌تواند کارمزد خود را برداشت کند؟

---

# پیاده‌سازی نسخه 3 پروتکل معامله

حالتی را در نسخه 2 پروتکل در نظر بگیرید که دو طرف معامله از نهایی کردن آن امتناع کنند یا رمز قفل چکیده مفقود شود. در این صورت تمام دارایی مسدود خواهد ماند. برای حل این مشکل می‌توان یک تاریخ انقضاء برای قفل چکیده در نظر گرفت طوری که بعد از آن، قفل چکیده از اسکریپت حذف شود و امضای 2 از 3 به امضای 2 از 2 تبدیل شود. در این حالت داور می‌تواند بدون وابستگی به نتیجه معاله کارمزد خود را برداشت کرده و عملاً از معامله کنار بکشد.

قطعه کد زیر پیاده‌سازی این حالت را با تاریخ انقضای 50 بلوک (در واقعیت این مقدار بسیار بیشتر خواهد بود) نشان می‌دهد. تمام شرایط مشابه حالت قبل است و تنها تفاوت در نحوه برداشت کارمزد توسط داور و انجام پرداخت است.

```python
from bitcoinutils.constants import TYPE_RELATIVE_TIMELOCK
from bitcoinutils.transactions import Sequence

otp = random.randbytes(4)
seq = Sequence(TYPE_RELATIVE_TIMELOCK, 50)
escrow3_script = Script()
fee3_script = Script()
escrow3_input = TxInput(escrow2_txid, 2)
escrow3_tx = Transaction([escrow3_input], [
    TxOutput(to_satoshis(.11), escrow3_script.to_p2sh_script_pub_key()),
    TxOutput(to_satoshis(.002), fee3_script.to_p2sh_script_pub_key()),
    TxOutput(to_satoshis(50 - .36), alice_address.to_script_pub_key())])
escrow3_input.script_sig = Script()
result = node.testmempoolaccept(rawtxs=[escrow3_tx.serialize()])[0]
assert result['allowed'], f"escrow3 failed: {result['reject-reason']}"
print('escrow3', result)
escrow3_txid = node.sendrawtransaction(escrow3_tx.serialize())

payment3_input = TxInput()
fee3_input = TxInput()
payment3_tx = Transaction([payment3_input], [
    TxOutput(to_satoshis(.05), bob_address.to_script_pub_key()),
    TxOutput(to_satoshis(.05), alice_address.to_script_pub_key())
])
fee3_tx = Transaction([fee3_input], [
    TxOutput(to_satoshis(.0019), judge_address.to_script_pub_key())
])
# with otp:
payment3_input.script_sig = Script()
result = node.testmempoolaccept(rawtxs=[payment3_tx.serialize()])[0]
assert result['allowed'], f"payment3+otp failed: {result['reject-reason']}"
print('payment3+otp', result)
fee3_input.script_sig = Script()
result = node.testmempoolaccept(rawtxs=[fee3_tx.serialize()])[0]
assert result['allowed'], f"fee3+otp failed: {result['reject-reason']}"
print('fee3+otp', result)
# no otp:
otp = None
payment3_tx.inputs[0].sequence = seq.for_input_sequence()
payment3_input.script_sig = Script()
result = node.testmempoolaccept(rawtxs=[payment3_tx.serialize()])[0]
assert result['reject-reason'] == 'non-BIP68-final'

fee3_tx.inputs[0].sequence = seq.for_input_sequence()
fee3_tx.inputs[0].script_sig = Script()
result = node.testmempoolaccept(rawtxs=[fee3_tx.serialize()])[0]
assert result['reject-reason'] == 'non-BIP68-final'

node.generatetoaddress(nblocks=50,
                       address=alice_address.to_string(),
                       invalid_call=False)
result = node.testmempoolaccept(rawtxs=[payment3_tx.serialize()])[0]
assert result['allowed'], f"payment3-otp failed: {result['reject-reason']}"
print('payment3-otp', result)
result = node.testmempoolaccept(rawtxs=[fee3_tx.serialize()])[0]
assert result['allowed'], f"fee3-otp failed: {result['reject-reason']}"
print('fee3-otp', result)
```

>**وظیفه 6**: تراکنش ساخت نسخه 3 وجه امانی را تکمیل کنید.

>**وظیفه 7**: تراکنش پرداخت و برداشت کارمزد توسط داور را، در شرایطی که رمز یک‌بار مصرف در دسترس هست، تکمیل کنید.

>**وظیفه 8**: تراکنش پرداخت و برداشت کارمزد توسط داور را، در شرایطی که رمز یک‌بار مصرف در دسترس نیست، تکمیل کنید
