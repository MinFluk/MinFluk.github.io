ROOTKIT คืออะไร ทำงานอย่างไร และจะลบมันออกได้อย่างไร?
Posted on 16 ก.พ. 2021 Support

คำว่า “rootkit” (รูทคิท) สามารถเชื่อมโยงกับไวรัส หรือการโจมตีอุปกรณ์สำหรับผู้ใช้งานคอมพิวเตอร์ และโดยปกติจะเกี่ยวข้องกับ มัลแวร์ (malware) – และด้วยเหตุผลที่ดี rootkit นั้น เป็นมัลแวร์ประเภทที่อันตรายที่สุด และนอกจากนี้ยังฉลาดมาก – คุณจะไม่ทันสังเกตด้วยซ้ำ ว่ามันได้มีอยู่ในคอมพิวเตอร์ของคุณ ดังนั้นผู้คนจำนวนมากจึงไม่ทราบถึงการมีอยู่ของภัยคุกคามประเภทนี้ และยังมีการแอบติดอุปกรณ์ของพวกเขา เราจะไปค้นหาว่า rootkit คืออะไร วิธีการลบมันออกไป และคุณสามารถป้องกัน rootkit ได้หรือไม่

Rootkit คืออะไร?
คำจำกัดความของรูทคิตนั้น ประกอบด้วยคำสองคำ: “รูท” (root) และ “Putty” (พุตตี้) โดย Unix มักเรียกตัวเองว่า “root” ซึ่งหมายถึงผู้ใช้ที่มีสิทธิ์เข้าถึงระบบอย่างเต็มที่และไม่จำกัด “putty” นั้น เป็นเพียงชุดเครื่องมือ การรวมกันของคำเหล่านี้หมายถึงซอฟต์แวร์ที่เป็นอันตรายอย่างยิ่ง ที่ช่วยให้แฮ็กเกอร์สามารถเข้าถึงคอมพิวเตอร์ที่ติดไวรัสได้จากระยะไกล และถาวร ผ่านการติดตั้งเครื่องมือต่าง ๆ โดยปกติแล้วจุดประสงค์ของพวกมันก็คือการขโมยข้อมูล และผู้ใช้งานมักจะไม่รู้เลยว่าเขาสูญเสียการควบคุมอุปกรณ์ของตัวเอง – ดังนั้นจึงไม่สามารถมองข้ามภัยคุกคามที่เกิดจาก rootkit ได้

Rootkit หลีกเลี่ยงการตรวจจับ ซึ่งทำหน้าที่คล้ายกับคีย์ล็อกเกอร์ – มันจะพยายามซ่อนตัวให้ลึกที่สุดในระบบ และซ่อนตัวจากโปรแกรมป้องกันไวรัส และโปรแกรมความปลอดภัยอื่น ๆ อย่างชาญฉลาด มันมักจะทำตัวเหมือนเป็นแบ็คดอร์ เพื่อสร้าง”ประตูที่มองไม่เห็น” สำหรับอาชญากรไซเบอร์ ให้กับระบบของเหยื่อซึ่งไม่เพียงแต่ติดตั้งส่วนประกอบเพิ่มเติมในนั้น เท่านั้น ซึ่งเครื่องมือที่พบบ่อยที่สุดใน Rootkit ได้แก่ :

โมดูลการโจรกรรม – การสกัดกั้นรหัสผ่านรายละเอียดบัตรเครดิตข้อมูลธนาคารออนไลน์
บอทสำหรับการโจมตีในรูปแบบ DDoS
keyloggers (กลไกในการตรวจจับการกดแป้นพิมพ์);
ฟังก์ชันที่สามารถหลีกเลี่ยงและปิดใช้งานระบบรักษาความปลอดภัย
มัลแวร์ Rootkit ต้องได้รับการออกแบบสำหรับระบบเฉพาะ ดังนั้นสำหรับ Windows คุณสามารถแยกแยะ Rootkit ที่ใช้งานได้เช่น: Necurs, Alueron, ZeroAccess หรือ TDSS ปัจจุบัน Rootkit สามารถโจมตีระบบใดก็ได้ ไม่ว่าจะเป็น MacOS, Solaris, FreeBSD และโซลูชันอื่น ๆ ที่เป็นที่รู้จักไม่มากก็น้อย

ข้อสรุปก็คือ: ในทุกวันนี้ไม่มีระบบใดรับประกันความปลอดภัยได้ 100%

การใช้งาน rootkits
Rootkit นั้นไม่เป็นอันตราย แต่ก็ไม่เคยเกิดขึ้นเอง แพ็กเกจ rootkit มักมีโปรแกรมที่เป็นอันตรายเพิ่มเติมอยู่เสมอ งานของ rootkit คือการปิดกั้นความพยายามในการตรวจจับผู้บุกรุก ปัจจุบันรูทคิทส่วนใหญ่ใช้สำหรับการโจมตีผ่านทางอินเทอร์เน็ต แต่ยังมี Rootkit ของเครื่องมือที่ช่วยให้คุณสามารถข้ามการป้องกันการละเมิดลิขสิทธิ์ได้
Rootkits ยังเป็นโซลูชันที่ได้รับความนิยมเป็นพิเศษในหมู่นักเล่นเกมคอมพิวเตอร์ ที่สร้างดิสก์เสมือนจริงด้วยเกมเวอร์ชันละเมิดลิขสิทธิ์ โดยไม่ต้องใส่สื่อซีดีต้นฉบับลงในไดรฟ์

Rootkits สามารถถูกใช้ใน: 

สร้าง backdoor หรือประตูที่มองไม่เห็นของระบบ ซึ่งแฮ็กเกอร์สามารถควบคุมอุปกรณ์ที่ถูกโจมตีจากระยะไกลได้ สิ่งนี้ช่วยให้คุณข้ามกลไกการตรวจสอบสิทธการอนุญาตให้เข้าถึง โดยไม่ได้รับอนุญาต เช่น การขโมยข้อมูล หรือการปลอมแปลงข้อมูล
มัลแวร์ ตัวอย่างเช่น มัลแวร์ที่ออกแบบมาเพื่อขโมยข้อมูลที่ละเอียดอ่อน รหัสผ่าน ฯลฯ เหล่านี้คือคีย์ล็อกเกอร์ และเป็นไวรัสที่ถูกพบบ่อยมากที่สุด
ใช้คอมพิวเตอร์หรือเครือข่ายที่ถูกโจมตีเพื่อโจมตีอุปกรณ์อื่น ๆ เพิ่มเติมโดยข้ามคอมพิวเตอร์ของแฮ็กเกอร์ คอมพิวเตอร์ที่ถูกโจมตีมักเรียกว่า “คอมพิวเตอร์ซอมบี้” โดยหลักการแล้วอุปกรณ์ใด ๆ ที่เชื่อมต่อกับอินเทอร์เน็ตนั้น ก็สามารถเปลี่ยนเป็นซอมบี้ได้ หากไม่ระมัดระวังตัว
การโจมตีประเภทนี้ส่วนใหญ่เกิดขึ้นกับกลุ่มคอมพิวเตอร์ที่ติดมัลแวร์ (Botnet) สิ่งนี้ช่วยให้ผู้ใช้จากระยะไกล และมองไม่เห็น เพื่อทำการโจมตีที่เกี่ยวข้องกับ เช่น สแปมโดยการส่งลิงก์การคลิกหลอกลวง (Phishing) หรือการโจมตี DDoS สำหรับซอมบี้รุ่นหลังนั้นเหมาะสมเป็นอย่างยิ่ง – DDoS คือการโจมตีครั้งใหญ่จากคอมพิวเตอร์หลายเครื่อง ต่อหน่วยเดียว ซึ่งขัดขวางการทำงานที่เหมาะสม โดยแย่งทรัพยากรว่างทั้งหมด (หน่วยความจำเวลาตัวประมวลผล) ของคอมพิวเตอร์ที่ถูกโจมตี
Rootkits – ดังที่เรากล่าวถึง – ไม่เลวเลยสำหรับคุณสมบัติในตัวมันเอง และมักใช้เพื่อถูกกฎหมาย แต่เป็นประโยชน์จากมุมมองของผู้ใช้งาน – การกระทำนั้นคือเจ้าของอุปกรณ์ได้รับการติดตั้งอย่างมีสติ ส่วนใหญ่ rootkit ดังกล่าว มักถูกใช้สำหรับ:

