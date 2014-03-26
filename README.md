#مشروع تطبيق للقرآن الكريم  للهواتف الذكية مبني بلغات الويب

##لماذا؟
جربت عدة تطبيقات للقرآن الكريم على نظام أندرويد، ولم تكن النتائج تعجبني دوماً، لعل أفضلها كان [Quran Android](https://play.google.com/store/apps/details?id=com.quran.labs.androidquran) لكن مشكلته كانت في كونه يعرض __صورًا للصفحات من مصحف المدينة بدلاً من النصوص__، الأمر الذي يجعلها صعبة القراءة على الشاشات الصغيرة وفي وضع الشاشة الشاقولي (portrait) وكذلك فإن الصور تجعل عرض الترجمة مرافقاً للأية غير ممكن، بل يجب النقر مطولاً على كل آية للاطلاع على تفسيرها أو ترجمتها، بعض التطبيقات الأخرى لا توفر ميزة البحث، وبعضها لا يراعي قابلية الاستخدام.
قررت البدء بتصميم التطبيق في البداية ليكون تطبيق Chrome يعمل بلا اتصال وبدأت ببناءه بالاعتماد على إطار العمل Bootstrap 3، ثم أدركت أن من الأفضل بناءه على أنه تطبيق للهواتف أولاً (mobile first) ثم الانتقال إلى سطح المكتب إن كان الأمر ممكناً.
لذا قمت بالانتقال إلى إطار العمل _ionic_ (وهو حديث نسبياً) أولاً لكونه موجهاً للهواتف الذكية، وثانياً لأنه مبنيّ على إطار عمل _Angular JS_ الذي أعشقه وأعتقد أن خبرتي به لا بأس بها.

##ما الذي يقدمه التطبيق؟
التطبيق حالياً يوفر المميزات التالية:
  * عرض النص القرآن مع تلوين الحركات وعلامات الوقف بلونين مختلفين لتسهيل القراءة
  * دعم كل الترجمات التي يقدمها [مشروع ذكر](http://zekr.org/resources.html)
  * دعم كل التلاوات التي يقدمها مشروع [EveryAyah](http://everyayah.com/)
  * البحث باستخدام الواجهة البرمجية [لمشروع الفانوس](http://alfanous.org/)
  * البحث بلا اتصال عند غياب الاتصال بالإنترنت، والمعتمد على التعابير النظامية (Regular Expressions) الذي يوفر إمكانية تجاهل الأخطاء في الهمزات والحركات

##الجوانب التقنية
المشروع مبني على إطار العمل [Ionic](http://ionicframework.com/) الذي يستخدم Angular JS، النصوص البرمجية مكتوبة بلغة [CoffeeScript](http://coffeescript.org/) وملفات العرض مكتوبة بلغة [Jade](http://jade-lang.com)، ملفات التنسيق مكتوبة بلغة [LESS](http://lesscss.org) (وأفكر في الانتقال إلى Sass لاحقاً لتكون أكثر توافقاً مع منهج ionic).
بالنسبة لنمط التصميم (Design Pattern) فهو بالطبع MVC، وملفات `.coffee` منسقة ضمن مجلدات وكل منها مسؤول عن خدمة أو متحكم... بما يسهل تطوير وتعديل الوحدات بشكل منفصل.

##ما الأنظمة التي سيستهدفها المشروع؟
بما أن المشروع مبني بلغات الويب وإطار عمل يستهدف الهواتف الذكية، فإنه سيكون متوفراً بقدر ضئيل من التعديلات على عدة أنظمة ذكية على رأسها Android وiOS وFirefox OS. سأضيف إعدادات منصة Cordova لبناء التطبيقات وسيتم الانتقال إليها على عدة مراحل، بالنتيجة سيتوفر التطبيق المنصات السابقة عند انتهاء الانتقال إلى Cordova.

##صور للتطبيق
حالياً هكذا يبدو التطبيق: (إن تعذر عرض الصور أدناه [فشاهدها هنا](http://imgur.com/a/zL9g5))

![الصفحة الرئيسية](http://i.imgur.com/xH9iWiU.png)
![البحث باستخدام الواجهة البرمجية لمشروع الفانوس](http://i.imgur.com/UDhVLXR.png)
![البحث بلا اتصال](http://i.imgur.com/OEVoJLO.png)
![صفحة التفضيلات](http://i.imgur.com/ekO9UYj.png)
![صفحة البحث](http://i.imgur.com/IjqMQPD.png)
![نتائج البحث](http://i.imgur.com/HK5M9zf.png)
![عرض آية مفردة مع ترجمتها (إمكانية اختيار أكثر من ترجمة)](http://i.imgur.com/hl8tsPF.png)
![الترجمات المتوفرة](http://i.imgur.com/l1kqI3j.png)
![عرض أية مفردة مع ترجمتها (إمكانية اختيار اكثر من ترجمة)](http://i.imgur.com/2pxbeMz.png)
![نتائج البحث](http://i.imgur.com/4bEwPzY.png)
![تلاوة الصفحة](http://i.imgur.com/DwMuKR6.png)

##كيف يمكنني المساعدة؟
* إن كنت تجيد التعامل مع مشاريع الويب فانسخ المشروع إلى جهازك وابنه باستخدام الأوامر التالية:


    gulp build
    gulp ayas ayas_search
    gulp recitations
    gulp download_translations
    gulp translations
    gulp watch serve
 

ثم افتح [localhost:7000](http://localhost:7000/) لبدء التطبيق. أنصح باستخدام Firefox وفي منظور التصميم المستجيب (Responsive Design View) لأن Chrome لا يعرض الكلمات العربية المشكلة بصورة صحيحة في نسخه الأخيرة.
* هل بإمكانك الترجمة أو التوثيق؟ أنشئ فرعاً عن المشروع على GitHub وأجر تعديلاتك ثم ادفعها إليّ!
