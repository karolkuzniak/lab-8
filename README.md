© 2013 Cisco and/or its affiliates. All rights reserved. This document is Cisco Public. Strona 1 z 8
Laboratorium - Odczytywanie adresów MAC w urządzeniach
sieciowych
Topologia
Tabela adresacji
Urządzenie Interfejs Adres IP Maska podsieci
Brama
domyślna
R1 G0/1 192.168.1.1 255.255.255.0 nie dotyczy
S1 VLAN 1 nie dotyczy Nie dotyczy Nie dotyczy
PC-A NIC 192.168.1.3 255.255.255.0 192.168.1.1
Cele
Część 1: Utworzenie topologii i uruchomienie urządzeń
 Połączenie urządzeń zgodnie z topologią.
 Uruchomienie routera i przełącznika oraz (jeśli jest to konieczne) usunięcie konfiguracji oraz ponowne
uruchomienie urządzeń.
Część 2: Konfiguracja urządzeń i weryfikacja połączeń
 Przypisanie statycznego adresu IP do karty sieciowej komputera PC-A.
 Konfiguracja podstawowych parametrów routera R1.
 Przypisanie statycznego adresu IP na R1.
 Weryfikacja połączeń sieciowych.
Część 3: Prezentacja, omówienie oraz analiza adresacji MAC w sieci.
 Analiza adresacji MAC komputera PC-A
 Analiza adresacji MAC routera R1.
 Wyświetlenie tablicy adresów MAC przełącznika S1.
Scenariusz
W sieciach Ethernet każde urządzenie jest identyfikowane poprzez adres MAC warstwy 2. Adres ten jest
zapisany w karcie sieciowej. Ćwiczenie to zawiera przegląd oraz analizę komponentów, z których składa się
adres MAC. Pokazane zostaną również sposoby uzyskania informacji o adresacji MAC różnych urządzeń
sieciowych, takich jak router, przełącznik czy komputer PC.
Laboratorium - Odczytywanie adresów MAC w urządzeniach sieciowych
© 2013 Cisco and/or its affiliates. All rights reserved. This document is Cisco Public. Strona 2 z 8
W pierwszej kolejności połączysz urządzenia zgodnie z topologią. Następnie skonfigurujesz router i komputer
PC zgodnie z załączoną tabelą adresacji. Zweryfikujesz swoją konfigurację testując połączenia za pomocą
komendy ping.
Po skonfigurowaniu urządzeń i sprawdzeniu połączenia sieciowego, wywołasz serię różnych komend w celu
uzyskania informacji i odpowiedzi na pytania dotyczące działania urządzeń sieciowych.
Uwaga: Routery używane w laboratorium CCNA to Cisco 1941 ISR (Integrated Services Routers) z
oprogramowaniem Cisco IOS wersja 15.2(4)M3 (obraz universalk9). Zastosowane w laboratorium
przełączniki to Cisco Catalyst 2960s z oprogramowaniem Cisco IOS wersja 15.0(2) (obraz lanbasek9).
Podczas laboratorium można wykorzystać inne routery, przełączniki oraz wersje systemu Cisco IOS. Zależnie
od modelu urządzenia i wersji systemu IOS dostępne komendy i wyniki ich działania mogą się różnic od
prezentowanych w niniejszej instrukcji. Podczas laboratorium wykorzystaj Identyfikatory interfejsów
znajdujące się w tabeli interfejsów routerów umieszczonej na końcu tej instrukcji.
Uwaga: Upewnij się, że konfiguracje routerów i przełączników zostały usunięte i nie mają konfiguracji
startowej. Jeśli nie jesteś pewien, poproś o pomoc instruktora.
Wymagane wyposażenie
 1 router (Cisco 1941 z oprogramowaniem Cisco IOS, wersja 15.2 (4) M3 obraz uniwersalny lub
porównywalny)
 1 przełącznik (Cisco 2960 Cisco IOS wersja15.0 (2) obraz lanbasek9 lub porównywalny)
 1 komputer PC (z systemem Windows 7, Vista, lub XP z emulatorem terminala takim jak Tera Term)
 Kable konsolowe do konfiguracji urządzeń Cisco przez port konsolowy
 Kable Ethernet zgodnie z zamieszczoną topologią