digital rights management (DRM) – รูทคิทในรูปแบบนี้สร้างระบบความปลอดภัยเช่น ไฟล์เพลงวิดีโอ และเกมที่อนุญาตให้เฉพาะผู้ซื้อที่ถูกต้องเท่านั้นที่สามารถเปิดใช้งานได้
ดีแล้วที่รู้

DRM แรกนั้นมีการเปลี่ยนแปลงชั่วคราว m.in ประกอบด้วยการขัดจังหวะเกมอย่างกะทันหัน โดยขอให้มีการแนะนำข้อความจากคู่มือกระดาษ โดยปกติเจ้าของคำแนะนำดังกล่าวในเวอร์ชันละเมิดลิขสิทธิ์นั้นมักไม่มี อย่างไรก็ตามเวลาได้เปลี่ยนไปและวิธีการในการต่อต้านการละเมิดลิขสิทธิ์ด้วยเช่นกัน มันเป็นสงครามครั้งยิ่งใหญ่ระหว่างผู้ผลิตความปลอดภัย และแฮกเกอร์ (ผู้สร้างดาบที่เรียกว่าแครกเกอร์และพวกโจรสลัด)

น่าเสียดายที่ความสมดุลของการชนะนั้นเอียงไปทางด้านอาชญากรไซเบอร์ นักพัฒนาเกมให้ความสำคัญกับการรักษาความปลอดภัยมากจนลืมนึกถึงผู้ใช้งานทั่วไป ดังนั้นความปลอดภัยของคนรัสเซียนั้น StarForce จึงไม่เพียงแต่ปกป้องความถูกต้องตามกฎหมายของเกมเท่านั้น แต่ยังควบคุมคอมพิวเตอร์ทั้งหมดของผู้เล่น ดังนั้นจึงป้องกันการดำเนินกิจกรรมที่ผิดกฎหมาย – ไม่เพียงแต่เกี่ยวข้องกับเกมเท่านั้น การปฏิบัติเหล่านี้ทำให้เกิดการต่อต้านอย่างรุนแรงในหมู่นักเล่นเกม m.in. ผู้พัฒนาเกมชาวฝรั่งเศส UbiSoft ยกเลิกข้อตกลงความร่วมมือกับ StarForce

กรณีศึกษาที่น่าสนใจยังเป็นตัวอย่างหนึ่งในเกมของ บริษัท Electronic Arts – “Spore” เวอร์ชันดั้งเดิมได้เพิ่มระบบป้องกันที่เรียกว่า SecuROM มันไม่อันตรายเท่า StarForce แต่สร้างความประหลาดใจให้กับผู้ใช้งานมากมาย เกมดังกล่าวต้องการการใช้ซีดีดั้งเดิม และการเปิดใช้งานเครือข่ายแบบบังคับ – ความจริงที่ว่าการรักษาความปลอดภัยเครือข่ายมีประสิทธิภาพสูงสุด อย่างไรก็ตามมันสมเหตุสมผลสำหรับเกมส์ที่ใช้เครือข่ายนี้อย่างสมบูรณ์เท่านั้น “Spore” ใช้อินเทอร์เน็ตในระดับเล็กน้อย อย่างไรก็ตามปัญหานั้นลึกกว่าคุณสามารถสร้างบัญชีผู้ใช้งานเพียงบัญชีเดียว และเปิดใช้งานได้ครั้งเดียว และภายในบัญชีของคุณเกมสามารถติดตั้งได้สูงสุด 3 ครั้ง

ซึ่งหมายความว่าไม่สามารถติดตั้งพร้อมกันบนพีซีและแล็ปท็อป ได้และระบบปฏิบัติการ 3 ระบบติดตั้งใหม่ ซึ่งไม่รวมความเป็นไปได้ในการติดตั้งเกมใหม่ ปรากฎว่าวิธีการเหล่านี้โดนใจผู้ใช้งานมากที่สุด – แฮกเกอร์ไม่ได้รับการปกป้องเหล่านี้ และเกม “Spore” เวอร์ชันผิดกฎหมายก็ออนไลน์ได้ ก่อนที่จะมีการเปิดตัวอย่างเป็นทางการ แม้ว่าผู้ผลิตจะสละข้อจำกัดส่วนใหญ่ในไม่กี่สัปดาห์ หลังจากเปิดตัวเกม แต่ก็ไม่ได้แก้ไขข้อเสนอแนะเชิงลบของผู้ใช้

การตรวจจับการโจมตี ตัวอย่างเช่น honeypot – นี่คือกับดักที่แอบอ้างว่าเป็นระบบบริการเดียวหรือเครือข่ายท้องถิ่น จุดประสงค์คือเพื่อสกัดกั้นและแจ้งเกี่ยวกับความพยายามที่จะเข้าถึงข้อมูลโดยไม่ได้รับอนุญาต Honeypots มาในเวอร์ชันที่น้อยลงและครอบคลุมมากขึ้น – รุ่นหลัง ๆ สามารถบันทึก และตรวจสอบพฤติกรรมของผู้โจมตี โดยใช้ที่อยู่ IP หลายรายการ เป็นเครื่องมือที่ยอดเยี่ยมสำหรับการตรวจจับการโจมตีตั้งแต่เนิ่น ๆ สำหรับการป้องกันมัลแวร์ และช่องโหว่
การปรับปรุงโปรแกรมจำลองไดรฟ์เสมือน – เป็นโปรแกรมเชิงพาณิชย์ยอดนิยม เช่น Alcohol120% หรือ Daemon Tools ใช้เพื่อกำจัดความปลอดภัยที่เกี่ยวข้องกับการคัดลอกอย่างผิดกฎหมาย เช่น เกมส์ พวกเขาทำลายระบบ safedisc และ securom ออกไป
การตรวจจับมัลแวร์ – ซอฟต์แวร์ป้องกันไวรัสคุณภาพดีใช้ rootkit เพื่อป้องกันมัลแวร์ ทำงานบนหลักการของการบันทึกกิจกรรมของระบบและป้องกันแขกที่ไม่ได้รับเชิญ กระบวนการป้องกันไวรัสไม่ได้ถูกซ่อนไว้ แต่คุณไม่สามารถดำเนินการได้ด้วยตัวเอง
การตรวจจับการฉ้อโกงในเกมส์ เช่น ผ่านผู้ตรวจสอบระบบ หรือ GameGuard นี่คือสิ่งที่เรียกว่าซอฟต์แวร์ป้องกันการโกง – ต่อต้านการโกงในเกม
รู้ก่อนที่จะไป

