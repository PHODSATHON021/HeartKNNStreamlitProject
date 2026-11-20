# Heart Disease Prediction — KNN + Streamlit

เว็บแอปสำหรับการเรียนรู้การจำแนกข้อมูลด้วย K-Nearest Neighbors (KNN) จากไฟล์ `Heart3.csv`

## ไฟล์ในโปรเจกต์
- `app.py` — โปรแกรม Streamlit
- `Heart3.csv` — ชุดข้อมูลต้นฉบับ
- `requirements.txt` — ไลบรารีที่ต้องติดตั้ง

## รันบนเครื่อง
```bash
pip install -r requirements.txt
streamlit run app.py
```

## Deploy บน Streamlit Community Cloud
1. สร้าง GitHub repository ใหม่
2. อัปโหลด `app.py`, `Heart3.csv`, `requirements.txt` ไปไว้ใน repository เดียวกัน
3. เข้า https://share.streamlit.io/
4. เลือก New app แล้วเชื่อม repository
5. ตั้ง Main file path เป็น `app.py`
6. กด Deploy

## วิธีใช้งาน
- ภาพรวมข้อมูล: ดูจำนวนข้อมูล สัดส่วนคลาส และสถิติเบื้องต้น
- สำรวจข้อมูล: ดูการกระจายของตัวแปร
- ฝึกและประเมินโมเดล: ปรับค่า K และสัดส่วน Test Set พร้อมดู Accuracy, Precision, Recall, F1-score และ Confusion Matrix
- ทำนายข้อมูลใหม่: กรอกคุณลักษณะ 11 ตัวแปร แล้วกดทำนาย

## หมายเหตุสำคัญ
- ใช้ StandardScaler ภายใน sklearn Pipeline ก่อน KNN
- ใช้ train_test_split แบบ stratify และ random_state=42
- ไม่ได้ลบหรือแทนค่าศูนย์ใน RestingBP และ Cholesterol เพราะคงข้อมูลตามไฟล์ต้นฉบับ
- รหัสตัวแปรเชิงหมวดหมู่ใช้ค่าตัวเลขเดิม เนื่องจากไฟล์ไม่มี data dictionary อธิบายชื่อหมวดหมู่ครบถ้วน
- ผลทำนายเพื่อการศึกษาเท่านั้น ไม่ใช่การวินิจฉัยทางการแพทย์
