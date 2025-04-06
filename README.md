# TSC_Project_EBookReader

Acest proiect reprezintă un sistem de tip **eBook Reader** bazat pe microcontrolerul **ESP32-C6**, ce integrează module de stocare, afișare, senzori de mediu, alimentare prin baterie și interfețe de conectivitate. Dispozitivul este proiectat pentru un consum energetic scăzut și este compatibil cu multiple tipuri de afișaje E-Ink.

---

## Descriere a componentelor și funcționalității hardware

### Microcontroller: ESP32-C6

- Microcontroller RISC-V pe 32 de biți cu suport **Wi-Fi 6** și **Bluetooth 5 Low Energy (BLE)**
- Alimentat la **3.3V**
- Gestionează toate perifericele proiectului
- Interfețe disponibile: **GPIO, SPI, I2C, UART**
- Arhitectură optimizată pentru **consum redus de energie**, ideală pentru aplicații portabile

---

### Alimentare și protecție

#### Regulator de tensiune LDO

- **XC6206P332MR-G** transformă tensiunea VIN (5V) în 3.3V
- Tranzistor PNP suplimentar pentru controlul alimentării

#### Controller de încărcare baterie

- **MCP73831** gestionează încărcarea bateriei Li-Po 3.7V
- Include protecție la supratensiune și curent excesiv
- LED-uri de stare încărcare

#### Monitorizare nivel baterie

- **MAX17048** monitorizează starea bateriei în timp real
- Comunică prin interfața I2C

#### Conector USB-C și protecție ESD

- Conector **USB-C** pentru alimentare și comunicație
- Protecție ESD: **PMF0501** și **USBLC6-2SC6Y**

---

## Stocare

### Card microSD

- Conectat la magistrala **SPI**
- Permite stocarea fișierelor eBook și a jurnalelor
- Linie dedicată pentru **detectare automată**

### Memorie NOR Flash externă (64MB)

- **W25Q512JVEIQ**
- Memorie nevolatilă pentru firmware și resurse statice
- Conectată la magistrala **SPI**

---

## Afișaj E-Paper

### Interfață EPD dedicată

- Conexiuni: **SPI**, semnale de control (**EPD_BUSY**, **EPD_DC**, **EPD_RST** etc.)
- Header dedicat EPD cu 20 pini, compatibil cu mai multe modele

### Circuit de alimentare EPD

- Convertor **DC-DC** și tranzistoare **MOSFET**

### Selector tip afișaj

- Permite alegerea tipului de ecran conectat

---

## Senzor BME688

- Măsoară: **temperatură, umiditate, presiune atmosferică, calitate aer (VOCs)**
- Conectare prin interfața **I2C**

---

## Modul RTC (DS3231SN)

- Precizie ridicată
- Menține ora și data în lipsa alimentării
- Interfață **I2C**

---

## Butoane de control

- Buton **RESET**
- Buton **BOOT**
- Buton custom **IO/CHANGE**

---

## Test Pads și Conectori de extensie

- **Paduri de test** și debugging
- Conector **Qwiic/Stemma QT** pentru senzori I2C suplimentari

---

## Protecție ESD pentru SPI

- Liniile **SPI** sunt protejate împotriva descărcărilor electrostatice

---

## Consum estimativ de energie

| Componentă               | Consum estimativ       |
|--------------------------|-------------------------|
| ESP32-C6 (Wi-Fi activ)   | 120 – 150 mA            |
| Afișaj EPD               | 20 – 40 mA              |
| Senzor BME688            | 1 – 2 mA                |
| Card SD (scriere/citire)| 50 – 100 mA             |
| MAX17048 + RTC DS3231    | < 1 mA                  |
| **Total (mod activ)**    | **~300 mA**             |
| **Total (deep sleep)**   | **< 10 mA**             |

### Estimare autonomie (baterie LiPo 2000mAh):

- **Folosire intensivă**: 5–7 ore
- **Standby cu afiș static**: zile/săptămâni

---

## Alocarea pinilor ESP32-C6

### 1. Afișaj EPD (e-paper display)

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO3 (26)     | EPD_BUSY    | Verifică dacă ecranul este ocupat   |
| IO5 (5)      | EPD_DC      | Comută între date și comandă        |
| IO6 (6)      | SCK         | Linie de ceas SPI (partajată)       |
| IO7 (7)      | MOSI        | Transmisie date SPI                 |
| IO10 (11)    | EPD_CS      | Selectare chip pentru EPD           |
| IO23 (21)    | EPD_RST     | Resetare ecran                      |
| IO20 (18)    | EPD_3V3_C   | Control alimentare 3V3 pentru EPD   |

---

### 2. Card SD

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO2 (27)     | MISO        | Recepție date SPI                   |
| IO4 (4)      | SS_SD       | Selectare chip SD                   |
| IO6 (6)      | SCK         | Linie de ceas SPI (partajată)       |
| IO7 (7)      | MOSI        | Transmisie date SPI                 |

---

### 3. Memorie Flash NOR

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO11 (12)    | FLASH_CS    | Selectare chip Flash                |
| IO2 (27)     | MISO        | Recepție date SPI                   |
| IO6 (6)      | SCK         | Linie de ceas SPI (partajată)       |
| IO7 (7)      | MOSI        | Transmisie date SPI                 |

---

### 4. Magistrală I2C (BME688, RTC DS3231, MAX17048)

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO21 (19)    | SDA         | Linie de date I2C                   |
| IO22 (20)    | SCL         | Linie de ceas I2C                   |
| IO19 (17)    | I2C_PW      | Activare alimentare senzori I2C     |

---

### 5. RTC (DS3231)

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO0 (8)      | INT_RTC     | Semnal de întrerupere               |
| IO1 (9)      | 32KHz       | Ieșire ceas precis                  |
| IO18 (16)    | RTC_RST     | Reset hardware RTC                  |

---

### 6. Conectivitate USB

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO12 (13)    | USB_D-      | Comunicație USB                     |
| IO13 (14)    | USB_D+      | Comunicație USB                     |

---

### 7. Serială UART 

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO16 (25)    | TX          | Transmisie UART                     |
| IO17 (24)    | RX          | Recepție UART                       |

---

### 8. Butoane 

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| EN (3)       | RESET       | Reset general microcontroler        |
| IO8 (10)     | IO/BOOT     | Buton BOOT (pus pe GND la pornire)  |
| IO15 (23)    | IO/CHANGE   | Buton custom                        |

---

### 9. Alimentare și Referință

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| Pin 2        | 3V3         | Alimentare principală               |
| Pin 1        | GND         | Împământare                         |
