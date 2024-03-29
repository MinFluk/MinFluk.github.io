การเข้ารหัสลับแบบสมมาตร (Symmetric Encryption)

การเข้ารหัสแบบสมมาตร หรือ Symmetric Encryption บางครั้งอาจเรียกว่าการเข้ารหัสแบบดั้งเดิม ( Conventional Encryption) สำหรับสาเหตุที่เรียกว่าสมมาตร เพราะมีกระบวนการเข้ารหัสและถอดรหัสที่เป็นกระบวนการแบบเดียวกัน ในการเข้ารหัสแบบนี้ บางครั้งก็จะเรียกว่า การเข้ารหัสแบบ Secret Key หรือ Single Key ก็ขอให้เข้าใจว่าเป็นการเข้ารหัสในแบบเดียวกันนี้

การเข้ารหัสแบบนี้ เป็นการเข้ารหัสที่มีมาแต่เดิม จนถึงประมาณทศวรรษที่ 70 จึงได้มีการพัฒนาวิธีการเข้ารหัสในอีกรูปแบบหนึ่งในชื่อว่า Asymmetric Encryption หรือ Public-Key Encryption ซึ่งจะกล่าวถึงในตอนต่อไป

และแม้ว่าจะมีการพัฒนาการเข้ารหัสในรูปแบบใหม่ ๆ แต่การเข้ารหัสในแบบนี้ ก็ยังได้รับการปรับปรุง และยังมีการใช้งานอยู่มากในปัจจุบัน ในบทนี้จะกล่าวถึงรูปแบบโดยทั่วไปของการเข้ารหัสในแบบดั้งเดิม และทำความเข้าใจกับแต่ละอัลกอริทึมที่ใช้ในการเข้ารหัสที่อยู่ในกลุ่มนี้จำนวน 3 ตัวด้วยกัน คือ DES, 3DES และ AES นอกจากนั้นยังได้พิจารณาไปถึงแนวทางในการใช้งานการเข้ารหัสในแบบนี้ด้วย อนึ่ง ในบทนี้จะขอเรียกวิธีการเข้ารหัสแบบนี้ว่า Secret Key

หลักการของ Secret Key

ในกระบวนการในการเข้ารหัสของ Secret Key จะมีส่วนประกอบอยู่ด้วยกันทั้งหมด 5 ส่วนด้วยกัน ได้แก่


รูปแบบอย่างง่ายของการเข้ารหัสแบบ Secret Key
Plaintext Input หมายถึง ข้อความเริ่มแรกที่ยังไม่ได้เข้ารหัส และมีความต้องการที่จะเข้ารหัส
Encryption Algorithm เป็นกระบวนการแปลงข้อความ Plaintext ไปเป็นข้อความที่ไม่สามารถอ่านได้
Secret Key เป็นรหัสที่ต้องป้อนเข้าไปในกระบวนการเข้ารหัส โดยการแปลงข้อความของอัลกอริทึมในการเข้ารหัส จะขึ้นกับ Secret Key ที่ป้อนเข้าไป
Ciphertext เป็นผลลัพธ์ที่ได้จากการเข้ารหัส โดยจะขึ้นกับ Plaintext และ Secret Key ที่ป้อนเข้าไป ข้อความที่เหมือนกัน แต่มี Key ที่ต่างกัน จะให้ผลลัพธ์ที่ต่างกันด้วย
Decryption Algorithm เป็นกระบวนการย้อนกลับของการเข้ารหัส โดยเมื่อใส่ Ciphertext และ Key ที่ถูกต้องเข้าไป จะต้องได้ข้อความเดิมหรือ Plaintext ออกมา
ในการใช้งานการเข้ารหัสในแบบ Secret Key นี้ จะมีความจำเป็น 2 ประการเพื่อให้การใช้งานได้ผลดี คือ

1. อัลกอรึทึมในการเข้ารหัส จะต้องมีความแข็งแกร่ง (Strong) ทั้งนี้เนื่องจากอัลกอริทึมที่เป็นแบบ Secret Key นี้ มักจะมีการเปิดเผยวิธีการอยู่แล้ว ดังนั้นผู้อื่นก็ย่อมจะรู้วิธีการเข้าและถอดรหัสเช่นเดียวกัน ดังนั้นจากส่วนประกอบของกระบวนการเข้ารหัส ผู้อื่นก็จะรู้ถึง Ciphertext เพราะสามารถดักได้จากกระบวนการส่ง และสามารถรู้อัลกอริทึม แต่สิ่งที่ผู้อื่นไม่รู้ก็คือ Key ดังนั้นเพื่อให้ได้ข้อความต้นฉบับกลับมา ก็จะต้องหา Key เพื่อจะได้ใช้ในการถอดรหัสให้ได้ ดังนั้นอัลกอริทึมนี้ จะต้องมีความแข็งแกร่งมากพอที่จะปิดบัง Key เอาไว้ แม้ว่าจะได้ทั้ง Plaintext และ Ciphertext ก็ไม่สามารถหา Key ได้

2. จากที่ได้กล่าวมา จะเห็นว่าหัวใจของกระบวนการเข้ารหัสแบบนี้ คือ Key ซึ่งจะเห็นได้ว่า แม้ว่าจะทราบถึงส่วนประกอบต่าง ๆ ทั้งหมด แต่ไม่ทราบ Key ก็ไม่สามารถจะ Break กระบวนการได้ ดังนั้นการรักษา Key จึงมีความสำคัญอย่างยิ่ง และวิธีการเข้ารหัสในแบบ Secret Key นี้ ก็จะถือว่า กระบวนการรับส่ง หรือ แจกจ่าย Key จะต้องมีความปลอดภัย โดยจะถือว่าผู้รับสารและผู้ส่งสาร จะต้องมีช่องทางในการรับส่ง Key อย่างปลอดภัยอยู่แล้ว เพราะหากมีผู้อื่นได้ Key ไป กระบวนการเข้ารหัสเพื่อรักษาความลับ ก็จะไม่เป็นความลับอีกต่อไป

