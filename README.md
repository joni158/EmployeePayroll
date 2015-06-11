# EmployeePayroll
This is my first desktop program using wxPython.
NIM   : L200134020
Name  : Joni
Class  : X
Semester  : 04
Lecturer  : Bana Handaga
Account Github  : Bana Handaga https://github.com/joni158

About My Application

1.	Descriptions
a.	This is my first desktop application I make using python programming language.
b.	Softwares that needed are IDLE Python Interpreter (Pyhton v.2.5), WxPython v.2.8 (as GUI Library), Boa Constructor (as IDE), MySQL Server (PHP and Apache in XAMPP), and Connector between Python to MySQL (MySQLdb module).
c.	This application is information system of employee payroll that I have given name “SI(Ar-Risallah).py”  (As main app).
d.	This application is in directory of “InformationSystem_EmployeePayroll”, put this folder in C:\\

2.	To Run This Application
a.	Install IDLE python interpreter and all modules needed above.
b.	Install MySQL Server (PHP and Apache in XAMPP).
c.	Creating database named “penggajian” in MySQL.
d.	Creating tables with this codes :

CREATE TABLE posisikaryawan (
	ID_posisi INTEGER(5) PRIMARY KEY NOT NULL,
	nama_posisi VARCHAR(45) NOT NULL,
	gaji_posisi INTEGER NOT NULL,
	tunjangan_posisi INTEGER,
	lembur_posisi INTEGER);

CREATE TABLE datakaryawan (
	NIK INTEGER PRIMARY KEY NOT NULL,
	nama VARCHAR(45) NOT NULL,
	tempat_lahir VARCHAR(45) NOT NULL,
	tgl_lahir DATE,
	tgl_masuk DATE,
	jenis_kelamin VARCHAR(10),
	alamat VARCHAR(225),
	telepon VARCHAR(15),
	ID_posisiFK INTEGER(5) REFERENCES posisikaryawan(ID_posisi)
	ON DELETE SET NULL ON UPDATE CASCADE);

CREATE TABLE gajikaryawan (
	nota INTEGER(10) PRIMARY KEY NOT NULL,
	total_gaji INTEGER,
	jam INTEGER,
	NIKFK INTEGER REFERENCES datakaryawan(NIK)
	ON DELETE SET NULL ON UPDATE CASCADE,
	ID_posisiFK INTEGER(5) REFERENCES posisikaryawan(ID_posisi)
	ON DELETE SET NULL ON UPDATE CASCADE);

INSERT INTO posisikaryawan (ID_posisi, nama_posisi, gaji_posisi, tunjangan_posisi, lembur_posisi)
VALUES (1301, 'Manager', 7000000, 1000000, 50000);

INSERT INTO posisikaryawan (ID_posisi, nama_posisi, gaji_posisi, tunjangan_posisi, lembur_posisi)
VALUES (1302, 'Sekretaris', 5000000, 500000, 30000);

e.	After creating database, tables, and inserting some records. Just run this application by 2 left clicking on “SI(Ar-Risallah).py”
f.	First frame will displayed Login Frame, just input username = joni and password = 12345
g.	In karyawan frame, we can insert, update, delete, seacrh, and view all employees. There is also some features that I make like auto inputted in gaji pokok, tunjangan posisi, and lembur /jam when I chose in combobox (posisi). Also when I click one of the data in list control, the data will automatically looked in form.
h.	In posisi frame, we can insert, update, delete, seacrh, and view all positions. The feature of this, I think almost same with karyawan frame.
i.	In hitung gaji frame, we want to print out a report of employee payroll. The nota textfield will auto increament. To count a payroll, just input NIK in NIK textfield, then press Enter and the position anf others will automatically inserted except jam textfield because we need to determine by ourself how many hours the employee working overtimes.
j.	In hitung gajii frame, we can count, delete, and print out a report of employee payroll. The addition feature is button of cetak. Just click one of employee in data list control then press cetak. It will display a pop up that the file will be saved with Ms.Excel.
k.	Directory of the Excel file is in C:\Users\Public.
l.	The report will be displayed on the file, then just print out the report using printer.
 
3.	Bug
There are some bugs on my applications :
a.	On auto refresh of frame, for example when I delete or update a data, the views of data list control is not directly change. So we need to back to other frame and go back to the frame again (the data will change). Still confusing how to auto update the frame.

THANK YOU