หนึ่งในเรื่องอื้อฉาวล่าสุดเกี่ยวกับ Valorant ได้ถูกปล่อยออกมาโดย Riot Games และระบบป้องกันการโกง “Vanguard” ผู้ใช้พบว่า rootkit นี้เริ่มต้นด้วยการเริ่มต้นระบบปฏิบัติการ และทำงานได้ แม้ว่าจะไม่ได้เปิดใช้งานเกมส์ก็ตาม และที่แย่กว่านั้นก็คือมีสิทธิ์ของผู้ดูแลระบบอยู่ด้วย!
ซึ่งหมายความว่าสามารถรวบรวมข้อมูลผู้ใช้ทั้งหมดได้ แต่ยังสร้างแบ็คดอร์ Riot Games ได้อธิบายสิ่งนี้ด้วยการตรวจสอบให้แน่ใจว่า Vanguard ได้รับการตรวจสอบช่องโหว่อย่างละเอียด และไม่ได้รวบรวมข้อมูลผู้ใช้ 100% ตามที่ผู้ผลิตได้กล่าวหาว่า “Vanguard” เป็นรูปแบบที่ยอดเยี่ยมของการต่อสู้กับคนขี้โกง อย่างไรก็ตามหากปรากฎว่าไดรเวอร์เปิดเผยผู้เล่น Riot Games จะถอนตัวและพัฒนากลไกใหม่ทั้งหมด สิ่งที่สองคือวิธีนี้ใช้งานได้จริงหรือไม่ เพราะอย่างไรก็ตามคนขี้โกงแม้จะมีอยู่ แต่ก็ทำได้ค่อนข้างดี

anti-theft – บนแล็ปท็อปคุณสามารถติดตั้งซอฟต์แวร์ในประเภท rootkit ซึ่งอิงตามไบออส ด้วยวิธีนี้คุณสามารถตรวจสอบตำแหน่งของแล็ปท็อป ปิด และลบข้อมูลจากระยะไกลได้
การข้ามการเปิดใช้งานผลิตภัณฑ์ Microsoft – ซึ่งเป็นเรื่องปกติสำหรับชุด Windows และ Microsoft Office
Rootkits ตัวล่าสุดไม่ได้มุ่งเป้าไปที่คอมพิวเตอร์และแล็ปท็อปอีกต่อไป แต่ยังรวมถึงอุปกรณ์พกพา โดยเฉพาะอย่างยิ่งอุปกรณ์ทที่ใช้งานระบบ Android ส่วนใหญ่มักเกี่ยวข้องกับแอปพลิเคชันที่น่าสนใจ ซึ่งสามารถดาวน์โหลดได้จากแหล่งที่ไม่น่าเชื่อถือ

ประเภทของไฟล์ rootkits มีอะไรบ้าง?
Rootkits นั้นมีหลายประเภท แต่เพื่อให้เข้าใจได้ดีคุณต้องพิจารณาสิ่งที่เรียกว่า protection rings พูดง่าย ๆ ก็คืออธิบายระดับสิทธิ์ของสถาปัตยกรรมระบบปฏิบัติการ ระดับประกอบด้วย 4 วงกลม ระดับที่เล็กที่สุดหรือต่ำสุด แต่มีสิทธิ์มากที่สุดคือวงแหวน “0” ซึ่งมีเคอร์เนลของระบบที่ควบคุมคอมพิวเตอร์ทั้งหมด ด้านบนคือวงแหวน “1” ตามด้วยวงแหวน “2” – ในนั้นจะมีไดรเวอร์ทั้งหมดเช่น จากการ์ดแสดงผล

ระดับสูงสุดสุดท้ายที่มีสิทธิ์ต่ำสุดคือวงแหวน “3” ซึ่งรวมถึงแอปพลิเคชันที่คุณใช้เช่น Microsoft Office, CorelDraw และ Photoshop เป็นที่น่าสังเกตว่าวงแหวน “0” ยังควบคุมการต่อต้านไวรัสที่อยู่ในระดับสูงสุด “3” ซึ่งมักจะไม่ถึงระดับ “1” ด้วยซ้ำ

Rootkits สามารถเล็งไปที่ระดับใดก็ได้ แต่สิ่งที่ยากที่สุดในการตรวจจับจะมุ่งเป้าไปที่เคอร์เนลของระบบ นอกจากนี้ยังมีรูทคิทแบบไฮบริด – นั่นคือรูทคิทที่ตีพร้อมกันตัวอย่างเช่นระดับผู้ใช้และระดับเคอร์เนลของระบบ

ก่อนที่คุณจะไปถึงระดับใดระดับหนึ่งคุณต้องใส่ใจกับ Persistent Rootkits และ Memory-Based Rootkits:

 

“Intrusive” คือ Rootkit ที่มีชื่อที่โดดเด่น เนื่องจากมีการเรียกใช้ทุกครั้งที่ระบบปฏิบัติการ เริ่มทำงานโดยปกติจะถูกจัดเก็บเป็นรหัส และโปรแกรมบนดิสก์ หรือรีจิสตรีจะทำงานในพื้นหลัง และไม่ปรากฏในรายการกระบวนการ และบริการของ ระบบนี่คือ Rootkit ประเภทที่พบมากที่สุด เนื่องจากไม่ต้องใช้รหัสพิเศษ และง่ายต่อการแจกจ่าย
Rootkit ในหน่วยความจำ สามารถทำงานในแคชของคอมพิวเตอร์ของคุณ เพื่อใช้แล้วทิ้ง – โดยการเปิดใช้งานเพียงครั้งเดียว และหายไปเมื่อระบบเริ่มต้นใหม่ นั่นเป็นสาเหตุที่ตรวจจับได้ยากกว่ามาก

รูทคิทระดับผู้ใช้งาน – วงแหวนระดับ “3”
Rootkits ในระดับนี้ สามารถทำงานร่วมกับแอปพลิเคชันอื่น ๆ พวกมันยังสามารถใช้วิธีการติดตั้งที่แตกต่างกันมาก แต่ทั้งหมดได้รับการออกแบบมาเพื่อจับภาพ และแก้ไขกระบวนการ API มาตรฐาน (อินเตอร์เฟสการเขียนโปรแกรมแอปพลิเคชันนั่นคือคำสั่งที่ระบบปฏิบัติการใช้เพื่อสื่อสารกับโปรแกรม)
ตัวอย่างเช่นสามารถ Inject ไลบรารีไดนามิก (ใน Windows ไฟล์ที่มีนามสกุล. dll ใน MacOS X – .dylib) ลงในกระบวนการอื่น ๆ ได้

หมายความว่าอย่างไร?