จากที่กล่าวมา จะเห็นได้ว่าความความปลอดภัยของการเข้ารหัส หรือ การรักษาความลับระหว่างการรับส่งข้อมูล ของวิธีการเข้ารหัสแบบ Secret Key นี้จะขึ้นกับความลับของ Key ไม่ใช่ความลับของอัลกอริทึม ทั้งนี้เนื่องจากการได้มาซึ่งอัลกอริทึมสัก 1 ตัวที่ความสามารถตามความต้องการของหลักการเข้ารหัสแบบ Secret Key นั้นเป็นเรื่องไม่ง่ายนัก ดังนั้นหากใช้วิธีให้ความลับอยู่ที่ อัลกอริทึมแล้ว หากถูกเปิดเผยก็จะต้องสร้างอัลกอริทึมใหม่ขึ้นมา ในขณะที่ใช้วิธีให้ความลับอยู่ที่ Key แล้ว หาก Key มีการเปิดเผย ก็เพียงแต่สร้าง Key ใหม่ขึ้นมาเท่านั้น ซึ่งเป็นเรื่องที่ง่ายกว่ามาก

และโดยการเปิดเผยอัลกอริทึมนี้เอง ที่ทำให้การใช้งานการเข้ารหัส Secret Key สามารถใช้งานได้ในวงกว้าง เพราะไม่จำเป็นที่แต่ละคนจะต้องสร้างอัลกอรึทึมในการเข้ารหัสของตัวเองขึ้นมา แต่ใช้สิ่งที่เป็นมาตรฐานเหมือน ๆ กัน แต่ใช้ Key ที่ต่างกัน และจากการที่ทุกคนรู้อัลกอริทึม ก็ไม่จำเป็นที่จะต้องบอกวิธีการให้อีกฝ่ายทราบ เพียงแต่เข้าใจตรงกันว่ากำลังใช้อัลกอริทึมไหน และใช้ Key อะไรอยู่ก็เพียงพอแล้ว นอกจากนั้นยังสามารถสร้างการเข้ารหัสในรูปของฮาร์ดแวร์ได้ด้วย

การเข้ารหัส
ระบบการเข้ารหัสนั้น โดยทั่วไปจะมีการพิจารณาใน 3 มุมมองด้วยกัน คือ

1. รูปแบบของการกระทำที่ใช้ในการแปลงจาก Plaintext ไปเป็น Ciphertext ในอัลกอริทึมของการเข้ารหัสทุกรูปแบบมักจะตั้งอยู่บนหลักการ 2 หลักด้วยกัน คือ การแทนที่ (Substitution) และการสลับที่ (Transposition) โดยหลักการแทนที่นั้น จะใช้วิธีแทนส่วนประกอบของ Plaintext (บิต กลุ่มของบิต หรือไบต์ หรือตัวอักษร) ด้วยส่วนประกอบอีกกลุ่มหนึ่ง และวิธีการสลับที่นั้น จะเป็นการจัดลำดับของบิต กลุ่มของบิต หรือไบต์ หรือตัวอักษร ใหม่ให้มีรูปแบบที่เปลี่ยนไป โดยในระหว่างกระบวนการทำนั้น จะต้องไม่มีข้อความ หรือส่วนใด ๆ ของข้อความที่หายไป (เพื่อให้กระบวนการย้อนกลับสามารถทำได้)

2. จำนวนของคีย์ที่ใช้ โดยหากทั้งผู้รับและผู้ส่งมีการใช้คีย์เดียวกัน ก็จะเรียกวิธีการเข้ารหัสนั้นว่า Symmetric Key หรือ Secret Key หรือ Single Key หรือ Conventional Encryption แต่หากผู้รับและผู้ส่งใช้คีย์ที่ต่างกัน ก็จะเรียกว่า Asymmetric Key หรือ Two Key หรือ Public Key

3. ลักษณะที่อัลกอริทึมกระทำกับข้อความต้นฉบับ โดยจะแบ่งออกเป็น 2 แบบ คือ Block Cipher โดยวิธีการนี้ คือ การแบ่งข้อมูลออกเป็นส่วน ๆ ที่มีความยาวเท่ากัน แล้วจึงประมวลผลข้อมูลไปทีละ Block โดยจะได้ผลลัพธ์เป็น Block เช่นเดียวกัน สำหรับอีกแบบ คือ Stream Cipher ซึ่งมีการประมวลผลไปทีละกลุ่ม (อาจเป็นบิต ไบต์ หรือกลุ่มของบิต) โดยผลลัพธ์ก็จะออกมาในทำนองเดียวกัน

การแกะรหัส (Cryptanalysis)

ในระบบของการเข้ารหัสใด ๆ จะต้องพิจารณาถึงความเป็นไปได้ที่จะมีการแกะรหัสที่ได้เข้าไว้ออกมา ว่ามีความยากหรือง่ายแค่ไหน ก่อนจะนำไปใช้งาน โดยการแกะรหัสก็เช่นเดียวกับการเข้ารหัส คือ มีหลายวิธี โดยขึ้นกับรูปแบบของการเข้ารหัสว่าเป็นแบบใด และมีข้อมูลให้ใช้มากน้อยแค่ไหน


ชนิดของการ Attack กับข้อความที่เข้ารหัสแบบต่าง ๆ
ตารางข้างต้นได้รวบรวมประเภทของการแกะรหัสต่าง ๆ โดยแยกตามข้อมูลที่ทราบ โดยชนิดที่แกะรหัสได้ยากที่สุด คือ แบบแรกที่เป็น Ciphertext Only เพราะไม่รู้ว่าวิธีในการเข้ารหัสเป็นวิธีไหน แต่โดยทั่วไปแล้ว เรามักจะถือว่าฝ่ายตรงข้ามรู้วิธีการเข้ารหัส ดังนั้นการแกะรหัสที่สามารถทำได้ จะเรียกว่าวิธี Brute Force นั่นก็คือ การลองทุก Key ที่สามารถเป็นได้ ซึ่งวิธีการนี้ ในทางทฤษฎีแล้ว จะถือว่าจะสามารถแกะได้แน่นอน เพียงแต่จะใช้เวลาเท่าไรแค่ไหนเท่านั้น โดยหาก Key มีความยาวมาก ๆ จนเวลาที่ใช้มากเกินกว่าจะใช้งานได้จริง ก็ถือว่ามีความปลอดภัยมากเพียงพอ อย่างไรก็ตามนอกจากวิธี Brute Force แล้ว ยังอาจใช้การเดาโดยใช้ Dictionary หรือคำที่ใช้บ่อย หรือคำที่เกี่ยวข้องก็อาจทำให้การแกะรหัสสามารถทำได้รวดเร็วมากขึ้น

วิธี Ciphertext Only เป็นวิธีที่ป้องกันได้ง่ายที่สุด เพราะฝ่ายตรงข้ามมีข้อมูลให้ใช้น้อย แต่บางครั้งที่ฝ่ายตรงข้ามสามารถหากข้อมูลได้เพิ่ม เช่น อาจดักจับ Plaintext ได้บางส่วน หรือ รู้รูปแบบข้อมูลที่แน่นอนบางส่วน ก็จะใช้วิธีการแกะในแบบที่ 2 คือ Known Plaintext ซึ่งจะทำให้ผู้แกะสามารถพิจารณาข้อมูลที่เข้าและออก และอาจสามารถหา Key ได้

