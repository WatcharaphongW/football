# คำอธิบายข้อมูล (Data Description)

โฟลเดอร์นี้อธิบายข้อมูลที่ใช้ในโครงงาน **Football Player & Salary Analysis**

## 1. แหล่งที่มาและสิทธิ์การใช้ข้อมูล

| หัวข้อ | รายละเอียด |
| --- | --- |
| ชื่อชุดข้อมูล | Football Player Salary & Performance Survey 2024 |
| แหล่งที่มาเดิม | https://www.kaggle.com/datasets/football-data/player-salaries-eu-2024 |
| ประเภทข้อมูล | ข้อมูลแบบสำรวจและรายงานค่าตอบแทนนักเตะอาชีพ (reported data) 1 แถวต่อผู้ตอบ/นักเตะ 1 คน |

## 2. ไฟล์ในโฟลเดอร์นี้

| ตำแหน่งไฟล์ | คำอธิบาย |
| --- | --- |
| `data/raw/football.csv` | ไฟล์ดิบตามที่ดาวน์โหลดมา **ห้ามแก้ไขด้วยมือ** มี 1,253 แถว 23 คอลัมน์ (รวมคอลัมน์ Timestamp/Metadata ในไฟล์ที่ตรวจ) |

วิธีสร้างไฟล์ที่ประมวลผลแล้วขึ้นใหม่: วางไฟล์ดิบที่ `data/raw/football.csv` แล้วรัน python `code/01_clean_data.py`


## 3. พจนานุกรมข้อมูล (Data Dictionary) ของ `football_clean.csv`

ข้อมูลหลังจากทำความสะอาดแล้วมีทั้งหมด 1,186 แถว ตารางต่อไปนี้แสดงชื่อคอลัมน์ ชนิดข้อมูล คำอธิบาย และจำนวนค่าว่างของแต่ละคอลัมน์

| คอลัมน์ | ชื่อคอลัมน์เดิม | ชนิดข้อมูล | คำอธิบาย / ค่าที่เป็นไปได้ | ค่าว่าง |
| --- | --- | --- | --- | ---: |
| `age` | Age | ตัวเลข | อายุของนักฟุตบอล หน่วยเป็นปี | 0 |
| `foot` | Preferred Foot | ข้อความ | ถนัดเท้า ได้แก่ Right, Left และ Both | 3 |
| `city` | Team City | ข้อความ | เมืองที่ตั้งของสโมสร ได้แก่ London, Madrid, Milan, Munich และ Other | 0 |
| `position` | Specific Position | ข้อความ | ตำแหน่งที่เล่นซึ่งระบุโดยละเอียด มีทั้งหมด 135 รูปแบบ เช่น Center-Back, Inverted Winger | 2 |
| `exp_total_years` | Total years of professional football | ตัวเลข | จำนวนปีประสบการณ์การเล่นฟุตบอลอาชีพทั้งหมด | 0 |
| `exp_league_years` | Years in current league | ตัวเลข | จำนวนปีประสบการณ์การเล่นในลีกปัจจุบัน | 44 |
| `role_level` | Squad Role / Seniority | ข้อความ | ระดับความสำคัญในทีม ได้แก่ Youth/Academy, Rotation, First-Team Regular, Key Player, Team Captain และ Other | 0 |
| `main_skill` | Main Technical Skill / Attribute | ข้อความ | ทักษะเด่นหรือจุดเด่นหลักในการเล่น กรอกด้วยตนเองและอาจมีรูปแบบการสะกดต่างกัน เช่น Pace, Passing, Dribbling | 109 |
| `secondary_skill` | Secondary Technical Skill / Attribute | ข้อความ | ทักษะเสริมอื่น ๆ ที่ใช้งานเป็นประจำ โดยอาจมีหลายรายการในหนึ่งช่อง เช่น Tackling, Long Shots | 141 |
| `salary_eur` | Yearly brutto salary (without bonus and signing fees) in EUR | ตัวเลข | ค่าตอบแทน/เงินเดือนรวมก่อนหักภาษีต่อปี ไม่รวมโบนัสและค่าเซ็นสัญญา หน่วยเป็นยูโร เป็นตัวแปรตามหลักสำหรับการวิเคราะห์ | 0 |
| `bonus_eur` | Yearly bonus + performance incentives in EUR | ตัวเลข | มูลค่าโบนัสผลงาน (ยิงประตู, คลีนชีต ฯลฯ) และส่วนแบ่งสิทธิประโยชน์ที่ได้รับต่อปี หน่วยเป็นยูโร | 396 |
| `salary_prev_year_eur` | Annual brutto salary ... one year ago (only if staying in the same league) | ตัวเลข | เงินเดือนรวมก่อนหักภาษีต่อปีของปีก่อนหน้า สำหรับผู้ที่ยังค้าแข้งอยู่ในลีกเดิม หน่วยเป็นยูโร | 333 |
| `bonus_prev_year_eur` | Annual bonus+incentives one year ago (only if staying in the same league) | ตัวเลข | มูลค่าโบนัสและเงินรางวัลในปีก่อนหน้า สำหรับผู้ที่ยังค้าแข้งอยู่ในลีกเดิม หน่วยเป็นยูโร | 590 |
| `contract_length_years` | Remaining contract length (years) | ตัวเลข | จำนวนปีสัญญาที่เหลืออยู่กับสโมสรปัจจุบัน | 66 |
| `employment_status` | Player Status | ข้อความ | สถานะสัญญาจ้าง ได้แก่ Permanent Player, Loaned Player, Free Agent, Academy Contract และ Other | 11 |
| `contract_duration` | Contract Type | ข้อความ | ประเภทสัญญาจ้าง ได้แก่ Long-term Contract (สัญญาระยะยาว) และ Short-term Contract (สัญญาระยะสั้น) | 22 |
| `main_language` | Primary language in dressing room | ข้อความ | ภาษาหลักที่ใช้สื่อสารภายในทีม/ห้องแต่งตัว ได้แก่ English, Spanish, German, French และ Other | 10 |
| `club_size` | Club Fanbase / Stadium Capacity | ข้อความ | ขนาดสโมสรตามความจุสนามและฐานแฟนบอล ได้แก่ Small (up to 10k), Medium (11k-30k), Large (31k-50k) และ Top Tier (50k+) | 8 |
| `club_type` | Club Ownership / Financial Structure | ข้อความ | ประเภทหรือรูปแบบโครงสร้างสโมสร ได้แก่ Private Owner, Fan-Owned/Socios, Investment Group และ Other | 15 |

**หมายเหตุ**
- จำนวนค่าว่าง (Missing Values) นับจากข้อมูลหลังทำความสะอาดแล้ว จำนวน 1,186 แถว

หน่วยของจำนวนเงินทั้งหมดคือยูโร (EUR) และเป็นเงินรวมก่อนหักภาษี (brutto)
