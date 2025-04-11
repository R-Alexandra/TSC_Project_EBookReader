# TSC_Project_EBookReader - Rădulescu Alexandra

Acest proiect reprezintă un sistem de tip **eBook Reader** bazat pe microcontrolerul **ESP32-C6**, ce integrează module de stocare, afișare, senzori de mediu, alimentare prin baterie și interfețe de conectivitate. Dispozitivul este proiectat pentru un consum energetic scăzut și este compatibil cu multiple tipuri de afișaje E-Ink.

---
## Diagramă Bloc
![Diagrama_Bloc](https://github.com/user-attachments/assets/b81236ec-386f-4a0d-bd1f-8474d03ccdcd)


---

## Bill of Materials (BOM)

| Componentă                | Link Achiziționare | Link Datasheet |
|---------------------------|--------------------|----------------|
| 112A-TAAR-R03 ATTEND      | https://store.comet.srl.ro/Catalogue/Product/43497/ | https://www.snapeda.com/parts/112A-TAAR-R03/Attend/datasheet/ |
| Condensator C0402         | https://ro.mouser.com/c/passive-components/capacitors/ceramic-capacitors/?q=CC0402 | https://componentsearchengine.com/Datasheets/2/CC0402MRX5R5BB106.pdf |
| Condensator Tantalum      | https://ro.mouser.com/ProductDetail/KYOCERA-AVX/TAJW107M010RNJ?qs=Wtp%252Bf%2FAeVqIH8v1VxV%252B1Rg%3D%3D | https://ro.mouser.com/datasheet/2/40/TAJ-3165264.pdf |
| CHG_LED                   | https://ro.mouser.com/ProductDetail/Kingbright/KP-1608SURCK?qs=2JU0tDl2GZ3FuyEWfBV1%2Fg== | https://www.snapeda.com/parts/KP-1608SURCK/Kingbright/datasheet/ |
| USBLC6-2SC6Y              | https://ro.mouser.com/ProductDetail/STMicroelectronics/USBLC6-2SC6Y?qs=gNDSiZmRJS%2FOgDexvXkdow%3D%3D | https://ro.mouser.com/datasheet/2/389/usblc6_2sc6y-1852505.pdf |
| SD0805S020S1R0            | https://ro.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D | https://ro.mouser.com/datasheet/2/40/schottky-3165252.pdf |
| MBR0530                   | https://ro.mouser.com/ProductDetail/onsemi-Fairchild/MBR0530?qs=VOMQJJE%252BBNniwJKcE3T43Q== | https://ro.mouser.com/datasheet/2/308/MBR0530_D-1810985.pdf |
| PGB1010603MR              | https://www.digikey.com/en/products/detail/littelfuse-inc/PGB1010603MR/715755 | https://www.littelfuse.com/assetdocs/pulseguard-esd-suppressors-pgb1-datasheet?assetguid=8a337998-d54d-466b-be4e-dc5bcd1f9321 |
| Rezistență R0402         | https://ro.mouser.com/c/passive-components/resistors/smd-resistors-chip-resistors/?case%20code%20-%20in=0402 | https://www.yageo.com/upload/media/product/products/datasheet/rchip/PYu-RC_Group_51_RoHS_L_12.pdf |
| BME680                    | https://ro.mouser.com/ProductDetail/Bosch-Sensortec/BME688?qs=IS%252B4QmGtzzqQoVDscqwx3A%3D%3D | https://ro.mouser.com/datasheet/2/783/bst_bme688_fl000-2307034.pdf |
| W25Q512JVEIQ              | https://ro.mouser.com/ProductDetail/Winbond/W25Q512JVEIQ?qs=l7cgNqFNU1jw6svr3at6tA%3D%3D | https://ro.mouser.com/datasheet/2/949/Winbond_W25Q512JV_Datasheet-3240039.pdf |
| ESP32-C6-WROOM-1-N8       | https://ro.mouser.com/ProductDetail/Espressif-Systems/ESP32-C6-WROOM-1-N8?qs=8Wlm6%252BaMh8ST02Gmwp74cw%3D%3D | https://ro.mouser.com/datasheet/2/891/Espressif_ESP32_C6_WROOM_1__Datasheet_V0_1_PRELIMI-3239987.pdf |
| DS3231SN#                 | https://ro.mouser.com/ProductDetail/Analog-Devices-Maxim-Integrated/DS3231SN?qs=1eQvB6Dk1vhUlr8%2FOrV0Fw%3D%3D | https://ro.mouser.com/datasheet/2/609/DS3231-3421123.pdf |
| MAX17048G+T10             | https://ro.mouser.com/ProductDetail/Analog-Devices-Maxim-Integrated/MAX17048G%2bT10?qs=D7PJwyCwLAoGnnn8jEPRBQ%3D%3D | https://ro.mouser.com/datasheet/2/609/MAX17048_MAX17049-3469099.pdf |
| MCP73831                  | https://ro.mouser.com/ProductDetail/Microchip-Technology/MCP73831T-2ATI-OT?qs=yUQqVecv4qsZbioEUu%252B83g%3D%3D | https://ro.mouser.com/datasheet/2/268/MCP73831_Family_Data_Sheet_DS20001984H-3441711.pdf |
| BD5229G-TR                | https://www.digikey.com/en/products/detail/rohm-semiconductor/BD5229G-TR/3663792 | https://fscdn.rohm.com/en/products/databook/datasheet/ic/power/voltage_detector/bd52xxg-e.pdf |
| XC6220A331MR-G            | https://ro.mouser.com/ProductDetail/Torex-Semiconductor/XC6220A331MR-G?qs=AsjdqWjXhJ8ZSWznL1J0gg%3D%3D | https://ro.mouser.com/datasheet/2/760/xc6220-3371556.pdf |
| FH34SRJ-24S-0.5SH(99)     | https://ro.mouser.com/ProductDetail/Hirose-Connector/FH34SRJ-24S-0.5SH99?qs=vcbW%252B4%252BSTIpKBl5ap9J8Fw%3D%3D | https://ro.mouser.com/datasheet/2/185/FH34SRJ_24S_0_5SH_99__CL0580_1255_6_99_2DDrawing_0-1615044.pdf |
| USB4110-GF-A              | https://ro.mouser.com/ProductDetail/GCT/USB4110-GF-A?qs=KUoIvG%2F9IlYiZvIXQjyJeA%3D%3D | https://ro.mouser.com/datasheet/2/837/GCT_USB4110_Product_Drawing___20k_cycles-3455479.pdf |
| QWIIC_RIGHT_ANGLE         | https://ro.mouser.com/ProductDetail/SparkFun/PRT-14417?qs=wd5RIQLrsJhgdz%2FpmZ%2F3GQ== | https://ro.mouser.com/datasheet/2/813/Qwiic_Connector_Datasheet-1223982.pdf |
| Bobină 744043680         | https://ro.mouser.com/ProductDetail/Wurth-Elektronik/744043680?qs=PGXP4M47uW6VkZq%252BkzjrHA%3D%3D | https://www.we-online.com/components/products/datasheet/744043680.pdf |
| PFMF.050.1                | https://ro.mouser.com/ProductDetail/EPCOS-TDK/B72520T0350K062?qs=dEfas%2FXlABIszF52uu7vrg%3D%3D | https://www.tdk-electronics.tdk.com/inf/75/db/CTVS_14/Surge_protection_series.pdf |
| DMG2305UX-7               | https://www.digikey.com/en/products/detail/diodes-incorporated/DMG2305UX-7/4340666 | https://www.diodes.com/assets/Datasheets/DMG2305UX.pdf |
| Si1308EDL-T1-GE3          | https://www.digikey.com/en/products/detail/vishay-siliconix/SI1308EDL-T1-GE3/4876435 | https://www.vishay.com/docs/63399/si1308edl.pdf |
| Solder Jumper (SJ)        | https://grabcad.com/library/solder-jumpers-1 | https://grabcad.com/library/solder-jumpers-1 |
| Buton                     | https://industry.panasonic.com/global/en/products/control/switch/light-touch/number/evqpuj02k | https://industry.panasonic.com/global/en/downloads?tab=catalog&small_g_cd=203&part_no=EVQPUJ02K |
| CPH3225A                  | https://www.digikey.com/en/products/detail/seiko-instruments/CPH3225A/8692444 | https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/6537/rev05-CPHCPM.pdf |

---

## Descriere a componentelor și funcționalității hardware

### Microcontroller: ESP32-C6

- Microcontroller RISC-V pe 32 de biți cu suport **Wi-Fi 6** și **Bluetooth 5 Low Energy (BLE)**
- Alimentat la **3.3V**
- Gestionează toate perifericele proiectului
- Oferă multiple interfețe  **GPIO, SPI, I2C, UART**
  - **SPI**(Serial Peripheral Interface): pentru conectare la memoria NOR Flash, cardul SD și afișajul E-Ink
  - **I2C**(Inter-Integrated Circuit): pentru conectare la senzorul BME688, modulul RTC DS3231 și senzorul de nivel baterie MAX17048
  - **GPIO**(General Purpose Input/Output): utilizat pentru semnale de control pentru ecranul E-Ink, butoane și detecție SD
- Are o arhitectură optimizată pentru **consum redus de energie**, ideală pentru aplicații portabile


### Alimentare și protecție

#### Regulator de tensiune LDO

- **XC6206P332MR-G** transformă tensiunea VIN (5V) în 3.3V și  este folosit un tranzistor suplimentar pentru controlul alimentării

#### Controller de încărcare baterie

- **MCP73831** gestionează încărcarea bateriei Li-Po 3.7V cu protecție integrată contra supratensiunii și a curentului excesiv
- LED-uri pentru semnalizare stare de încărcare

#### Monitorizare nivel baterie

- **MAX17048** oferă monitorizare în timp real a stării de încărcare a bateriei 
- Comunică cu ESP32-C6 prin interfața I2C

#### Conector USB-C și protecție ESD

- Conector **USB-C** pentru alimentare și comunicație
- Protecție la descărcări electrostatice realizată prin **PMF0501** și **USBLC6-2SC6Y**, care protejează liniile de alimentare și semnal


## Stocare

### Card microSD

- Conectat la magistrala **SPI**
- Permite stocarea fișierelor eBook și a jurnalelor de sistem
- Linie dedicată pentru **detectare automată** a cardului

### Memorie NOR Flash externă (64MB)

- Chipul **W25Q512JVEIQ** furnizeză memorie nevolatilă pentru firmware și resurse statice
- Conectată la magistrala **SPI**


## Afișaj E-Paper

### Interfață EPD dedicată

- Include toate conexiunile necesare pentru controlul unui ecran E-Ink (**SPI**, semnale de control precum **EPD_BUSY, EPD_DC, EPD_RST** etc).
- Header dedicat EPD cu 20 pini, compatibil cu mai multe modele DE afișaje.

### Circuit de alimentare EPD

- Utilizează un convertor DC-DC și tranzistoare MOSFET pentru a genera tensiunile de alimentare cerute de ecranele E-Ink.

### Selector tip afișaj

- Permite alegerea tipului de ecran conectat, în funcție de compatibilitatea cu semnalele de control.



## Senzor BME680

- Măsoară: **temperatură, umiditate, presiune atmosferică, calitate aer (VOCs)**
- Este conectat prin interfața **I2C** (SDA și SCL)



## Modul RTC (DS3231SN)

- Precizie ridicată pentru a păstra ora și data corectă, chiar și în absența alimentării principale.
- Interfață **I2C** (SDA și SCL)



## Butoane de control

- Buton **RESET**
- Buton **BOOT**
- Buton custom **IO/CHANGE**



## Test Pads și Conectori de extensie

- Sunt prezente **paduri de testare** și debugging 
- Conector **Qwiic/Stemma QT** pentru extinderea rapidă a sistemului cu senzori I2C suplimentari



## Protecție ESD pentru SPI

- Liniile **SPI** sunt protejate împotriva descărcărilor electrostatice

---

## Consum estimativ de energie
Sistemul este proiectat pentru un consum energetic redus, aspect esențial pentru funcționarea pe baterie.

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
- **Folosire intensivă**: câteva ore
- **Standby cu afiș static**: zile/săptămâni

---

## Alocarea pinilor ESP32-C6

### 1. Afișaj EPD (e-paper display)

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO3 (26)     | EPD_BUSY    | Verifică dacă ecranul este ocupat   |
| IO5 (5)      | EPD_DC      | Comută între date și comandă        |
| IO6 (6)      | SCK         | Linie de ceas SPI                   |
| IO7 (7)      | MOSI        | Transmisie date SPI                 |
| IO10 (11)    | EPD_CS      | Selectare chip pentru EPD           |
| IO23 (21)    | EPD_RST     | Resetare ecran                      |
| IO20 (18)    | EPD_3V3_C   | Control alimentare 3V3 pentru EPD   |



### 2. Card SD

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO2 (27)     | MISO        | Recepție date SPI                   |
| IO4 (4)      | SS_SD       | Selectare chip SD                   |
| IO6 (6)      | SCK         | Linie de ceas SPI                   |
| IO7 (7)      | MOSI        | Transmisie date SPI                 |



### 3. Memorie Flash NOR

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO11 (12)    | FLASH_CS    | Selectare chip Flash                |
| IO2 (27)     | MISO        | Recepție date SPI                   |
| IO6 (6)      | SCK         | Linie de ceas SPI                   |
| IO7 (7)      | MOSI        | Transmisie date SPI                 |



### 4. Magistrală I2C (BME688, RTC DS3231, MAX17048)

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO21 (19)    | SDA         | Linie de date I2C                   |
| IO22 (20)    | SCL         | Linie de ceas I2C                   |
| IO19 (17)    | I2C_PW      | Activare alimentare senzori I2C     |



### 5. RTC (DS3231)

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO0 (8)      | INT_RTC     | Semnal de întrerupere               |
| IO1 (9)      | 32KHz       | Ieșire ceas precis                  |
| IO18 (16)    | RTC_RST     | Reset hardware RTC                  |



### 6. Conectivitate USB

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO12 (13)    | USB_D-      | Comunicație USB                     |
| IO13 (14)    | USB_D+      | Comunicație USB                     |



### 7. Serială UART 

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| IO16 (25)    | TX          | Transmisie UART                     |
| IO17 (24)    | RX          | Recepție UART                       |



### 8. Butoane 

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| EN (3)       | RESET       | Reset general microcontroler        |
| IO8 (10)     | IO/BOOT     | Buton BOOT (pus pe GND la pornire)  |
| IO15 (23)    | IO/CHANGE   | Buton custom                        |



### 9. Alimentare și Referință

| Pin ESP32-C6 | Funcție     | Observație                          |
|--------------|-------------|--------------------------------------|
| Pin 2        | 3V3         | Alimentare principală               |
| Pin 1        | GND         | Împământare                         |

---

## Considerații privind realizarea proiectului
În procesul de realizare a designului hardware am respectat cerințele din ghidurile de proiectare (ERC, DRC, layout) și am încercat să iau decizii care să ofere echilibru între funcționalitate, integrare și respectarea bunelor practici. Amplasarea componentelor am făcut-o atât pe baza documentației oferite (dimensiuni mecanice și recomandări de placement), cât și pentru o rutare cât mai bună, care să reducă interferențele și să faciliteze traseele de alimentare și semnal.

Pentru designul PCB-ului, am folosit DRC-ul oferit pentru verificare și am rezolvat erorile apărute, inclusiv prin ajustarea dimensiunii unor footprint-uri. Am aplicat regulile de rutare pentru traseele de putere și pentru date, evitând unghiurile drepte. Traseele de alimentare au lățimea de 0.3mm, restul traseelor de 0.15mm și am realizat câte un plan de masă atât pentru top cât și pe bottom. Test pad-urile rămase le-am poziționat astfel încât să putem testa rapid anumite componente: 
- lângă header-ul display-ului pentru a testa alimentarea și semnalele de date către ecran;
- lângă ESP32-C6 pentru a verifica semnale critice și pentru debugging.

Am avut în vedere și integrarea finală în ansamblul 3D al carcasei. De aceea, am poziționat conectorii astfel încât să fie accesibili din exterior, iar unele componente au fost ușor translatate pentru a obține o potrivire corectă și o funcționare bună a dispozitivului. De asemenea, am desenat bateria și ecranul folosind dimensiunile mecanice specificate pentru o integrare cât mai bună. 