สำหรับวิธี Chosen Plaintext นั้นจะเกิดจากกรณีที่ผู้แกะ สามารถเข้าถึงเครื่องหรือระบบที่ใช้ในการเข้ารหัส และสามารถป้อนข้อความที่ตนเองได้เลือกเอาไว้ ซึ่งผู้แกะสามารถจะเลือกข้อความที่มีลักษณะเฉพาะ ตามที่ต้องการใส่เข้าไปในระบบ เพื่อดูผลลัพธ์ที่ออกมาว่ามีลักษณะอย่างไร ก็จะทำให้ผู้แกะสามารถจะหาโครงสร้างของ Key ได้ง่ายมากขึ้นไปอีก และในทางกลับกันหากผู้แกะสามารถเข้าถึงเครื่องหรือระบบที่ใช้ในการถอดรหัส ก็สามารถจะป้อน Ciphertext เพื่อดูว่าจะได้ Plaintext อะไรออกมา ได้เช่นเดียวกัน สำหรับวิธีสุดท้าย คือ กรณีที่ผู้แกะสามารถเข้าถึงทั้งระบบที่เข้าและถอดรหัส ซึ่งสามารถจะลองได้ทั้ง 2 รูปแบบ

อย่างไรก็ตาม ในทางปฏิบัติแล้ว การแกะที่มักจะเกิดขึ้น มักจะเกิดในกรณีที่ 1 คือ รู้แต่ Ciphertext อย่างเดียว หรืออาจจะรู้ Plaintext บางส่วนเท่านั้น เพราะการที่ผู้แกะเข้าถึงระบบได้นั้น เป็นสิ่งที่เกิดขึ้นได้ยาก ดังนั้นโดยทั่วไปมักจะออกแบบอัลกอริทึมในการเข้ารหัสที่สามารถต่อต้านกันวิธีที่ 1 และ 2 ได้

โดยทั่วไปในการออกแบบอัลกอริทึมในการเข้ารหัสนั้น จะถือว่าประสบความสำเร็จในการรักษาความปลอดภัย เมื่อรหัสที่สร้างขึ้นมาโดยอัลกอริทึมนั้น สามารถบรรลุข้อกำหนดใดข้อกำหนดหนึ่งใน 2 ข้อกำหนดต่อไปนี้

- ค่าใช้จ่ายที่ต้องใช้ในการถอดรหัสจะต้องมากกว่ามูลค่าของข้อมูลที่เข้ารหัส

- เวลาที่ใช้ในการถอดรหัส จะต้องมากกว่าอายุการใช้งานของข้อมูลนั้น

ทั้งนี้เนื่องจากความต้องการข้อมูลที่เข้ารหัสก็เนื่องจากความต้องการนำข้อมูลนั้นไปใช้ประโยชน์ แต่หากค่าใช้จ่ายที่ต้องใช้ในการถอดรหัส มีมูลค่ามากกว่าตัวข้อมูลเองแล้ว ก็ไม่มีความคุ้มค่าในการถอดรหัส อย่างไรก็ตามการประเมินมูลค่าของข้อมูลนั้นมักเป็นเรื่องที่พิจารณาได้ยาก ดังนั้นโดยส่วนใหญ่จึงมักประเมินความปลอดภัยของอัลกอริทึมเอาไว้ที่ข้อหลังมากกว่า เพราะเป็นสิ่งที่พิจารณาได้ง่าย ดังนั้นหากสมมติว่าอัลกอริทึมที่ออกแบบไม่มีจุดอ่อน ซึ่งหมายความว่าการจะถอดรหัสจะต้องใช้วิธีที่เรียกว่า Brute-Force เพียงอย่างเดียว


วิธีการที่เรียกว่า Brute-Force นั้น เป็นวิธีการที่ลองเดา Key ในทุก ๆ ค่าที่เป็นไปได้ ซึ่งหมายความว่า จะต้องสามารถแกะได้อย่างแน่นอน สมมติว่าโดยเฉลี่ยจะสามารถแกะ Key ออกได้ เมื่อได้ลอง Key ที่เป็นไปได้จำนวนเท่ากับครึ่งหนึ่งของ Key ทั้งหมด ในตารางข้างบนนี้ จะแสดงว่าจะต้องใช้เวลาเท่าไร ในการแกะ Key ที่มีความยาวต่าง ๆ กัน โดยสมมติว่าในการแกะรหัส 1 ครั้ง จะใช้เวลาเท่ากับ 1 ไมโครวินาที จะเห็นว่าความยาวของ Key ที่เริ่มมีความปลอดภัย คือ ที่ 56 บิต แต่หากใช้คอมพิวเตอร์ความเร็วสูง เช่น เครื่องซูเปอร์คอมพิวเตอร์แบบ MPP ซึ่งสมมติว่ามีความเร็วในการทำงานเท่ากับการแกะรหัส 100 ล้านครั้งต่อวินาที จะเห็นว่าความยาวของ Key ที่เริ่มมีความปลอดภัย คือ 128 บิต (ปัจจุบันความยาวคีย์ที่ถือว่าปลอดภัย คือ 256 บิต)

Feistel Cipher Structure
ในการเข้ารหัสข้อมูลทุกรูปแบบที่ใช้อัลกอริทึมในกลุ่มที่เป็นแบบ Secret Key นี้ จะมีโครงสร้างในการเข้ารหัสโดยรวม เป็นแบบที่นำเสนอโดย Horst Feistel แห่ง IBM ในปี 1973 ซึ่งแสดงในรูปด้านล่าง โดยอินพุตจะป้อนเข้าสู่อัลกอริทึมในการเข้ารหัสในลักษณะที่เป็นกลุ่มของข้อมูลที่มีความยาวเท่า ๆ กัน เรียกว่า Block โดยจะมีความยาวของกลุ่มข้อมูลเท่ากับ 2w โดยใช้คีย์ Key K จากนั้นกลุ่มข้อมูลจะแบ่งออกเป็น 2 ส่วนเท่าๆ กัน คือ L0 และ R0 จากนั้นข้อมูลทั้ง 2 ส่วน จะป้อนเข้าสู่การประมวลผล โดยหลักของการเข้ารหัสในแบบนี้ จะอาศัยการประมวลผลซ้ำ ๆ กัน เพื่อสร้างความซับซ้อน โดยในแต่ละรอบของการประมวลผล อินพุต Li-1 และ Ri-1 จะได้มาจากผลของการประมวลผลก่อนหน้า และคีย์ย่อย Ki ก็จะได้มาจากคีย์ K ซึ่งโดยทั่วไปแล้ว คีย์ย่อยที่จะใช้ในแต่ละรอบของกรประมวลผลจะต้องไม่ซ้ำกัน