Część 1. Utworzenie topologii i uruchomienie urządzeń
W części 1 będziesz tworzyć sieć zgodnie z załączoną topologią, w razie potrzeby usuniesz istniejącą
konfigurację urządzeń oraz będziesz tworzyć podstawową konfigurację routera i przełącznika.
Krok 1. Wykonaj okablowanie sieci zgodnie z topologią.
a. Połącz wymagane urządzenia odpowiednimi kablami, tak jak pokazano na schemacie topologii.
b. Włącz zasilanie wszystkich urządzeń pokazanych w topologii.
Krok 2. Zainicjalizuj i zrestartuj router oraz przełącznik.
Część 2. Konfiguracja urządzeń i weryfikacja połączeń
W części 2 zestawisz topologię i skonfigurujesz podstawowe ustawienia, takie jak adresy IP interfejsów,
dostęp do urządzenia oraz hasła. Zajrzyj do tabeli adresacji oraz topologii aby uzyskać informacje na temat
nazw urządzeń oraz ich adresacji.
Krok 1. Skonfiguruj adres IPv4 dla komputera PC.
a. Skonfiguruj adres IPv4, maskę podsieci i adres bramy domyślnej dla komputera PC-A
b. Wykonaj komendę ping na adres bramy domyślnej (interfejs R1) z poziomu wiersza poleceń komputera
PC-A

Laboratorium - Odczytywanie adresów MAC w urządzeniach sieciowych
© 2013 Cisco i/lub partnerzy. All rights reserved. (Wszelkie prawa zastrzeżone). Ten dokument jest Cisco Public. Strona3 z8
Krok 2. Skonfiguruj router.
a. Podłącz się do konsoli routera i przejdź do trybu konfiguracji globalnej.
b. Przypisz nazwę hosta routerowi bazując na tablicy adresacji.
c. Wyłącz przeszukiwanie nazw domenowych.
d. Skonfiguruj i włącz interfejs G0/1 routera.
Krok 3. Zweryfikuj połączenia sieciowe.
a. Wykonaj polecenie ping z komputera PC-A do bramy domyślnej R1.

Część 3. Prezentacja, omówienie oraz analiza adresacji MAC w sieci.
Każde urządzenie w sieci Ethernet LAN posiada zapisany na stałe adres MAC (Media Access Control) w
interfejsie sieciowym (NIC). Długość adresu MAC wynosi 48 bitów. Są one przedstawiane w postaci sześciu
par cyfr szesnastkowych, oddzielonych od siebie przeważnie myślnikami, dwukropkami lub kropkami.
Poniższy przykład przedstawia ten sam adres MAC zapisany przy użyciu trzech różnych notacji:
00-05-9A-3C-78-00 00:05:9A:3C:78:00 0005.9A3C.7800
Uwaga: adresy MAC są również nazywane adresami fizycznymi, adresami sprzętowymi lub ethernetowymi
adresami sprzętowymi.
W części 3 użyjesz komend, dzięki którym będzie można zobaczyć adres MAC na komputerze PC, routerze
oraz przełączniku, a także przeprowadzisz analizę właściwości każdego z nich.
Krok 1. Analiza adresacji MAC karty sieciowej komputera PC-A
Zanim rozpoczniesz analizę adresu MAC na komputerze PC-A, spójrz na przykład dotyczący karty sieciowej
innego komputera. Jeśli chcesz zobaczyć adres MAC swojej karty sieciowej, wydaj polecenieipconfig /all.
Przykładowy ekran wynikowy jest przedstawiony poniżej Zauważ, że w wynikach komendy ipconfig /all
adresy MAC są określane jako adresy fizyczne. Odczytując adres MAC od lewej strony, sześć pierwszych
cyfr w reprezentacji szesnastkowej związana jest z dostawcą (producentem) urządzenia. Te pierwsze sześć
cyfr (3 bajty) znane są także jako unikatowy identyfikator organizacji (organizationally unique identifier - OUI).
Ten 3-bajtowy kod jest przyporządkowywany dostawcy przez organizację IEEE. Jeśli chcesz znaleźć
producenta, możesz użyć narzędzia takiego jak www.macvendorlookup.comlub udać się na stronę IEEE i
przeszukać zarejestrowane kody OUI dostawców. Adres strony IEEE, na której można odnaleźć informacje
na temat OUI: http://standards.ieee.org/develop/regauth/oui/public.html Ostatnie sześć cyfr adresu fizycznego
jest numerem seryjnym karty sieciowej przypisanym przez producenta.
a. Korzystając z wyniku komendy ipconfig /all, odpowiedz na następujące pytania.
Jaką postać ma identyfikator OUI dla wskazanego adresu MAC karty sieciowej?
Laboratorium - Odczytywanie adresów MAC w urządzeniach sieciowych
© 2013 Cisco i/lub partnerzy. All rights reserved. (Wszelkie prawa zastrzeżone). 