ไลบรารีแบบไดนามิก เชื่อมต่อกับโปรแกรมที่เรียกใช้งานได้ แต่เมื่อถูกเรียกใช้งานเท่านั้น Rootkit ที่ติดตั้งด้วยวิธีการเหล่านี้นั้น สามารถดำเนินการตามกระบวนการเป้าหมาย – เพื่อปลอมแปลง (ซ่อนกระบวนการที่กำลังทำงานอยู่หรือไฟล์ในระบบ)

ตัวอย่างนี้เป็นช่องโหว่ใน Windows ที่เรียกว่า Import Address Table IAT เป็นส่วนหนึ่งของไฟล์. dll ที่มีหน้าที่ชี้ไปยังฟังก์ชันไลบรารีเช่นเดียวกับ. dll อื่น ๆ รหัสบูตของ rootkit ใช้หนึ่งในฟังก์ชันที่ใช้บ่อยที่สุดในไลบรารีระบบโดยเขียนทับ
สิ่งนี้เริ่มต้นแทนฟังก์ชันที่ระบุ อย่างไรก็ตามเพื่อให้ไม่มีใครสังเกตเห็นต่อไปมันยังเรียกใช้คำสั่งที่ร้องขอ ไลบรารีที่มีช่องโหว่ที่สุดของ Win32 ได้แก่ Kernel32.dll, Gdi32.dll และ User32.dll เมื่อพูดถึง Windows API – Advapi32.dll

อีกตัวอย่างหนึ่งคือการเขียนทับหน่วยความจำของแอปพลิเคชันที่เลือก – แต่สามารถทำได้เมื่อคุณได้รับสิทธิ์การเข้าถึงที่เหมาะสม
Rootkit สามารถใช้กลไกการ Injection ที่แตกต่างกัน:

สกัดกั้นข้อความ
สามารถผ่านช่องโหว่ด้านความปลอดภัยของ Debugger
ส่วนขยายแอปพลิเคชัน (application extensions) – ตัวอย่างคือ Windows Explorer ซึ่งมีอินเทอร์เฟซสาธารณะที่สามารถแก้ไขด้วยส่วนขยายโดยบุคคลที่สาม
จับภาพและแก้ไข API
 

ระดับผู้ใช้งานมักเป็นพื้นที่สำหรับ Rootkit เพื่อทดแทนที่โปรแกรมมาตรฐานด้วยเวอร์ชันของโทรจัน วิธีนี้ช่วยให้คุณปกปิดการมีอยู่ของมัลแวร์ และเข้าถึงข้อมูลได้อย่างไม่ยากเย็นนัก

ตัวอย่าง Rootkit ระดับผู้ใช้ ได้แก่ Aphex, Hacker Defender หรือ Vanquish
HackerDefender iเป็นหนึ่งในรูทคิทยอดนิยม โดยปกติจะถูกถ่ายโอนร่วมกับมัลแวร์อื่น ๆ เช่น Trojan ของตระกูล CWS การมีอยู่ในคอมพิวเตอร์ของคุณ อาจบ่งบอกถึงการหายไปอย่างกะทันหันของโปรแกรม เช่น m.in HiJackThis (HJT – โปรแกรมกำจัดมัลแวร์) หรือการขัดขวางการทำงานของโปรแกรมป้องกันไวรัส HackerDefender มีหลายเวอร์ชันและยังสามารถ … ซื้อใช้งานได้บนเครือข่ายในเวอร์ชันเชิงพาณิชย์ – คุณสามารถปรับแต่งตามความต้องการและความสามารถของคุณ

 

รูทคิทระดับไฮเปอร์ไวเซอร์ – ระดับวงแหวน “2” และ “1”
 

จากระดับที่ hypervisor (เครื่องมือการจัดการกระบวนการจำลองเสมือน ) rootkit รองรับระบบปฏิบัติการดั้งเดิมเป็นเครื่องเสมือน สิ่งนี้ช่วยให้สามารถสกัดกั้นกระบวนการต่างๆเช่นกระบวนการที่เรียกฮาร์ดแวร์ (หน้าจอภายนอกเครื่องพิมพ์เราเตอร์อะแดปเตอร์เครือข่าย ฯลฯ ) โดยระบบปฏิบัติการ รูทคิทมีข้อได้เปรียบเหนือไฮเปอร์ไวเซอร์ที่พวกเขาไม่ต้องชาร์จก่อนที่ระบบจะเริ่ม – สามารถอยู่ที่นั่นได้ก่อนที่ระบบจะเลื่อนระดับเป็นเครื่องเสมือน
Rootkit ระดับ 1 ไม่จำเป็นต้องทำการเปลี่ยนแปลงเคอร์เนล นั่นไม่ได้หมายความว่าจะไม่ได้รับผลกระทบ ตัวอย่างจะเป็นความแตกต่างที่เห็นได้ชัดในการตอกบัตร cpu ซึ่งช่วยให้คุณค้นพบการมี Rootkit ในเวลาเดียวกัน

ตัวอย่างของรูทคิทระดับไฮเปอร์ไวเซอร์: “SubVirt” คือ Rootkit ของแล็บที่พัฒนาโดย Microsoft และ University of Michigan มันขึ้นอยู่กับเครื่องเสมือน VMBR “Blue Pill” –  Rootkit พร้อมคีย์ล็อกเกอร์ นี่คือโครงการของ Joanna Rutkowska, ที่ต้องการพิสูจน์ว่าเป็นไปได้ที่จะสร้าง rootkit ที่มองไม่เห็นอย่างสมบูรณ์ แรงบันดาลใจสำหรับชื่อนี้คือภาพยนตร์เรื่อง Matrix
Rootkits ของเฟิร์มแวร์และฮาร์ดแวร์

ในวงแหวน 2 และ 1 ควรกล่าวถึง Rootkit ของเฟิร์มแวร์ (เฟิร์มแวร์ที่ติดตั้งถาวรในอุปกรณ์) และฮาร์ดแวร์ พวกเขาไม่ได้โจมตีระบบโดยตรง เฉพาะรหัสที่รับผิดชอบในการใช้งานฮาร์ดแวร์ (การ์ดเครือข่ายฮาร์ดดิสก์เราเตอร์) รูทคิทดังกล่าวสามารถมุ่งเป้าไปที่รหัส BIOS สำหรับเฟิร์มแวร์มักจะไม่ตรวจสอบความสมบูรณ์ของโค้ด ซึ่งสำหรับแฮกเกอร์ ถือเป็นการเชิญชวนให้ดำเนินการได้อย่างเปิดเผย

Rootkit โหมดเคอร์เนล – ระดับ “0”
วงแหวนระดับ “0” คือระดับที่มีสิทธิ์สูงสุดในระบบปฏิบัติการ โดย Rootkit ได้มุ่งเป้าไปที่หัวใจหลักของระบบ โดยการเพิ่มโค้ด หรือแทนที่บางส่วนของระบบปฏิบัติการได้อย่างสมบูรณ์ (ใช้กับทั้งเคอร์เนล และไดรเวอร์อุปกรณ์)

