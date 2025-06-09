# Database

![image](https://github.com/user-attachments/assets/4813c6ed-c810-4c4c-a945-a822b4efed4f)

```
CREATE TABLE Kund (
KundID INT AUTO_INCREMENT PRIMARY KEY,
Bilmärke varchar(10),
RegNummer VARCHAR(10) NOT NULL,
Namn VARCHAR(100) NOT NULL,
Telefon VARCHAR(20)
);
```

```
CREATE TABLE Servicehistorik (
ServiceID INT PRIMARY KEY AUTO_INCREMENT,
ServiceTypID INT,
KundID INT,
ServciceDatum TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
FOREIGN KEY (KundID) REFERENCES Kund(KundID),
FOREIGN KEY (ServiceTypID) REFERENCES ServiceTyp(ServiceTypID)
);
```

```
CREATE TABLE ServiceTyp(
ServiceTypID PRIMARY KEY AUTO_INCREMENT,
ServiceTyp varchar(100),
Pris DECIMAL(10,2) NOT NULL
);
```

```
CREATE TABLE Reservdel (
ReservdelID INT PRIMARY KEY AUTO_INCREMENT,
Namn VARCHAR(100) NOT NULL,
Pris DECIMAL(10,2) NOT NULL
);
```

```
CREATE TABLE ReservdelHandel (
FörsäljningID INT PRIMARY KEY AUTO_INCREMENT,
KundID INT,
ReservdelID INT,
Antal INT,
FörsäljningsDatum DATE,
FOREIGN KEY (KundID) REFERENCES Kund(KundID),
FOREIGN KEY (ReservdelID) REFERENCES Reservdel(ReservdelID)
);
```

```
CREATE TABLE Verktyg (
VerktygID INT,
VerktygNamn varchar(100),
Pris DECIMAL(10,2)
);
```

FÖR OLLES PERSPEKTIV:

```
CREATE TABLE Arbetare (
ArbetareID INT PRIMARY KEY AUTO_INCREMENT,
Namn varchar(100),
Telefonnummer varchar(100)
);
```

```
CREATE TABLE Arbetsuppgift (
ArbetsuppgiftID INT PRIMARY KEY AUTO_INCREMENT,
ArbetareID INT,
Område VARCHAR(20),
Arbetsuppgift VARCHAR(100),
FOREIGN KEY (ArbetareID) REFERENCES Arbetare(ArbetareID)
);
```