Krok 2. Analiza adresacji MAC interfejsu G0/1 routera R1.
Możesz użyć różnych poleceń, aby wyświetlić adresy MAC routera.
a. Aby odnaleźć informacje o adresie MAC, połącz się przy pomocy konsoli do routera R1 i wydaj
polecenieshow interfaces g0/1. Przykład jest widoczny poniżej. Używając komunikatów wyjściowych
twojego routera, odpowiedz na pytania.
R1> show interfaces g0/1
GigabitEthernet0/1 is up, line protocol is up
 Hardware is CN Gigabit Ethernet, address is 30f7.0da3.1821 (bia 30f7.0da3.1821)
 Internet address is 192.168.1.1/24
 MTU 1500 bytes, BW 100000 Kbit/sec, DLY 100 usec,
 reliability 255/255, txload 1/255, rxload 1/255
 Encapsulation ARPA, loopback not set
 Keepalive set (10 sec)
 Full Duplex, 100Mbps, media type is RJ45
 output flow-control is unsupported, input flow-control is unsupported
 ARP type: ARPA, ARP Timeout 04:00:00
 Last input 00:00:00, output 00:00:00, output hang never
 Last clearing of "show interface" counters never
 Input queue: 0/75/0/0 (size/max/drops/flushes); Total output drops: 0
 Queueing strategy: fifo
 Output queue: 0/40 (size/max)
 5 minute input rate 3000 bits/sec, 4 packets/sec
 5 minute output rate 0 bits/sec, 0 packets/sec
 15183 packets input, 971564 bytes, 0 no buffer
 Received 13559 broadcasts (0 IP multicasts)
 0 runts, 0 giants, 0 throttles
 0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored
 0 watchdog, 301 multicast, 0 pause input
 1396 packets output, 126546 bytes, 0 underruns
 0 output errors, 0 collisions, 1 interface resets
 195 unknown protocol drops
 0 babbles, 0 late collision, 0 deferred
Laboratorium - Odczytywanie adresów MAC w urządzeniach sieciowych
© 2013 Cisco i/lub partnerzy. All rights reserved. (Wszelkie prawa zastrzeżone). Ten dokument jest Cisco Public. Strona5 z8
 0 lost carrier, 0 no carrier, 0 pause output
 0 output buffer failures, 0 output buffers swapped out

b. Innym sposobem wyświetlenia adresów MAC na routerze jest użycie polecenia show arp. Użyj polecenia
show arp, aby wyświetlić informacje o adresie MAC. Polecenie to umożliwia wyświetlenie adresów
warstwy 2 powiązanych z adresami warstwy 3. Poniżej przedstawiono przykładowy wynik wykonania tej
komendy. Używając wyników uzyskanych na twoim routerze, odpowiedz na pytania.
R1> show arp
Protocol Address Age (min) Hardware Addr Type Interface
Internet 192.168.1.1 - 30f7.0da3.1821 ARPA GigabitEthernet0/1
Internet 192.168.1.3 0 c80a.a9fa.de0d ARPA GigabitEthernet0/1