Rootkits ระดับเคอร์เนลเป็นสิ่งที่อันตรายที่สุด เนื่องจากสามารถเข้าถึงทรัพยากรคอมพิวเตอร์ทั้งหมดได้ไม่จำกัด ในขณะเดียวกันก็เป็นสิ่งที่เขียนยากที่สุด แม้แต่ข้อผิดพลาดเล็กน้อยในโค้ด ก็ทำให้เสถียรภาพของระบบหยุดชะงัก และนี่เป็นวิธีสั้น ๆ สำหรับผู้ใช้ที่ได้รับอนุญาตในการค้นหาRootkit ซึ่ง Rootkitระดับเคอร์เนลที่กระจายอยู่ทั่วไปตัวแรกถูกเขียนขึ้นสำหรับ Windows – NT 4.0 มันได้รับการตีพิมพ์ในปี 1999 บนนิตยสาร Phrack โดย Greg Hoglund
Rootkits ที่มุ่งเป้าไปที่เคอร์เนลนั้น เป็นสิ่งที่ยากที่สุดในการตรวจจับและลบ ส่วนใหญ่เป็นเพราะพวกมันทำงานในระดับเดียวกับระบบปฏิบัติการ และสามารถแก้ไข หรือแม้แต่ลบทั้งหมดได้ แม้กระทั่งการทำงานของระบบที่น่าเชื่อถือที่สุด – รวมถึงการปลอมแปลงซอฟต์แวร์ป้องกันไวรัส การมีรูทคิทในวงแหวน “0” ทำให้แน่ใจว่าไม่มีส่วนใดของระบบที่มีความปลอดภัย

ใน Windows สำหรับ Rootkit นั้นสามารถเปลี่ยนโครงสร้างข้อมูลในเคอร์เนลได้โดยใช้ไฟล์ Direct Kernel Object Manipulation (DKOM) ซึ่งรับผิดชอบการบันทึกและการตรวจสอบ ด้วยการแก้ไขนี้ rootkit จะส่งคืนข้อมูลเท็จให้กับระบบเช่น เกี่ยวกับการดำรงอยู่ของกระบวนการ
อีกวิธีหนึ่งคือการเชื่อมต่อ Rootkit ภายใต้ไฟล์ System Service Descriptor Table (SSDT – อาร์เรย์ของตัวบอกกระบวนการระบบ) อาร์เรย์ประกอบด้วยที่อยู่ของฟังก์ชันระบบปฏิบัติการที่กำลังทำงานอยู่)

โซลูชันนี้ลึกกว่า IAT ที่ทำงานในวงแหวนระดับ “3” เนื่องจากสามารถทำงานได้ทั้งระบบ ไม่ใช่เฉพาะในไลบรารีเดียว ตัวอย่างเช่น rootkit ในรุ่นนี้อาจโจมตี NtQueryDirectoryFile ในไฟล์ Ntoskrnl.exe และซ่อนโฟลเดอร์และไฟล์ในระบบไฟล์ Rootkit ยังสามารถอำพรางได้โดยการแก้ไขเกตเวย์ระหว่างโหมดผู้ใช้งาน และโหมดเคอร์เนล
สำหรับ Linux นั้น rootkit เคอร์เนลจะปรากฏเป็น LKM – โมดูลเคอร์เนลที่โหลดได้ มันใช้งานได้เหมือนใน Windows – สามารถปรับเปลี่ยนตารางการโทรของระบบได้

Bootkits
Bootkits สมควรได้รับตำแหน่งพิเศษในรายการภัยคุกคามเคอร์เนลของระบบ สามารถโจมตีรหัสบูตได้เช่น Master Boot Record (MBR), VBR (Volume Boot Record) หรือบูตเซกเตอร์ (ดังนั้นจึงมีชื่อว่า “bootkity”) วิธีนี้ช่วยให้คุณสามารถโจมตีระบบเข้ารหัสดิสก์ทั้งหมด

Evil Maid Attack – การโจมตีของ bootkit นี้กำหนดเป้าหมายไปที่คอมพิวเตอร์ที่ไม่มีใครดูแล พวกมันมีไว้สำหรับแฮ็กเกอร์ที่ได้เดินทางมายังห้องพักของโรงแรม ที่มีกระเป๋าเดินทางอันมีค่าของลูกค้า ที่ถูกทิ้งไว้เบื้องหลังสำหรับแม่บ้านจอมโกง Bootkit แทนที่โมดูลบูตที่ถูกต้องตามกฎหมายด้วยโมดูลที่ควบคุมโดยอาชญากรไซเบอร์ สำหรับ Malware ที่โหลดด้วยวิธีนี้ ยังคงอยู่ในเคอร์เนลโดยเข้าสู่โหมดป้องกัน เมื่อโหลดเคอร์เนล สิ่งนี้ช่วยให้สามารถควบคุมเคอร์เนล แฮ็กเกอร์ใช้เวลาประมาณ 4 นาทีในการฝังมัลแวร์ลงในระบบที่ไม่มีการป้องกันดังกล่าว

Rootkit ติดตั้งและซ่อนตัวเองได้อย่างไร ?
เส้นทางของการติดตั้ง Rootkit นั้นมีอยู่สองทาง: สามารถทำได้โดยอัตโนมัติหรือด้วยตนเอง กรณีแรกไม่จำเป็นต้องดำเนินการมากนักในส่วนของแฮ็กเกอร์ อย่างไรก็ตามประการที่สองดึงดูดผู้โจมตีในระดับที่มากขึ้น ขั้นแรกเขาต้องเข้าถึงคอมพิวเตอร์ของเหยื่อเช่น โดยใช้ช่องโหว่ด้านความปลอดภัยหรือทำลายรหัสผ่านด้วย m.in. ฟิชชิง (ฟิชชิงโดยการแอบอ้างเป็นสถาบันการเงิน) และทำการติดตั้งเท่านั้น
Rootkit ได้ซ่อนสถานะของมันหลังจากการติดตั้ง และในขณะเดียวกันก็ยังคงสามารถเข้าถึงส่วนประกอบทั้งหมดของระบบได้อย่างถาวร ซึ่งหมายความว่าแฮ็กเกอร์สามารถแก้ไขซอฟต์แวร์ทั้งหมดที่ติดตั้งในอุปกรณ์ รวมถึงโปรแกรมป้องกันไวรัสและโปรแกรมรักษาความปลอดภัยทั้งหมด (เช่น การยกเว้นให้ Rootkit เป็นข้อยกเว้นด้านความปลอดภัย)

ส่วนใหญ่รูทคิทใช้ประโยชน์จากช่องโหว่แล้ว พวกเขายังสามารถซ่อนตัวได้แบบ Trojans ที่ได้ทำการหลอกลวงผู้ใช้งานที่คิดว่าเขากำลังติดตั้งซอฟต์แวร์ที่ไม่เป็นอันตราย และมีประโยชน์ Rootkit สามารถเข้าถึงคอมพิวเตอร์ของคุณได้ โดยใช้ลิงก์ที่ไม่ปลอดภัยไปยังไซต์ที่ติดไวรัส อีเมลที่น่าสงสัย พร้อมไฟล์แนบ ที่แก้ไขการติดตั้งโปรแกรม และแอปพลิเคชันจากแหล่งที่ไม่รู้จักและใช้ USB