ในแต่ละรอบของการประมวลผลจะประกอบด้วยการใช้ Round Function F กระทำกับข้อมูล R และนำผลลัพธ์ทีได้ไป XOR กับข้อมูล L โดย Round Function ที่ใช้จะต้องเป็นฟังก์ชันเดียวกันทั้งหมด แต่เปลี่ยนคีย์ไปเรื่อย ๆ เท่านั้น ซึ่งโดยทั่วไปแล้ว ความซับซ้อน หรือ ความยากในการแกะรหัส จะขึ้นอยู่กับ การออกแบบในส่วนต่าง ๆ โดยมีข้อพิจารณาในการออกแบบอัลกอริทึมในแต่ละส่วนดังนี้

ขนาดของบล็อกข้อมูล บล็อกข้อมูลที่มีขนาดใหญ่ จะมีความปลอดภัยมากขึ้น แต่จะทำให้ความเร็วในการเข้าและถอดรหัสลดลงด้วย ปกติจะถือว่าบล็อกที่มีขนาด 64 บิต ถือว่ามีความเหมาะสม
ขนาดของคีย์ ขนาดคีย์ที่มีขนาดใหญ่ จะมีความปลอดภัยมากขึ้น แต่จะทำให้ความเร็วในการเข้าและถอดรหัสลดลงด้วย ปัจจุบันในอัลกอริทึมสมัยใหม่จะถือว่าคีย์ที่มีความยาว 128–256 บิต ถือว่ามีความปลอดภัยเพียงพอ
จำนวนครั้งของการประมวลผล ยิ่งทำมากรอบจะยิ่งถอดรหัสได้ยากขึ้น ปกติจะถือว่าประมาณ 16 รอบ มีความเหมาะสม
อัลกอริทึมที่ใช้ในการสร้างคีย์ย่อย ยิ่งอัลกอริทึมซับซ้อนจะยิ่งทำให้การแกะรหัสยากขึ้น
ฟังก์ชัน Round ยิ่งฟังก์ชันซับซ้อนจะยิ่งทำให้การแกะรหัสยากขึ้น
สำหรับการถอดรหัสแล้ว จะมีกระบวนการเดียวกับการเข้ารหัส แต่จะใช้คีย์ย่อยย้อนกลับ

อัลกอริทึมเข้ารหัสลับแบบ Secret Key มีอะไรบ้าง

ในการเข้ารหัสแบบ Block Cipher นั้น มีอัลกอริทึมอยู่หลายตัวที่มีการออกแบบและใช้งานในปัจจุบัน โดยอัลกอริทึมที่มีความสำคัญ และใช้งานมากที่สุด คือ DES (Data Encryption Standard) และ 3DES (Triple Data Encryption Standard) ซึ่งถือว่าเป็นรากฐานของระบบเข้ารหัสที่ใช้ในปัจจุบัน อย่างไรก็ตาม เนื่องจาก DES และ 3DES ได้มีการใช้งานมาระยะหนึ่งแล้ว และเริ่มจะมีความปลอดภัยน้อยลง จึงได้มีความพยายามออกแบบอัลกอริทึมในการเข้ารหัสใหม่ในชื่อ AES (Advanced Encryption Stabdard) ซึ่งจะกล่าวถึงในที่นี้ด้วย

Data Encryption Standard
DES เป็นอัลกอริทึมแบบ Block Cipher ที่มีการใช้งานมากที่สุด โดย DES เป็นมาตรฐานของ NIST (National Institute of Standard and Technology) โดยประกาศใช้งานเมื่อปี 1977 โดยใช้ชื่อรหัสว่า FIPS PUB 64 (Federal Information Processing Standard 46) และในปี 1994 ได้ปรับปรุงมาตรฐานเป็น FIPS PUB 46–2 โดยอัลกอริทึมที่ใช้รู้จักกันในชื่อของ DEA (Data Encryption Algorithm)


อัลกอริทึมการทำงานของ DES แสดงไว้ในรูปข้างบน โดย DES จะใช้บล็อกข้อมูลขนาด 64 บิต และใช้คีย์ขนาด 56 บิต โดยหากข้อมูลมีขนาดใหญ่กว่า 64 บิต ก็จะแบ่งออกเป็นบล็อกละ 64 บิต จากรูปทางด้านฝั่งซ้าย จะแสดงการนำบล็อกข้อมูลมากระทำ โดยแบ่งออกเป็น 3 ช่วงย่อย โดยช่วงแรกจะเป็นการนำเอาบล็อกข้อมูลมาผ่านการสลับบิตขั้นต้น (Initail Permutation) ซึ่งจะสลับบิตทั้งหมดเสียใหม่ จากนั้นจะเข้าสู่ช่วงที่ 2 โดยประกอบด้วยการทำฟังก์ชัน Round จำนวน 16 ครั้ง และช่วงสุดท้าย จะประกอบด้วยการสลับกลุ่มข้อมูล 32 บิตซ้ายและขวา จากนั้นก็จะนำมาผ่านการสลับบิตย้อนกลับ (Reverse Initial Permutaion) อีกครั้ง ก็จะได้ออกมาเป็น Ciphertext ที่มีความยาวเท่ากับ Plaintext ที่เข้าไป คือ 64 บิต


แสดงตารางการสลับบิตขั้นต้น
สำหรับทางด้านฝั่งขวา จะแสดงกระบวนการในการสร้างคีย์ย่อย โดยเริ่มต้นคีย์หลักที่มีความยาว 56 บิต จะผ่านฟังก์ชันการสลับบิต 1 จากนั้นจะนำผลลัพธ์ที่ได้ไปใช้ในการสร้างคีย์ย่อยจำนวน 16 คีย์ โดยในแต่ละครั้งของการสร้างคีย์ย่อยนั้น จะมีการทำ Circular Shift และนำผลลัพธ์ที่ได้ไปผ่านฟังก์ชันการสลับบิต 2 จากทั้งหมดที่ได้กล่าวมา คงจะเห็นภาพรวมของการเข้ารหัสแบบ DES สำหรับรายละเอียดของการเข้ารหัสในแต่ละรอบนั้น ได้แสดงไว้ในรูปด้านล่าง


