![image](https://github.com/user-attachments/assets/7ba746f0-6025-463a-a542-f747868a735a)



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

 
