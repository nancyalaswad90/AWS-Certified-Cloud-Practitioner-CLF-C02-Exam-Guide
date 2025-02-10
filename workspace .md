![image](https://github.com/user-attachments/assets/7090e0e0-b9ab-4230-a368-4f73386402f9)


.
### **ترجمة محتويات الصورة إلى العربية:**

.

#### **ND9991 - الدورة الثانية - البنية التحتية ككود (Infrastructure as Code)**

يحتوي هذا المستودع على الكود الأساسي للمشروع النهائي الخاص بالدورة الثانية "البنية التحتية ككود" ضمن شهادة Cloud DevOps Engineer من Udacity.

**نشر تطبيق ويب عالي التوافر باستخدام CloudFormation**  
في هذا المشروع، ستقوم بنشر خوادم ويب لتطبيق عالي التوافر باستخدام CloudFormation. ستكتب الكود الذي ينشئ وينشر البنية التحتية والتطبيق الخاص بتطبيق مشابه لـ Instagram من البداية. ستبدأ بنشر مكونات الشبكة، تليها الخوادم، وأدوار الأمان، والبرمجيات. الخطوات التي ستتبعها ستصبح جزءًا من محفظتك العملية في مشاريع الحوسبة السحابية.

---

### **الخطوات الأساسية للبدء:**

#### **التبعيات (Dependencies):**
1. تثبيت **AWS CLI** وإعداده في بيئة العمل باستخدام **AWS IAM Role** مع أذونات المسؤول (Administrator Permissions).  
2. الوصول إلى أداة لإنشاء المخططات (Diagram Creator).  
3. محرر نصوص أو IDE جاهز للعمل.

#### **التثبيت (Installation):**
يمكنك بدء العمل عن طريق استنساخ المستودع التالي إلى بيئتك المحلية:
```bash
git clone git@github.com:udacity/-cd12352-Deploy-Infrastructure-as-Code-project.git
```

---

#### **التعليمات الخاصة بالمشروع (Project Instructions):**
1. قم **بتصميم مخطط الحل الخاص بك** باستخدام أداة من اختيارك وقم بتصديره كملف صورة.  
2. أضف جميع **موارد الشبكة الخاصة بـ CloudFormation** والمعلمات إلى الملفات `network.yml` و `network-parameters.json` داخل مجلد `starter`.  
3. أضف جميع **موارد التطبيق الخاصة بـ CloudFormation** والمعلمات إلى الملفات `udagram.yml` و `udagram-parameters.json` داخل نفس المجلد.  
4. قم بإنشاء أي سكريبتات لازمة **لأتمتة إنشاء وحذف المكدسات (CloudFormation Stacks)**.  
5. قم **بتحديث ملف README.md** في المجلد `starter` لتتضمن تعليمات الإنشاء والحذف، وأي معلومات مفيدة حول الحل الخاص بك.  
6. قم **بتقديم الحل الخاص بك كملف مضغوط (Zipped Folder)** يحتوي على مخطط التصميم، ملفات YAML و JSON الخاصة بـ CloudFormation، السكريبتات، وملف README.md.

---

### **كيفية البدء:**

#### **1. تجهيز البيئة:**
- **تأكد من تثبيت AWS CLI:**  
  - استخدم الأمر التالي لإعداد بيانات الاعتماد الخاصة بـ AWS:  
    ```bash
    aws configure
    ```
  - أدخل بيانات المستخدم، المفتاح السري، المنطقة الافتراضية، وتنسيق الإخراج.

#### **2. استنساخ المستودع:**
- استخدم الأمر:
  ```bash
  git clone git@github.com:udacity/-cd12352-Deploy-Infrastructure-as-Code-project.git
  ```
  - بعد استنساخ المستودع، ادخل إلى المجلد:
    ```bash
    cd starter
    ```

#### **3. تصميم المخطط:**
- قم بإنشاء مخطط يوضح مكونات البنية التحتية مثل:
  - الشبكات: VPC، Subnets.
  - موازن التحميل (Load Balancer).
  - EC2، NAT Gateways.

#### **4. تعديل ملفات YAML و JSON:**
- افتح `network.yml` وأضف الموارد الشبكية مثل:
  - VPC.
  - Subnets (Public and Private).
  - Internet Gateway و NAT Gateway.
- استخدم `network-parameters.json` لتحديد المعلمات (مثل CIDR Blocks).

- افتح `udagram.yml` لإضافة موارد التطبيق مثل:
  - EC2 Instances.
  - Load Balancer.
- استخدم `udagram-parameters.json` لإضافة معلمات مثل معرفات VPC و Subnets.

#### **5. تنفيذ النشر:**
- قم بتنفيذ الأوامر باستخدام AWS CLI:
  - لنشر الشبكة:
    ```bash
    aws cloudformation deploy --template-file network.yml --stack-name network-stack --parameter-overrides file://network-parameters.json
    ```
  - لنشر التطبيق:
    ```bash
    aws cloudformation deploy --template-file udagram.yml --stack-name udagram-stack --parameter-overrides file://udagram-parameters.json
    ```

#### **6. الاختبار:**
- افتح رابط DNS الخاص بموازن التحميل للتحقق من أن التطبيق يعمل.

#### **7. توثيق المشروع:**
- قم بتحديث ملف `README.md` لشرح خطوات التنفيذ والحذف.

#### **8. التحضير للتسليم:**
- اجمع جميع الملفات في مجلد مضغوط أو قم برفعها إلى GitHub.

🚀 **بالتوفيق في تنفيذ المشروع! إذا كنت بحاجة إلى أي مساعدة إضافية، فلا تتردد في السؤال.**