การเข้ารหัสในแต่ละรอบของอัลกอริทึม DES
จากรูป จะเห็นได้ว่าในแต่ละรอบการทำงานนั้น จะมีการแบ่งข้อมูลขนาด 64 บิตที่ได้จากผลของการทำงานในรอบก่อนหน้าออกเป็นข้อมูล 32 บิต 2 ชุด โดยจะเรียกว่าชุด L และชุด R โดยสามารถเขียนเป็นสมการของการสร้างข้อมูลชุด L และ R ในรอบที่ I ได้ดังนี้


สำหรับฟังก์ชัน F นั้นเป็นฟังก์ชันที่มีทั้งการทำงานในแบบที่มีการสลับบิต (Permutaion) และการแทนที่ (Substution) โดยผ่านทาง E Table และ S-BOX โดย E Table จะเป็นการสลับบิตในแบบที่มีการขยายความยาวด้วย โดยตาราง E สามารถดูได้จากตารางข้างล่างนี้ จากนั้นจะนำผลลัพธ์ที่ขยายเป็น 48 บิตไป XOR กับคีย์ย่อย จากนั้นเมื่อผ่าน S-BOX แล้วจะถูกลดความยาวลงเหลือ 32 บิตเท่าเดิม และนำไปผ่านฟังก์ชันสลับบิต P อีกครั้ง


สำหรับกระบวนการในการถอดรหัส DES ก็จะมีลักษณะเช่นเดียวกับการเข้ารหัสทุกประการ ซึ่งถือเป็นสิ่งสำคัญ คือเป็นอัลกอริทึมเดียวกัน เพียงแต่เปลี่ยนอินพุตเป็น Ciphertext และฟังก์ชันที่สร้างคีย์ จะต้องสร้างออกมาในลำดับที่ย้อนกลับกันเท่านั้น ทั้งนี้เนื่องจากการเข้ารหัสนี้โดยภาพรวมแล้ว จะเป็นการสลับบิตข้อมูลไปมา โดยผ่านทางตารางที่มีรูปแบบตายตัว ซึ่งเป็นกระบวนการที่ย้อนกลับได้ และผ่านฟังก์ชัน XOR ซึ่งเป็นกระบวนการที่ย้อนกลับได้เช่นเดียวกัน ดังนั้นการออกแบบอัลกอริทึมที่เหมาะสม ก็จะทำให้การถอดรหัสทำได้ง่าย (หากทราบคีย์) แต่การแกะจะทำได้ยาก เพราะข้อมูลมีการเปลี่ยนไปมาก

ความแข็งแกร่งของ DES
ในการพิจารณาถึงความแข็งแกร่งของ DES นั้น เราจะพิจารณากันใน 2 ด้าน คือ ด้านของตัวอัลกอริทึมเอง และด้านความยาวของคีย์ สำหรับเรื่องของอัลกอริทึมนั้น หลังจากที่ DES ได้ประกาศใช้ออกมา ก็ได้มีผู้พยายามจะหาจุดอ่อนของ DES อยู่มาก จนอาจกล่าวได้ว่า DES เป็นอัลกอริทึมการเข้ารหัสที่มีผู้ศึกษาค้นคว้ามากที่สุดในโลกก็ว่าได้ แต่จนถึงบัดนี้ก็ยังไม่มีผู้ที่ค้นหาจุดอ่อนของ DES ได้เลย ดังนั้นจึงอาจถือได้ว่ายังเป็นอัลกอริทึมที่ยังไม่มีจุดอ่อน

แต่จุดที่น่าสนใจมากกว่า คือ ความยาว 56 บิตของ DES เพียงพอหรือไม่ เนื่องจาก DES เกิดมาในช่วงที่คอมพิวเตอร์ยังไม่มีความเร็วมากนัก แต่หลังจากนั้นก็ได้มีการพัฒนาความสามารถของคอมพิวเตอร์อย่างรวดเร็ว ทำให้ความเป็นไปได้ในการแกะคีย์ขนาด 56 บิตมีความเป็นไปได้มากขึ้น ในปี 1998 มีเหตุการณ์หนึ่งที่ต้องบันทึกไว้ และถือได้ว่าเป็นเหตุการณ์ที่ทำให้อัลกอริทึม DES ถึงจุดจบอย่างเป็นทางการ เหตุการณ์ที่ว่านั้นเกิดจากหน่วยงานหนึ่งที่ชื่อว่า EFF (Electronics Frontier Foundation) ได้สร้างเครื่องคอมพิวเตอร์ขึ้นมาเครื่องหนึ่งเพื่อทำหน้าที่ในการแกะรหัส DES โดยเฉพาะ โดยใช้ชื่อว่า “DES Cracker” โดยใช้เงินทุนไม่ถึง 250,000 เหรียญ โดยสามารถแกะคีย์ขนาด 56 บิตได้ในเวลา 3 วันเท่านั้น ยิ่งไปกว่านั้น EFF ได้เผยแพร่ผลงานของตนเองสู่สาธารณะ ทำให้ทุกคนสามารถสร้างได้

อย่างไรก็ตาม ในการแกะรหัสนั้นจะเริ่มจากการใส่ Ciphertext เข้าไปจากนั้นก็ใส่ Key เข้าไปทีละตัวอย่าง ซึ่งจะทำให้เกิดเป็น Plaintext ออกมา แต่ Plaintext จะเป็น Plaintext ที่ถูกต้อง คือ ตรงกับต้นฉบับก็ต่อเมื่อ Key ที่ใส่เข้าไปเป็นคีย์ที่ถูกต้อง คราวนี้จะรู้ได้อย่างไรว่า Plaintext ที่ได้เป็น Plaintext ที่ถูกต้อง ซึ่งหมายถึง Key ที่ถูกต้องด้วย นั่นก็คือ การพิจารณาดูเนื้อความ เช่น หากต้นฉบับเป็นภาษาอังกฤษ Plaintext ที่ถูกต้องก็ต้องเป็นภาษาอังกฤษด้วย ดังนั้นก็จะใช้วิธีดูไปเรื่อย ๆ ว่าหากผลลัพธ์ที่แกะได้ออกมาเป็นภาษาที่อ่านได้ ก็หมายความว่า Key ที่ใช้เป็น Key ที่ถูกต้องแล้ว แต่หากไฟล์ที่เข้ารหัสเป็นไฟล์แบบอื่น เช่น ไฟล์ที่มีตัวเลขอย่างเดียว หรือ ไฟล์ที่ผ่านการบีบข้อมูลมาแล้ว ก็จะยิ่งหา Key ที่ถูกต้องได้ยากยิ่งขึ้น หรืออาจทำไม่ได้เลยก็ได้