แฮกเกอร์ใช้ประโยชน์จากความอยากรู้อยากเห็นของมนุษย์ และทิ้ง ไดรฟ์ หรือแฟลชการ์ดไว้ในที่สาธารณะ เช่น ร้านกาแฟอาคารสำนักงานโรงแรม ในกรณีส่วนใหญ่เครื่องมือค้นหาจะเชื่อมต่อผู้ให้บริการข้อมูลที่พบเข้ากับคอมพิวเตอร์ของเขา จึงทำให้อุปกรณ์ของเขาติดไวรัส
Rootkits บางตัวที่ผู้ใช้งานได้ติดตั้งอย่างมีสติ ตัวอย่างเช่น เพื่อตรวจสอบการทำงานของพนักงาน อื่น ๆ มาพร้อมกับซอฟต์แวร์เชิงพาณิชย์ในระบบจ่ายต่อการติดตั้ง (PPI) การทำงานนี้คล้ายกับ บริษัท ในเครือ แต่จะมีการชำระเงินสำหรับการส่งเสริมการขายหลังจากติดตั้งซอฟต์แวร์เพิ่มเติมซึ่งมักจะซ่อนรูทคิตไว้

วิธีการติดตั้งส่วนใหญ่ได้อธิบายเอาไว้ข้างต้นแล้ว – เมื่อวิเคราะห์ประเภท Rootkit คุณต้องจำไว้ว่า Rootkit มักจะสร้างระบบไฟล์ที่เข้ารหัส และมองไม่เห็นโดยสมบูรณ์ ซึ่งจะซ่อนสำเนาของไฟล์ที่ติดไวรัสหรือมัลแวร์อื่น ๆ (ระดับเคอร์เนล) นอกจากนี้ยังสามารถปรับเปลี่ยนเครื่องมือรักษาความปลอดภัยมาตรฐาน และโปรแกรมป้องกันไวรัส ที่ทำให้เข้าใจยากยิ่งขึ้น

วิธีตรวจหา Rootkit ?
การตรวจจับ Rootkit นั้นทำได้ยากอย่างไม่น่าเชื่อ เพราะมันสามารถซ่อนตัวจากโปรแกรมตรวจจับภัยคุกคามทั้งหมดได้อย่างมีประสิทธิภาพ สิ่งนี้เกี่ยวข้องโดยตรงกับระดับที่ Rootkit และโปรแกรมออกแบบมาเพื่อให้ทำงานได้

หาก Rootkit ทำงานในระดับที่มีสิทธิพิเศษมากกว่าที่โปรแกรมกำลังมองหา แทบจะไม่มีโอกาสที่จะประสบความสำเร็จในการค้นหาดังกล่าวแน่นอน เพราะว่า Rootkit ได้ใช้สิทธิ์ของมันอย่างถูกต้อง

การค้นหา Rootkit ในระบบที่ติดไวรัสแล้วในระดับเคอร์เนล ในทางปฏิบัติไม่ได้ผลลัพธ์ใด ๆ เครื่องตรวจจับ Rootkit ใด ๆ จะสามารถค้นหาได้เฉพาะสิ่งที่เสียหาย การสะกดคำผิด หรือทำงานในระดับที่ต่ำกว่าซอฟต์แวร์ตรวจจับระดับเคอร์เนล

สำหรับการตรวจหา Rootkit จากการใช้งานทั่วไปคือ :

วิธีการทางพฤติกรรม – นั่นคือการเปรียบเทียบรูปแบบของพฤติกรรมที่เป็นอันตราย กับพฤติกรรมของระบบ อาจมีการเปลี่ยนแปลงเวลาการใช้งาน CPU หรือระหว่างการสืบค้น API โดย Rootkit บางตัวมีผลกระทบอย่างมากต่อการเปลี่ยนแปลงเหล่านี้ ดังนั้นวิธีนี้จึงเป็นหนึ่งในวิธีที่ง่ายกว่าในการดำเนินการ แต่ในขณะเดียวกันก็เป็นผลลัพธ์ที่ผิดพลาดที่สุดอย่างหนึ่ง
หลังจากการอัปเดตความปลอดภัยของ Windows Alureon rootkit ทำให้ระบบขัดข้อง – การอัปเดตนี้แสดงข้อผิดพลาดในรหัสการออกแบบทำให้ตรวจพบได้
การสแกนแบบใช้ Signature  – มักถูกใช้โดยโปรแกรมป้องกันไวรัส เพื่อตรวจจับมัลแวร์ โค้ดที่เป็นอันตรายที่นักวิจัยดึงมาจะถูกเพิ่มลงในฐานข้อมูลและโปรแกรมป้องกันไวรัส – การสแกนดิสก์ – จะค้นหา Signature ที่รู้จัก (ซึ่งอยู่ในฐานข้อมูล) ดังนั้นการสแกน Signature จึงใช้ได้ผลกับ Rootkit ที่ได้ทำเครื่องหมายไว้แล้วเท่านั้น
การสแกนหาความแตกต่าง (cross-comparison) – เปรียบเทียบข้อมูลดิบที่ไม่ถูกทำลายกับเนื้อหาที่อาจติดไวรัสที่ส่งคืนโดย API โดยทั่วไป คุณเปรียบเทียบการเขียนไบนารีบนดิสก์ กับสำเนาของสิ่งเหล่านี้ ในหน่วยความจำหรือรีจิสทรีของ Windows กับโครงสร้างทางกายภาพที่สอดคล้องกันของดิสก์ อย่างไรก็ตาม Rootkit บางตัวสามารถค้นพบวิธีนี้ในการค้นหา และจับคู่ผลการสแกนทำให้ไม่สามารถตรวจพบได้
เหตุการณ์ที่เป็นข่าวใหญ่ที่อธิบายไว้ก่อนหน้านี้เกี่ยวกับบริษัท Sony BMG ซึ่งถูกตรวจพบโดย RootkitRevealer ได้อย่างแม่นยำด้วยวิธีการสแกนหาความแตกต่างนั่นเอง

ทำการเชื่อมต่อระบบทางเลือกและที่ได้พิสูจน์แล้ว – นี่เป็นวิธีที่ดีที่สุดในการตรวจจับรูทคิทในระดับระบบปฏิบัติการ คุณต้องปิดคอมพิวเตอร์เชื่อมต่อสื่อที่เชื่อถือได้เช่น USB หรือ CD-ROM ซึ่งมีระบบบูตและตรวจสอบไดรฟ์ที่เราสงสัยว่าติดไวรัส ประสิทธิภาพของเทคนิคนี้เกิดจากการที่รูทคิตไม่มีการใช้งานในระหว่างการค้นหา – หากคอมพิวเตอร์ที่ติดไวรัสไม่ทำงาน Rootkit ก็จะยังคงไม่ทำงาน
การวิเคราะห์การถ่ายโอนข้อมูลหน่วยความจำเสมือน หรือการถ่ายโอนข้อมูลเคอร์เนลระบบอย่างสมบูรณ์ – มันค่อนข้างยากมากที่จะทำตามขั้นตอนนี้ แต่มันก็มีประสิทธิภาพดี – ข้อมูลส่วนใหญ่ของ Rootkit มักไม่สามารถซ่อนตัวอยู่ได้ อย่างไรก็ตาม Rootkit ในระดับไฮเปอร์ไวเซอร์บางตัว อาจตรวจพบความพยายามในการถ่ายโอนข้อมูลหน่วยความจำ
ตรวจสอบความสมบูรณ์ – เพื่อตรวจสอบว่าโมดูลในโฟลเดอร์การติดตั้งแอปพลิเคชันต่าง ๆ นั้น ไม่มีการแก้ไข หรือเกิดความเสียหาย หากเกิดเหตุการณ์ขึ้น โมดูลจะถูกจัดประเภทว่าเสียหาย หากลายเซ็นดิจิทัลที่มอบให้โดยผู้เผยแพร่ซอฟต์แวร์นั้นไม่ถูกต้อง สิ่งนี้ช่วยให้คุณค้นพบการเปลี่ยนแปลงรหัสที่ไม่ได้รับอนุญาตในไลบรารีบนดิสก์ อย่างไรก็ตามวิธีนี้ใช้ได้ผลกับการเปลี่ยนแปลงที่เกิดขึ้น หลังจากติดตั้งแอปพลิเคชันเท่านั้น
เราจะลบ Rootkit ออกไปได้อย่างไร?
คุณสามารถลองติดตาม Rootkit ด้วยตัวเอง และใช้วิธีการลบออกได้ด้วยตนเอง ซึ่งน่าเสียดายที่ใช้เวลานานมาก และต้องใช้ความรู้เฉพาะทาง โชคดีที่แอนตี้ไวรัสที่เป็นที่รู้จัก และเป็นที่นิยมจำนวนมากได้รับการติดตั้งระบบป้องกัน Rootkits