Krok 3. Przejrzyj adresy MAC na przełączniku.
a. Połącz się kablem konsolowym do przełącznika i wykonaj polecenie show interfaces dla portów 5 i 6
aby wyświetlić informacje o adresach MAC. Przykładowy wynik wywołania takiej komendy zamieszczono
poniżej. Używając komunikatów wyjściowych twojego przełącznika, odpowiedz na pytania.
Switch> show interfaces f0/5
FastEthernet0/5 is up, line protocol is up (connected)
 Hardware is Fast Ethernet, address is 0cd9.96e8.7285 (bia 0cd9.96e8.7285)
 MTU 1500 bytes, BW 100000 Kbit, DLY 100 usec,
 reliability 255/255, txload 1/255, rxload 1/255
 Encapsulation ARPA, loopback not set
 Keepalive set (10 sec)
 Full-duplex, 100Mb/s, media type is 10/100BaseTX
 input flow-control is off, output flow-control is unsupported
Laboratorium - Odczytywanie adresów MAC w urządzeniach sieciowych
© 2013 Cisco i/lub partnerzy. All rights reserved. (Wszelkie prawa zastrzeżone). Ten dokument jest Cisco Public. Strona6 z8
 ARP type: ARPA, ARP Timeout 04:00:00
 Last input 00:00:45, output 00:00:00, output hang never
 Last clearing of "show interface" counters never
 Input queue: 0/75/0/0 (size/max/drops/flushes); Total output drops: 0
 Queueing strategy: fifo
 Output queue: 0/40 (size/max)
 5 minute input rate 0 bits/sec, 0 packets/sec
 5 minute output rate 0 bits/sec, 0 packets/sec
 3362 packets input, 302915 bytes, 0 no buffer
 Received 265 broadcasts (241 multicasts)
 0 runts, 0 giants, 0 throttles
 0 input errors, 0 CRC, 0 frame, 0 overrun, 0 ignored
 0 watchdog, 241 multicast, 0 pause input
 0 input packets with dribble condition detected
 38967 packets output, 2657748 bytes, 0 underruns
 0 output errors, 0 collisions, 1 interface resets
 0 babbles, 0 late collision, 0 deferred
 0 lost carrier, 0 no carrier, 0 PAUSE output
 0 output buffer failures, 0 output buffers swapped out
Jaki jest adres MAC interfejsu F0/5 na twoim przełączniku?
____________________________________________________________________________________
Wykonaj to samo polecenie dla interfejsu F0/6 i zanotuj jego adres MAC.
____________________________________________________________________________________
Czy OUI (kod producenta) adresu na przełączniku są takie same jak analogiczne wyświetlone na
routerze?
____________________________________________________________________________________
Przełącznik utrzymuje łączność z urządzeniami dzięki wykorzystaniu adresów MAC warstwy 2. W naszej
topologii przełącznik przechowuje informacje o adresach MAC routera R1 oraz MAC komputera PC-A.
b. Wykonaj na przełączniku polecenie show mac address-table. Przykład zamieszczono poniżej. Używając
komunikatów wyjściowych twojego przełącznika, odpowiedz na pytania.
Switch> show mac address-table
 Mac Address Table
-------------------------------------------
Vlan Mac Address Type Ports
---- ----------- -------- -----
All 0100.0ccc.cccc STATIC CPU
All 0100.0ccc.cccd STATIC CPU
All 0180.c200.0000 STATIC CPU
All 0180.c200.0001 STATIC CPU
All 0180.c200.0002 STATIC CPU
All 0180.c200.0003 STATIC CPU
All 0180.c200.0004 STATIC CPU
All 0180.c200.0005 STATIC CPU
All 0180.c200.0006 STATIC CPU
All 0180.c200.0007 STATIC CPU
Laboratorium - Odczytywanie adresów MAC w urządzeniach sieciowych
© 2013 Cisco i/lub partnerzy. All rights reserved. (Wszelkie prawa zastrzeżone). Ten dokument jest Cisco Public. Strona7 z8
All 0180.c200.0008 STATIC CPU
All 0180.c200.0009 STATIC CPU
All 0180.c200.000a STATIC CPU
All 0180.c200.000b STATIC CPU
All 0180.c200.000c STATIC CPU
All 0180.c200.000d STATIC CPU
All 0180.c200.000e STATIC CPU
All 0180.c200.000f STATIC CPU
All 0180.c200.0010 STATIC CPU
All ffff.ffff.ffff STATIC CPU
 1 30f7.0da3.1821 DYNAMIC Fa0/5
 1 c80a.a9fa.de0d DYNAMIC Fa0/6
Total Mac Addresses for this criterion: 22