กราฟแสดงระยะเวลาที่ใช้ในการเบรคเทียบกับความยาวคีย์ (สมมติให้เครื่องคอมพิวเตอร์มีความสามารถในการถอดรหัส 1 ล้านครั้งต่อวินาที)
Triple DES
อัลกอริทึม 3DES ได้รับการเสนอครั้งแรกโดย Tuchman โดยเริ่มแรกเป็นมาตรฐานของ ANSI หมายเลข X9.17 ในปี 1985 จากนั้น NIST ได้นำมาเป็นส่วนหนึ่งของมาตรฐานหมายเลข FIPS PUB 46–3 ในปี 1999 โดย 3DES จะใช้อัลกอริทึมเดียวกับ DES แต่จะใช้คีย์จำนวน 3 คีย์และทำ DES จำนวน 3 ครั้ง ดังรูป


ดังนั้นคีย์ทั้งหมดจะมีความยาวเท่ากับ 168 บิต อย่างไรก็ตาม FIPS PUB 46–3 ยอมให้ใช้คีย์เพียง 2 คีย์ คือ กำหนดให้คีย์ K1 เท่ากับ K3 ได้ ดังนั้นความยาวคีย์จะเหลือเท่ากับ 112 บิต กล่าวโดยสรุป 3DES เป็นการปรับปรุง DES ให้มีความปลอดภัยมากขึ้น สามารถใช้งานร่วมกับ DES ได้ อย่างไรก็ตามการทำ DES จำนวน 3 ครั้ง ถือได้ว่ามีความปลอดภัยมากพอสำหรับช่วงเวลาที่จะมีการพัฒนาอัลกอริทึมในการเข้ารหัสตัวต่อไป นั่นก็คือ AES

Advanced Encryption Standard
แม้ว่า 3DES เป็นอัลกอริทึมที่มีความปลอดภัย เพราะใช้คีย์ที่มีความยาวถึง 168 บิต ทำให้ยากต่อการแกะรหัส และใช้ อัลกอริทึมเดียวกับ DES ซึ่งรู้จักกันทั่วไป ดังนั้นจึงถือว่ามีความปลอดภัยมากที่สุดในปัจจุบัน ซึ่งจนถึงปัจจุบันก็ยังไม่มีใครแกะ3DES ได้สำเร็จ ดังนั้นหากจะพิจารณาในด้านความปลอดภัยเพียงอย่างเดียว 3DES ถือเป็นตัวเลือกที่เหมาะสม แต่เนื่องจากรูปแบบอัลกอริทึมเป็นอัลกอริทึมที่ออกแบบมาให้ง่ายต่อการสร้างด้วยฮาร์ดแวร์มากกว่าซอฟต์แวร์ ประกอบกับการทำ DES ถึง 3 ครั้ง ทำให้การเข้ารหัสข้อมูลจำนวนมาก ๆ มีความล่าช้า อีกประการหนึ่งคือ บล็อกข้อมูลขนาด 64 บิต ถือว่าเล็กเกินไปหน่อยในปัจจุบัน

ด้วยเหตุดังกล่าวในระยะยาว จึงมีความต้องการอัลกอริทึมใหม่ ที่มีความเหมาะสมมากขึ้น โดยในปี 2540 ได้มีการประกาศให้นักพัฒนาเสนออัลกอริทึมเข้ามาให้ NIST พิจารณา โดยได้ตั้งชื่ออัลกอริทึมใหม่นี้ว่า AES ซึ่งมีข้อกำหนดเบื้องต้นว่า จะต้องมีความปลอดภัยอย่างน้อยเท่ากับ 3DES มีการใช้บล็อกข้อมูลขนาด 128 บิต และสามารถใช้ความยาวคีย์ได้ตั้งแต่ 128 บิต 192 บิต และ 256 บิต โดยมีความเร็วในการทำงานที่ดี และใช้หน่วยความจำในการทำงานน้อย โดยในรอบแรกมีผู้เสนอเข้ามา 15 อัลกอริทึม และได้คัดเหลือ 5 อัลกอริทึมในรอบที่ 2 คือ MARS, RC6™, Rijndael, Serpent,Twofish และในเดือนตุลาคม 2543 ทาง NIST ก็ได้ประกาศผู้ชนะ ออกมา

อัลกอริทึม AES ที่ได้รับการตัดสินให้ชนะเลิศนี้ สร้างขึ้นโดย Joan Daemen และ Vincent Rijmen ซึ่งเป็นนักวิจัยชาวเบลเยี่ยม โดยอัลกอริทึมนี้เดิมทีใช้ชื่อว่า Rijndael (Rijmen & Daemen) อัลกอริทึมนี้จะยังคงเป็นแบบ Block Cipher โดยใช้บล็อกข้อมูลขนาด 128 บิต 196 บิต และ 256 บิต โดยสามารถใช้คีย์ได้ยาวถึง 128 บิต 196 บิต และ 256 บิต โดยอัลกอริทึมนี้ได้รับการออกแบบให้มีการทำงานที่เหมาะสมกับโพรเซสเซอร์รุ่นใหม่ ๆ และสามารถใช้งานกับ Smart Card ได้ เพราะใช้หน่วยความจำน้อย

อัลกอริทึม Rijndael จะใช้ฟังก์ชัน Round ที่สามารถเลือกได้ว่าจะทำ 10,12 หรือ 14 ครั้ง โดยมีการทำงานอยู่ 4 การทำงานย่อย คือ Byte Sub ก็คือการใช้ S-Boxes ในการสลับข้อมูลระหว่าง 2 บล็อก ShiftRow คือการสลับข้อมูลระหว่างแถว Mix Column คือการ Shift ข้อมูลในแต่ละ Column และสุดท้ายคือ Key Addition คือการนำมาบวกกับคีย์ ซึ่งการทำงานทั้งหมด เป็นการทำงานที่ง่าย มีจำนวนครั้งของการทำงานน้อย ทำงานได้เร็ว และใช้หน่วยความจำน้อย