เราสามารถแนะนำโซลูชันที่ใช้โดย Bitdefender อย่างไรก็ตามหากโปรแกรมป้องกันไวรัสของคุณไม่สามารถกำจัดภัยคุกคามได้ คุณสามารถใช้โปรแกรมที่กำหนดเป้าหมายไปที่ Rootkit โดยเฉพาะ ตัวอย่างของโปรแกรมดังกล่าวสำหรับ Windows ดังกล่าวข้างต้น คือ Rootkit Revealer หรือระบบอื่น ๆ ก็ไม่ได้ถูกละเลย สำหรับ Linux และ MacOS chkrootkit และ rkhunter (สำหรับ UNIX) ที่ถูกสร้างขึ้นและอื่น ๆ

อย่างไรก็ตาม ปัญหามักจะคล้ายกับการต่อสู้ชั่วนิรันดร์ ระหว่างความดีและความชั่ว ยิ่งโปรแกรมตรวจจับ Rootkit มีประสิทธิภาพมากเท่าไหร่ นักพัฒนาของพวกเขาก็มุ่งเน้นไปที่การเปลี่ยนรหัสให้เข้าใจยากขึ้นเท่านั้น

Rootkits ที่โจมตีองค์ประกอบที่สำคัญที่สุดของระบบ – เคอร์เนล – แทบจะเป็นไปไม่ได้ที่จะลบออก สำหรับกระบวนนี้การค่อนข้างนี้ซับซ้อนมาก โดยปกติจะจบลงด้วยการ Format ดิสก์ทั้งหมด และต้องติดตั้งระบบปฏิบัติการใหม่ ซึ่งจำเป็นต้องมาจากแหล่งที่เชื่อถือได้

เมื่อระบบปฏิบัติการพัฒนาขึ้น Rootkit จะได้รับความสนใจมากขึ้นเรื่อย ๆ ดังนั้นการทำเครื่องหมายไดรเวอร์ระดับเคอร์เนล ที่บังคับจึงถูกนำมาใช้ใน Windows 64 บิต ขั้นตอนนี้มีวัตถุประสงค์เพื่อทำให้ยากต่อการฝังรหัสแปลกปลอมที่ระดับสูงสุด ของระบบ Microsoft ได้สร้างเครื่องมือลบ Rootkit: Microsoft Windows Malicious Software Removal Tool – จะสแกนคอมพิวเตอร์ของคุณ ก่อนที่คุณจะเริ่มระบบ Windows Defender Offline – จะสร้างสภาพแวดล้อมพิเศษก่อนที่ระบบจะเริ่มทำงานพยายามตรวจหา Rootkit ที่มีอยู่

วิธีป้องกัน Rootkits
จนถึงทุกวันนี้ก็ยังไม่มีใครรู้ว่า “การป้องกันดีกว่าการรักษา” ซึ่งไม่เพียงแต่ใช้ในแง่ของการป้องกันสุขภาพเท่านั้น แต่ยังรวมถึงการปกป้องคอมพิวเตอร์ และอุปกรณ์แบบพกพาอื่น ๆ อีกด้วย ผู้พัฒนาซอฟต์แวร์ระบบเองก็จำเป็นสำหรับสิ่งนี้เช่นกัน

ในปี 2009, University of North Carolina, ด้วยความร่วมมือกับ Microsoft สร้าง anti-rootkit สำหรับระดับไฮเปอร์ไวเซอร์ – “Hooksafe“หน้าที่ของมันคือการป้องกันทั่วไปจาก Rootkit ที่มีเป้าหมาย แม้แต่ที่เคอร์เนลของระบบ ด้วยการถือกำเนิดของ Windows 10 คุณลักษณะใหม่ได้ปรากฏขึ้นนั่นก็คือ: “Device Guard” ซึ่งใช้กระบวนการ Virtualization เพื่อให้การป้องกัน Rootkit จากภายนอกที่เป็นอิสระ

อย่างไรก็ตามไม่มีวิธีใดที่มีประสิทธิภาพมากไปกว่าแอนตี้ไวรัสที่ดี พร้อมแอนตี้ Rootkits เช่น Bitdefender

Rootkitsนั้นร้ายกาจและเพื่อป้องกันตัวจากพวกมัน คุณต้องใส่ใจกับพฤติกรรมบนโลกออนไลน์ของคุณ:

หลีกเลี่ยงหน้าเพจที่น่าสงสัย เปิดลิงก์ และไฟล์แนบที่ไม่ปลอดภัยจากอีเมล หรือจากผู้ส่งที่ไม่รู้จัก
ระวังโปรแกรมฟรี โดยเฉพาะ เกมส์ เพลง และภาพยนตร์ที่ละเมิดลิขสิทธิ์บนเว็บไซต์
ให้ทำการอัปเดตระบบให้ใหม่อยู่เสมอ และตลอดเวลา
อย่าให้สิทธิ์เข้าถึงอุปกรณ์ของคุณอย่างเต็มที่กับแอปทั้งหมดที่คุณติดตั้ง – หรือแอปโดยทั่วไปคุณไม่จำเป็นต้องใช้มาก
ใช้ไฟร์วอลล์, แอนตี้ไวรัส, และตัวสแกน Rootkit
ทำการทดสอบความปลอดภัยเป็นประจำ
พยายามใช้ระบบพิสูจน์ตัวตนแบบหลาย ๆ ปัจจัย
ปัญหาของ Rootkits ไม่ได้สงวนไว้เฉพาะกลุ่มผู้ใช้งานที่ได้ทำการเลือกแล้วเท่านั้น แต่มีเป้าหมายที่พวกเราเกือบทั้งหมด นั่นเป็นเหตุผลว่าทำไมการดูแลแล็ปท็อป เดสก์ท็อป และอุปกรณ์เคลื่อนที่ให้ปลอดภัย ไม่มีใครอยากจะถูกแอบมอง และยิ่งคุณรู้เกี่ยวกับภัยคุกคามที่อาจเกิดขึ้นมากเท่าไหร่ คุณก็จะระมัดระวังป้องกันภัยคุกคามได้ง่ายขึ้นเท่านั้น

 

