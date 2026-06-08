# flowchart```mermaid
flowchart TD
    Title([🏥 تدفق مريض مركز غزة للسرطان - مجمع ناصر])
    
    Start((دخول مريض الأورام))
    Title --- Start

    Start --> Clinic[🩺 العيادة]
    Start --> ER[🚑 الطوارئ]

    subgraph Shared[المسار المشترك للعيادة والطوارئ]
        direction TB
        Reg[📋 1. تسجيل ملف ووصول]
        Vitals[💓 2. فحص العلامات الحيوية]
        Samples[💉 3. سحب العينات]
        Exam[👨‍⚕️ 4. الفحص الطبي]

        Reg --> Vitals --> Samples --> Exam
    end

    Clinic --> Reg
    ER --> Reg

    Exam --> |مسار خاص بالعيادة فقط| Pharmacy[💊 صيدلية صرف خارجي]
    
    Exam --> |مسار مشترك| DayClinic[☀️ عيادة نهارية]
    Exam --> |مسار مشترك| Inpatient[🛏️ قسم مبيت]

    DayClinic --> DayWomen[👩 عيادة نهارية حريم]
    DayClinic --> DayMen[👨 عيادة نهارية رجال]

    Inpatient --> InWomen[👩 مبيت أورام حريم - قسم داخلي]
    Inpatient --> InMen[👨 مبيت أورام رجال - باطنة رجال]

    subgraph InpatientCare[إجراءات الرعاية في قسم المبيت]
        direction TB
        InVitals[💓 فحص العلامات الحيوية]
        FollowUp[📈 متابعة الحالة الطبية]
        RecSamples[🧪 تسجيل العينات]
        Meds[💊 صرف الأدوية - الكاردكس]
        
        InVitals --> FollowUp --> RecSamples --> Meds
    end

    InWomen --> InVitals
    InMen --> InVitals
```
اعطني الفلو تشارت صورة