การเข้ารหัสแบบ Secret Key อื่นๆ
ที่ผ่านมาเราได้ศึกษาอัลกอริทึมในการเข้ารหัสของ NIST เพราะเป็นองค์กรหลักที่ทำหน้าที่ด้านนี้ แต่นอกจาก NIST แล้วยังมีผู้อื่นที่สร้างอัลกอริทึมในการเข้ารหัสในแบบ Block Cipher ขึ้นมาเช่นกัน โดยลักษณะของอัลกอริทึมส่วนใหญ่ จะยังคงเป็นแบบที่ใช้โครงสร้างของ Feistel ทั้งนี้เนื่องจากโครงสร้างนี้เป็นโครงสร้างที่รู้จักกันดีอยู่แล้ว ทำให้เมื่อต้องการวิเคราะห์การเข้ารหัส สามารถทำได้ง่าย เพราะหากมีการใช้โครงสร้างที่ต่างไปโดยสิ้นเชิง อาจมีจุดอ่อนของโครงสร้าง ซึ่งอาจไปปรากฏในภายหลังได้

IDEA

อัลกอริทึม IDEA (International Data Encryption Algorithm) เป็น Symmetric Block Cipher พัฒนาโดย Xuejia Lai และ James Massey แห่ง Swiss Federal Institute of Technology ในปี 1991 อัลกอริทึม IDEA ใช้คีย์ขนาด 128 บิต ซึ่งจะต่างจาก DES ทั้งในส่วนของฟังก์ชัน Round และส่วนของฟังก์ชันที่ใช้ในการสร้างคีย์ย่อย

ในส่วนของฟังก์ชัน Round ใน IDEA จะไม่ใช้ S-Boxes โดยจะใช้ฟังก์ชันคณิตศาสตร์ XOR การบวก และการคูณประกอบกัน ซึ่งเป็นผลให้ฟังก์ชันดังกล่าว มีความซับซ้อนมาก ทำให้ยากต่อการวิเคราะห์ ในส่วนของคีย์ย่อยจะใช้ Circular Shift ในการสร้างคีย์ย่อย โดยจะมีการประมวลผลจำนวน 8 ครั้งด้วยกัน และเนื่องจาก IDEA เป็นอัลกอริทึมแรก ๆ ที่ใช้คีย์ขนาด 128 บิต เพื่อใช้แทน DES จึงไม่ได้รับความสนใจมากนัก และได้รับการต่อต้านจากนักวิเคราะห์ค่อนข้างมาก IDEA มีการใช้งานใน PGP (เป็นตัวเลือกหนึ่ง) และมีการใช้ในผลิตภัณฑ์ต่าง ๆ หลายตัว

Blowfish

อัลกอริทึม Blowfish พัฒนาโดย Bruce Schneier ในปี 1993 โดยเขาเป็นเป็นที่ปรึกษาอิสระและผู้เชี่ยวชาญด้านการเข้ารหัส ซึ่ง Blowfish ได้รับการต้อนรับอย่างดี ในฐานะตัวเลือกหนึ่งของ DES อัลกอริทึม Blowfish ได้รับการออกแบบมาเพื่อให้สร้างได้ง่าย และมีความเร็วในการทำงานสูง เป็นอัลกอริทึมที่ใช้พื้นที่ในการทำงานน้อยมาก เพียง 5K ก็สามารถทำงานได้ สิ่งที่น่าสนใจใน Blowfish คือ การใช้คีย์ที่มีการเปลี่ยนค่าความยาวได้ โดยยาวได้มากถึง 448 บิต แต่ในทางปฏิบัติมักใช้กันที่ 128 บิตก็ถือว่าเพียงพอแล้ว ในอัลกอริทึมนี้มีการวนรอบทั้งหมด 16 ครั้ง

อัลกอริทึม Blowfish มีการใช้ S-Boxes และ XOR เช่นเดียวกับ DES แต่ยังมีการใช้การบวกร่วมด้วย แต่สิ่งที่ต่างจาก DES คือ ใน DES จะใช้ S-Boxes แบบความยาวคงที่ แต่ใน Blowfish จะสามารถเปลี่ยนค่าความยาวได้ สำหรับส่วนของการสร้างคีย์ย่อยนั้น Blowfish มีการนำเอาอัลกอริทึม Blowfish เองมาใช้ในการสร้างคีย์ย่อยและ S-Boxes ด้วย โดยจะต้องมีการวนทั้งหมด 521 รอบในการทำงานเพื่อสร้างคีย์ย่อยและ S-Boxes และนั่นทำให้ Blowfish ไม่เหมาะที่จะใช้กับงานที่จะต้องมีการเปลี่ยนค่า Secret Key บ่อย ๆ

อัลกอริทึม Blowfish เป็นหนึ่งในอัลกอริทึมการเข้ารหัสที่มีความปลอดภัยสูง เนื่องจากการสร้างส่วนของคีย์ย่อย และ S-Boxes สร้างขึ้นมาจากอัลกอริทึม Blowfish เอง ซึ่งทำให้การแกะรหัสจะทำได้ยากมาก ปัจจุบันมีการใช้งานในผลิตภัณฑ์บางตัว

RC5

อัลกอริทึม RC5 พัฒนาขึ้นมาโดย Ron Rivest แห่ง RSA ซึ่งเป็นหนึ่งในผู้ร่วมค้นคิดอัลกอริทึม RSA อันเลื่องชื่อ (เป็นตัว R ใน RSA) RC5 พัฒนาขึ้นมาในปี 1994 โดยได้รับประกาศเป็นมาตรฐานใน RFC 2040 โดยมีลักษณะเด่นของการออกแบบดังนี้

มีความเหมาะสมต่อการสร้างทั้งทางด้านฮาร์ดแวร์และซอฟต์แวร์ เพราะใช้เพียงการทำงานพื้นฐานเท่านั้น
มีความเร็วสูง โดย RC5 มีการทำงานเป็น Word Oriented และมีอัลกอริทึมที่ง่าย
สามารถปรับปรุงในเข้ากับโพรเซสเซอร์ที่มีขนาด Word ความยาวต่าง ๆ เพราะ RC5 สามารถปรับความยาวได้
สามารถปรับจำนวนรอบการทำงานได้
สามารถใช้คีย์ที่มีความยาวต่าง ๆ ได้
มีโครงสร้างที่ง่าย ทำให้การวิเคราะห์หาจุดอ่อนสามารถทำได้ง่าย
ต้องการหน่วยความจำในการทำงานน้อย
มีความปลอดภัยสูง หากมีการกำหนดค่าการทำงานที่เพียงพอ
RC5 มีการใช้งานในผลิตภัณฑ์ของ RSA Data Security, Inc.

CAST-128