ประวัติของ Rootkits – พวกมันมาจากไหน?
 

ประวัติของรูทคิทเริ่มขึ้นในยุค 80 หรือของศตวรรษที่แล้ว จริง ๆ แล้วอาจกล่าวได้ว่าเทมเพลตของพวกมัน ได้ถูกสร้างขึ้นโดย Ken Thompson ซึ่งทำงานที่ Bell Labs ซึ่งเป็นหนึ่งในผู้สร้าง unix อีกด้วย

ในปี 1972 UNIX ได้รับการเขียนใหม่จาก B ถึง C คิดค้นโดย Thompson ดังนั้นเคอร์เนล UNIX จึงทำงานใน C. Ken Thompson ในปี 1983 ได้ปรากฎเหตุการณ์ exploit – โปรแกรมที่ใช้ประโยชน์จากข้อบกพร่องของซอฟต์แวร์ที่มีอยู่ ซึ่งได้รับการออกแบบมาเพื่อให้สามารถล็อกออนเข้าสู่ระบบได้ โดยไม่เปิดเผยรหัสที่เป็นอันตราย นั่นคือเมื่อรวบรวมคำขอเป็น C สิ่งนี้เกิดขึ้นผ่านคอมไพเลอร์ที่แก้ไข ซึ่งเป็นโปรแกรมที่แปลรหัสภาษาต้นฉบับเป็นรหัสเดียวกันในภาษาอื่นได้โดยอัตโนมัติ

คอมไพลเลอร์ที่แก้ไข ได้ตรวจพบความพยายามของผู้ใช้ในการคอมไพล์ (แปล) คำสั่งที่ออกให้กับ UNIX และสร้างโค้ดที่เปลี่ยนแปลง รหัสดังกล่าวยอมรับรหัสผ่านที่ผู้ใช้งานได้ป้อนอย่างถูกต้อง และในเวลาเดียวกันรหัสผ่าน “ลับ ๆ” เพิ่มเติมที่แฮ็กเกอร์ให้มา

นอกจากนี้คอมไพลเลอร์ที่ได้รับการแก้ไข ยังมีผลกระทบโดยตรงต่อการอัปเดตทั้งหมดของคอมไพลเลอร์ดั้งเดิม และแทรกช่องโหว่เดียวกันลงในนั้น การเรียกดูซอร์สโค้ด การเข้าสู่ระบบ และรหัสคอมไพเลอร์ที่อัปเดตไม่ได้ทำอะไรเลย – โค้ดที่เป็นอันตรายมักจะมองไม่เห็น และยังคงจับข้อมูล Rootkits ทำงานบนพื้นฐานที่คล้ายกันกับการแสวงประโยชน์นี้
และไวรัสตัวแรกที่บันทึกไว้บน IBM-PC ที่ทำงานบน DOS (1986) – Brain – ได้ใช้เทคนิคนี้ในการซ่อน มันโจมตีบูตเซกเตอร์โดยการสกัดกั้นความพยายามที่จะอ่าน และเปลี่ยนเส้นทางไปยังตำแหน่งที่เก็บสำเนาของบูตเซกเตอร์ดั้งเดิม  ซึ่งมันได้แพร่กระจายผ่านฟล็อปปี้ดิสก์นั่นเอง

แน่นอนว่าช่วงเวลาที่ผ่านไปทำให้เกิดการพัฒนาวิธีการปิดบังไวรัสใน DOS เหนือสิ่งอื่นใด โดยการจับข้อมูลที่ระดับต่ำสุดของดิสก์ – INT 13H BIOS – โดยการขัดจังหวะการเชื่อมต่อเพื่อซ่อนการแก้ไขไฟล์ที่ไม่ได้รับอนุญาต

การเพิ่มขึ้นของรูทคิททำให้เกิดเรื่องอื้อฉาวมากมายในระดับโลก หนึ่งในนั้นคือการค้นพบในปี 2005 โดยวิศวกรซอฟต์แวร์ Mark Russinovich ของรูทคิทในซอฟต์แวร์ Extended Copy Protection software โดย First 4 ซึ่งเผยแพร่บนซีดีโดย Sony BMG หนึ่งในองค์ประกอบของซอฟต์แวร์ คือเครื่องเล่นเพลง และโปรแกรมนี้มีวัตถุประสงค์เพื่อป้องกันการคัดลอกและการจัดการลิขสิทธิ์ดิจิทัล

จากนั้น Russinovich ได้พัฒนาเครื่องมือตรวจจับรูทคิต RootkitRevealer, ซึ่งค้นพบในคอมพิวเตอร์เครื่องหนึ่งของเขา ว่ามีการติดตั้งเครื่องเล่นเพลงพร้อมกับ Rootkits ที่จำกัดการเข้าถึงซีดีของผู้ใช้ โดยรวมแล้วนี่เป็นเหตุการณ์แรกในระดับใหญ่ที่ทำให้ผู้ใช้ตระหนักถึงอันตรายของ Rootkits อย่างมาก แม้ว่า Sony BMG จะออกการอัปเดตอย่างรวดเร็ว เพื่อถอนการติดตั้ง Rootkits แต่ก็สายไปเสียแล้ว

ผู้ใช้งานยังเสี่ยงต่อการถูกโจมตีมากขึ้น ในสหรัฐอเมริกายังมีการฟ้องร้องร่วมกันกับ Sony BMG อีกตัวอย่างหนึ่งคือเรื่องอื้อฉาวระดับสูงที่เรียกว่า Greek Watergate มันเกี่ยวข้องกับการดักฟังโทรศัพท์มือถือมากกว่า 100 เครื่องที่ทำงานบนเครือข่าย Vodafone Greece อย่างผิดกฎหมาย ซึ่งส่วนใหญ่ใช้โดยเจ้าหน้าที่ระดับสูงของรัฐบาล กระบวนการดักฟังเริ่มขึ้นเมื่อประมาณเดือนสิงหาคม พ.ศ. 2547 และดำเนินไปจนถึงเดือนมีนาคม พ.ศ. 2548 แต่ไม่มีการระบุผู้เขียนดักฟัง รูทคิทโจมตี Ericsson’s AX telephone exchange ที่นี่

ซอฟต์แวร์ดังกล่าว สามารถตรวจสอบกิจกรรมของกระบวนการการไหลของข้อมูล สามารถเข้าถึงรหัสผ่าน และการเข้าสู่ระบบได้ การมีอยู่ของมันถูกตรวจพบโดยข้อผิดพลาดในการอัปเดต Rootkits ซึ่งปิดกั้นความสามารถในการส่ง SMS ช่องโหว่ที่รายงานต่อ Ericsson ซึ่งได้เปิดเผยว่ามีซอฟต์แวร์ดักฟังที่ผิดกฎหมาย พร้อมกับ Rootkits และบล็อกข้อมูลที่ซ่อนอยู่พร้อมรายการหมายเลขโทรศัพท์ที่ได้ทำการตรวจสอบ