
# MIST4610GroupProject1
# Team Name
Sp25_21479_Group2
# Team Members 
1. Buckner, Alexa [@amb21398](https://github.com/amb21398/MIST4610-GP2/blob/9b648b16ef476529aad6283655399297cd5f3377/README.md)
2. Eloore, Neha [@neloore](https://github.com/neloore/MIST-4610-Group-Project.git)
3. Nguyen, Hung @[triumviratesys](https://github.com/triumviratesys/MIST4610-GP1)
4. Spraker, Dabney @[dps24510](https://github.com/dps24510/Dabney-Spraker-Group-Project-1)
5. Dorrien, Leah [@leahdorrien2](https://github.com/leahdorrien2/MIST4610GroupProject1/blob/main/README.md)
# Scenario Description
The Hospital Management system was made as a digital system to efficiently manage information regarding the employees working in the hospital and the patients entering and leaving. In a modern hospital setting, managing a large volume of patients, staff, billing, and medical processes requires an integrated system to meet medical regulations and optimize resources. Through this system the hospital is able to manage patient care, staff scheduling, medical records, prescriptions, and department operations within a hospital environment. This system serves as a central database for tracking appointments, patient history, prescriptions, staff shifts, and billing information, ensuring smooth operations and effective healthcare delivery.
# Data Model Explanation

<img width="602" alt="image" src="https://github.com/user-attachments/assets/ee616e47-91e5-462e-baac-93bc3480af98" />

   Our model is based on the structure of a hypothetical hospital system. The Departments entity represents different departments within the hospital, such as Cardiology, Emergency, or Pediatrics. Each department can have multiple staff members and doctors, reflected in one to many, non-identifying relationships between Departments and Staff and Departments and Doctors. These relationships are non-identifying because staffID and doctorID remain the same even if a staff member or doctor changes departments.

   We chose to have separate Staff and Doctor entities because not all employees should be classified as doctors. Only doctors are associated with entities such as Appointments, MedicalRecords, and Prescriptions.

   The Staff entity represents hospital employees, including nurses, administrative workers, and technicians, with job titles and department assignments. Staff schedules are captured in the StaffSchedule entity, linking staff members to shifts recorded in the Shifts entity, which includes start times, end times, and shift types. The relationship between Staff and StaffSchedule is one to many and identifying. The relationship between StaffSchedule and Shifts is also a one to many, identifying relationship. This is because each schedule record depends on both a specific staff member and a specific shift. Each staff member can appear multiple times on the schedule (one to many), and each schedule entry must be linked to exactly one staff member and one shift (identifying). Each of the schedule entities also include a shift status to show whether a shift is completed, cancelled, or active.

   Similarly, the Doctors entity contains doctor names, specializations, and department assignments. Doctor shift schedules are managed through the DoctorSchedule entity, which functions identically to StaffSchedule, forming one to many, identifying relationships with both Doctors and Shifts.
The Patients entity stores patient demographics, contact information, medical details (such as blood type and allergies), and links to their pharmacy and insurance information. 
There is a one to many, non-identifying relationship between Patients and Appointments, since each patient can have multiple appointments, but each appointment has its own identity and simply references the patient. The relationship between Doctors and Appointments is also a one to many, non-identifying relationship, as each doctor may have multiple appointments, but each appointment only points to one doctor.
   
   The same applies to EmergencyContacts, where patients can have many emergency contacts, but said records and contacts can exist independently of the patient. Conversely, pharmacies and insurance companies also have a 1-M relationship with Patients, but they are referenced as foreign keys on the Patients entity. These firms can accommodate many patients, but each patient only needs to go to one pharmacy and be on one insurance plan. 
Patient medical history is stored in the MedicalRecords entity, recording diagnoses, treatments, dates, and links to the patient and doctor responsible. This is a one to many, identifying relationship between Patients and MedicalRecords because each medical record is uniquely tied to a patient and cannot exist without them. The relationship between Doctors and MedicalRecords is one to many, non-identifying, since each doctor may have multiple records associated with them, but the records are independent entities with their own primary keys. As such, the MedicalRecords entity contains patientID and doctorID as foreign keys.
   
   The Appointments entity records reasons, dates, statuses, and links to both the doctor and patient. Billing for these appointments is tracked in the Billings entity. There is a one to many, non-identifying relationship between Appointments and Billings, as one appointment may have multiple billing records (for partial payments or adjustments), but each billing entry exists independently and only references one appointment.
Prescriptions are recorded in the Prescriptions entity, with details on medication name, dosage, duration, prescribing doctor, patient, and prescription date. There is a one to many, non-identifying relationship between Patients and Prescriptions and Doctors and Prescriptions. A patient can have multiple prescriptions, and each prescription is issued by one doctor, but each prescription exists independently with its own unique ID.
The Pharmacies entity stores pharmacy details. There is a one to many, non-identifying relationship between Pharmacies and Patients, as each pharmacy can serve multiple patients, but each patient is linked to only one pharmacy. The pharmacy exists independently of any patient.
   
   The InsurancePolicies entity holds policy numbers and company details. It has a one to many, non-identifying relationship with Patients, where one insurance policy may cover multiple patients, but the policy exists independently of any single patient.
   
   Lastly, the EmergencyContacts entity allows each patient to have multiple emergency contacts, with phone numbers, addresses, and relation types recorded. This is a one to many, non-identifying relationship, as emergency contacts can exist as independent entries linked to only one patient.

# Data Dictionary
<img width="431" alt="image" src="https://github.com/user-attachments/assets/c577dd8a-a663-45f8-aaf9-05ce2f25f982" />

<img width="422" alt="image" src="https://github.com/user-attachments/assets/ea0ceb2e-861c-497c-859a-7eed8c483859" />

<img width="421" alt="image" src="https://github.com/user-attachments/assets/af2a6f21-2106-4852-a086-87dc294e2553" />

<img width="417" alt="image" src="https://github.com/user-attachments/assets/8a2406f7-29a4-41ef-a0b7-2fd1cbac5f0f" />

<img width="416" alt="image" src="https://github.com/user-attachments/assets/8c3ddf93-dbd9-46d5-a176-e30a8c71bd9e" />

<img width="415" alt="image" src="https://github.com/user-attachments/assets/2987054f-1ee4-4227-93d5-0bb522cd84b6" />

<img width="417" alt="image" src="https://github.com/user-attachments/assets/8f0054a1-d76b-457a-961c-8e5480b03817" />

<img width="416" alt="image" src="https://github.com/user-attachments/assets/d35b7872-bba6-4ba1-a566-0c39f85eacbc" />

<img width="417" alt="image" src="https://github.com/user-attachments/assets/bdbf74f4-4a60-4641-be5b-f050af9b57b8" />

<img width="417" alt="image" src="https://github.com/user-attachments/assets/ad20a977-44cb-4da7-b5ee-ee0f1d4c3d6e" />

<img width="416" alt="image" src="https://github.com/user-attachments/assets/c02270ed-32d6-43ac-a973-571013918dfc" />

<img width="413" alt="image" src="https://github.com/user-attachments/assets/f39beebe-f444-4597-a2a3-869fcebe5c91" />

<img width="413" alt="image" src="https://github.com/user-attachments/assets/da188559-bfbb-4c24-85f7-1d5e52229cb8" />

<img width="414" alt="image" src="https://github.com/user-attachments/assets/51313593-9d65-4747-8d13-05d936bc91c1" />

<img width="413" alt="image" src="https://github.com/user-attachments/assets/9504b846-1fa5-4e1d-b966-eef54d5b00f8" />

<img width="414" alt="image" src="https://github.com/user-attachments/assets/1721af4a-2b24-4ecd-942e-9e38bd742be4" />

<img width="421" alt="image" src="https://github.com/user-attachments/assets/74062d94-9a07-461e-a9d0-22332271b6bb" />













# Queries

<img width="466" alt="image" src="https://github.com/user-attachments/assets/849aa4a9-184c-4385-baac-aa813dd44739" />


1. Query 1 lists the patient’s first name, last name, and their emergency contact’s name if their blood type is O negative. The results are also listed in descending order based on the patient’s last name.

<img width="349" alt="image" src="https://github.com/user-attachments/assets/e765655d-ee3e-4088-bc75-6d1f1897b19e" />
Query 1 allows the hospital management system to see which of their patients has an O negative blood type. O negative is considered the “universal donor” as any individual can receive this blood type. People with O negative blood are often sought out to see if they'd be willing to donate their blood, which could potentially save hundreds of others lives.


2. Query 2 lists the patient's first and last time and their total outstanding billing amount for bills that are pending or overdue. The results are listed in descending order by the total outstanding billing amount.

   <img width="491" alt="image" src="https://github.com/user-attachments/assets/18562218-1d99-43f9-9488-237ef0ebd1c7" />
   
Query 2 allows the staff in charge of billings to oversee how much money they are still waiting to receive from the patients in their care. Including both pending and overdue payments, the system can contact these individuals to check in on their payments and keep track of who they are owed money from.

3. Query 3 lists out the pharmacy’s name and the number of patients at each pharmacy.

<img width="379" alt="image" src="https://github.com/user-attachments/assets/07a45dc2-c191-4ee3-9b4a-c2e283bdf3db" />

Query 3 allows the billing staff to look over all of the different pharmacies that their patients are assigned to. Based on the pharmacy, they can make certain deals with the hospital if enough patients are assigned and receiving medication orders/refills. They can also maintain their business relationships with these suppliers, which will strengthen their business overal

4. Query 4 lists out the patient’s first name, last name, ID, appointment reason, and bill for their appointment if it is greater than the average billing amount in the hospital.


<img width="514" alt="image" src="https://github.com/user-attachments/assets/a19e8f30-add9-4aed-a95c-28bde17eb6ea" />

Query 4 allows the hospital billing staff to see the patient’s name, their ID number, their appointment reason, and the bill for their appointment if it is greater than the average bill amount for the hospital. This gives a general idea for the staff to see which appointments cost more than the typical average of all appointments within the hospital. This also brings forth important information such as which patients are bringing more than the average revenue from appointments, future budgeting plans, and whether or not resources need to be allocated more.


5. Query 5 lists the patients ID, first name, last name, and their phone number if they do not have any allergies, they are not a minor, and they are not taking any medications.


<img width="767" alt="image" src="https://github.com/user-attachments/assets/0cb320a6-a2eb-4562-9b0d-d7f589d7f2c8" />


Query 5 allows the hospital staff who are in charge of keeping data and improving upon the hospital itself to possibly give patients surveys and record their experiences. In order to get the best results while taking the survey, the patient must not have any allergies, must be older than 18, and not currently taking medication. They then can have a list of patients to ask if they’d be willing to take the survey and use their data to better improve the hospital.

6. Query 6 lists the doctors ID, first name, last name, and the amount of overtime hours they have worked. Overtime is considered to be above 40 hours within a working week and they will be paid time and a half.

<img width="526" alt="image" src="https://github.com/user-attachments/assets/7d1e9a04-8c11-4831-ab25-2667a8e017ba" />

Query 6 allows the hospital staff in charge of the doctor’s payroll to see who needs to be compensated properly for any time worked above the normal 40 hours a week. If a doctor has worked more than 40 hours, then they can be paid extra money for any additional hours worked. This makes it a lot easier to see who has worked overtime and who has not.

7. Query 7 lists the names of all of the staff members such as their ID, first name, last name, job title, and department name (not including doctors) who work less than 2 night shifts.

<img width="731" alt="image" src="https://github.com/user-attachments/assets/7a2582c0-f855-4b4f-9699-087d9048640a" />

Query 7 allows any shift supervisors to see which staff members work less than 2 night shifts for a work week. Supervisors can use this to determine if there is anyone in the department that can possibly pick up more night shifts due to them working less than 2.

8. Query 8 lists the patients’ first name, last name, and medication name for each medication of those who are taking more than 1 prescription. Order by the patient’s names.

<img width="647" alt="image" src="https://github.com/user-attachments/assets/063e1aa4-ba39-421c-8a4c-b08297ba3a58" />

Query 8 allows doctors to look through their patients and know which patients are taking more than one medication and the names of those medications. Taking multiple medications at the same time can increase the risk of dangerous side effects occurring, so it is very important for doctors to know what their patients are taking in order to keep their patient safe. It is also helpful in determining if the patient can take more medications based on what they are already taking.


9. Query 9 determines the distribution of insurance companies among insured patients in the hospital

<img width="761" alt="image" src="https://github.com/user-attachments/assets/e843edd0-5c20-4261-bf42-0f3e8178286c" />

Query 9 allows the hospital to understand who their top insurance providers are (in terms of patients insured). With this information, the management staff can better optimize the billing system, know the prominent insurance company among patients, and streamline the insurance process by understanding how the prominent insurance companies work. If the providers are in equal proportion, the query also sorts providers alphabetically.


10. Query 10 lists the patient’s first name, last name, age, and their diagnosis if they are born after 01/01/1997


<img width="439" alt="image" src="https://github.com/user-attachments/assets/24a0dbf0-e385-4e85-99c0-22881b4df0b2" />

Query 10 is useful for the hospital staff to relay important information to doctors on how to treat younger patients that are a part of Generation Z or Alpha. Knowing your patient’s age difference is key in helping understand them and what can be different in their treatment compared to individuals who are Millennials or Generation X. 

# Database Information
Name of the database: ns_Sp25_21479_Group2

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Q1();