อัลกอริทึม CAST ได้รับการพัฒนาขึ้นโดย Carlisle Adams และ Stafford Tavares แห่ง Entrust Techonology ในปี 1997 โดยอัลกอริทึมนี้ เป็นส่วนหนึ่งของ CAST Project โดยประกาศเป็นมาตรฐานใน RFC 2144 โดยมีขนาดของคีย์ตั้งแต่ 40 จนถึง 128 บิต โดยเพิ่มทีละ 8 บิต อัลกอริทึม CAST เป็นผลจากการวิจัยและพัฒนาอย่างยาวนาน และได้รับการวิเคราะห์อย่างกว้างขวางก่อนนำมาใช้งาน โดยมีการใช้งานในหลายผลิตภัณฑ์ ซึ่งรวมทั้ง PGP ด้วย

อัลกอริทึม CAST ในส่วนของการสร้างคีย์ย่อย มีการใช้ S-Boxes ที่มีความยาวคงที่ แต่มีความยาวมากกว่า DES โดยใช้ฟังก์ชันแบบ Non-Linear ทำให้การแกะรหัสทำได้ยาก นอกจากนั้นในส่วนของฟังก์ชัน Round ก็ต่างจากอัลกอริทึมอื่นด้วย เพราะใน CAST ในแต่ละรอบของการทำงาน จะใช้ฟังก์ชัน Round ที่แตกต่างกันไป ซึ่งยิ่งทำให้การแกะสามารถทำได้ยากมาก

Cipher Block Modes of Operation
ในการเข้ารหัสแบบ Symmetric Block Cipher นั้น จะมีการประมวลผลข้อมูลเป็นชุด เช่น ใน DES และ 3DES นั้นจะประมวลผลข้อมูลครั้งละ 64 บิต ดังนั้นในกรณีที่ข้อมูลมีขนาดยาวมากกว่านั้น ก็มีความจำเป็นต้องแบ่งข้อมูลออกเป็นชุด ๆ แล้วประมวลผลทีละชุดไปเรื่อย ๆ จนหมดข้อมูล (ในกรณีที่ข้อมูลชุดสุดท้ายเหลือไม่ถึง 64 บิต ก็จะมีการเติมให้ครบ 64 บิต) ในการประมวลผลข้อมูลเป็นชุด ๆ นี้ การทำงานในแบบที่ง่ายที่สุด จะมีชื่อว่า Electronic Codebook หรือ ECB ซึ่งหลักการทำงานก็คือ จะแบ่งข้อมูลออกเป็นบล็อกละ 64 บิต โดยในการเข้ารหัสข้อมูลแต่ละชุด จะใช้คีย์เดียวกันทั้งหมด

การทำงานในแบบ ECB นี้ แม้ว่าจะเป็นการทำงานที่ง่าย แต่จะมีข้อเสีย คือ ในกรณีที่บล็อกข้อมูล 64 บิตเป็นข้อมูลเดียวกัน จะทำให้เกิดเป็น Ciphertext ที่มีลักษณะเหมือนกัน ดังนั้นกรณีที่ข้อมูลมีลักษณะเป็นโครงสร้างมาก ๆ เช่น ข้อมูลในลักษณะที่เป็น Record หรือข้อมูลที่มีลักษณะซ้ำกันบ่อย ๆ การทำงานในแบบ ECB อาจไม่ปลอดภัยเพียงพอ ดังนั้นในข้อมูลลักษณะดังกล่าว จึงควรใช้โหมดการทำงานอื่น

Cipher Block Chaining Mode

การทำงานในแบบ Cipher Block Chaining หรือ CBC แสดงในรูปด้านล่าง โดยอินพุตที่จะป้อนเข้าสู่อัลกอริทึมการเข้ารหัสนั้น จะเกิดจากผลลัพธ์ของการทำ XOR ระหว่าง Plaintext Block ปัจจุบันกับ Ciphertext Block จากการทำงานครั้งก่อนหน้า โดยใช้คีย์เดียวกัน ในทุกการเข้ารหัส ซึ่งจะเป็นผลให้อินพุตถูกเปลี่ยนก่อนที่จะเข้าสู่กระบวนการเข้ารหัส โดยการเปลี่ยนนี้จะเกิดขึ้นในลักษณะของลูกโซ่ไปเรื่อย ๆ ซึ่งทำให้ผลลัพธ์ของการเข้ารหัสไม่มีส่วนสัมพันธ์โดยตรงกับข้อมูลก่อนเข้ารหัส ทำให้มีความปลอดภัยมากขึ้น


สำหรับการถอดรหัส ก็จะใช้กระบวนการที่กลับกันดังแสดงในรูป 2.7b สำหรับ IV ที่แสดงในภาพนั้น หมายถึง Initialize Vector ซึ่งเป็นชุดข้อมูลที่จะใช้เฉพาะการ XOR กับข้อมูลในบล็อกแรกเท่านั้น โดยข้อมูล IV นี้จะต้องตรงกันทั้งผู้รับและผู้ส่ง เพราะในการถอดรหัสข้อมูล จำเป็นจะต้องใช้ IV มา XOR กับผลลัพธ์ของการถอดรหัส เพื่อให้ได้ข้อมูลเดิมกลับมา ดังนั้นในการทำงานจริงข้อมูล IV อาจเป็นข้อมูลที่ผู้ส่งกำหนดขึ้นเสมือนกับเป็นคีย์อย่างหนึ่ง หรืออาจเป็นข้อมูลที่ผู้ส่งสร้างขึ้นมาจากการสุ่ม จากนั้นก็ส่งให้ฝั่งรับโดยใช้วิธี ECB ในครั้งหนึ่งก่อน จากนั้นจึงค่อยใช้ IV ในการทำงานในโหมด CBC ต่อไป สำหรับข้อมูล IV นี้ควรจะมีการเปลี่ยนแปลงทุกครั้งที่มีการส่งข้อมูล 1 ชุด เพราะหากฝ่ายตรงข้ามได้ข้อมูล IV นี้ไปได้ ก็จะสามารถทำกระบวนการถอดรหัส CBC ได้เช่นเดียวกัน

Cipher Feedback Mode

สำหรับการทำงานในแบบ CFB นี้ จะมีการทำงานในรูปแบบของ Streme Cipher โดยหากต้องการให้ทำงานในแบบ Byte Oriented จะเลือก j=8 ซึ่งเมื่อมีข้อมูลเข้ามา 1 ไบต์ จะสามารถประมวลผล และสามารถส่งข้อมูลที่เข้ารหัสไปได้ในทันที แต่การทำงานในโหมดนี้ จะมีการทำงานล่าช้า เพราะการทำงานครั้งละ 64 บิต แต่มีการนำไปใช้งานเพียง 8 บิตเท่านั้น
