# Projekt-2---Omijanie-zabezpiecze-
Dokumentacja do projektu nr 2
# Zadanie 1 - Łamanie haseł (met. brute-force)
Dla podanych niżej hashy określ typ wykorzystanego algorytmu hashującego, a następnie złam hasło metodą brute-force.

Typ każdego hashu został określony za pomocą narzędzia na stronie https://www.tunnelsup.com/hash-analyzer/. Hasła były łamane używając hashcat'a.

## Przypdadek 1
  Każde hasło składa się z maksymalnie 5 znaków (tylko cyfry)
  
<b> hashcat -a 3 -m N hash -i ?d?d?d?d?d </b>

-a 3 - attack mode - 3 - metoda ataku brute-force

-m N - mode - N - rodzaj używanego hashu

-i - increment - hasło jest łamane "stopniowo", biorąc pod uwagę po kolei każdą ilość znaków podaną we wzorcu 

?d?d?d?d?d - wzorzec dla hasła; ?d oznacza jedną cyfrę w haśle

<b>1. 81dc9bdb52d04dc20036dbd8313ed055</b>

Rodzaj hashu: MD5 = -m 0

![zad1_1_1](https://user-images.githubusercontent.com/113295774/200119112-606a9389-df2c-4cdb-8bce-9fa634f78d0d.png)

Hasło: 1234

<b>2. d8826bbd80b4233b7522d1c538aeaf66c64e259a</b>

Rodzaj hashu: SHA1 = -m 100

![zad1_1_2](https://user-images.githubusercontent.com/113295774/200119202-f8a64852-4073-4224-859d-7119085a0d27.png)

Hasło: 4121

<b>3.b021d0862bc76b0995927902ec697d97b5080341a53cd90b780f50fd5886f4160bbb9d4a573b76c23004c9b3a44ac95cfde45399e3357d1f651b556dfbd0d58f</b>

Rodzaj hashu: SHA2-512 = -m 1700

![zad1_1_3](https://user-images.githubusercontent.com/113295774/200119238-727a7154-2afe-45da-8378-2d4ec2d331e1.png)

Hasło: 6969

<b>4.31bca02094eb78126a517b206a88c73cfa9ec6f704c7030d18212cace820f025f00bf0ea68dbf3f3a5436ca63b53bf7bf80ad8d5de7d8359d0b7fed9dbc3ab99</b>

Rodzaj hashu: SHA2-512 = -m 1700

![zad1_1_4](https://user-images.githubusercontent.com/113295774/200119266-6bf9bdd5-0bc3-4c1a-bd6d-4b94caf9c54b.png)

Hasło: 0

## Przypadek 2
  Każde hasło składa się z maksymalnie 5 znaków (małe i wielkie litery).
  
  <b> hashcat -a 3 -m N hash -i -1 ?u?l ?1?1?1?1?1 </b>
  
-a 3 - attack mode - 3 - metoda ataku brute-force

-m N - mode - N - rodzaj używanego hashu

-i - increment - hasło jest łamane "stopniowo", biorąc pod uwagę po kolei każdą ilość znaków podaną we wzorcu 

-1 ?u?l ?1?1?1?1?1 - charset - -1 oznacza numer zestawu znaków używanych do łamania haseł; można podać wzorzec (?u?l - dowolne małe i wielkie litery; ?1?1?1?1?1 pięć znaków z podanego poprzednio zakresu) lub podać je w pliku

<b>1.9e66d646cfb6c84d06a42ee1975ffaae90352bd016da18f51721e2042d9067dcb120accc574105b43139b6c9c887dda8202eff20cc4b98bad7b3be1e471b3aa5</b>

Rodzaj hashu: SHA2-512 = -m 1700

![zad1_2_1](https://user-images.githubusercontent.com/113295774/200119667-2a387e96-2fa1-47a2-9ffe-7578397f5d1c.png)

Hasło: sda

<b>2.8a04bd2d079ee38f1af784317c4e2442625518780ccff3213feb2e207d2be42ca0760fd8476184a004b71bcb5841db5cd0a546b9b8870f1cafee57991077c4a9</b>

Rodzaj hashu: SHA2-512 = -m 1700

![zad1_2_2](https://user-images.githubusercontent.com/113295774/200119724-c8806419-d689-4b6d-b40e-ce43ef2f885b.png)

Hasło: Asia

## Przypadek 3
Hasło składa się z dokładnie z 6 znaków alfanumerycznych. (w zadaniu jest błąd - występują również znaki specjalne)

<b>hashcat -a 3 -m N hash -i -1 ?ua ?1?1?1?1?1?1 </b>

-a 3 - attack mode - 3 - metoda ataku brute-force

-m N - mode - N - rodzaj używanego hashu

-i - increment - hasło jest łamane "stopniowo", biorąc pod uwagę po kolei każdą ilość znaków podaną we wzorcu 

-1 ?a ?1?1?1?1?1?1 - charset - -1 oznacza numer zestawu znaków używanych do łamania haseł; można podać wzorzec (?a - dowolny znak; ?1?1?1?1?1?1 sześć znaków z podanego poprzednio zakresu) lub podać je w pliku

Rodzaj hashu: SHA2-512 = -m 1700

![zad1_3_1](https://user-images.githubusercontent.com/113295774/200120447-0b6a6aa3-08c8-48c9-a8be-5c80321f7690.png)

Hasło: T0^^3k

# Zadanie 2 - Łamanie haseł (met. słownikowa)
Dla podanych niżej hashy określ typ wykorzystanego algorytmu hashującego, a następnie złam hasło metodą słownikową.
Hasła pochodzą ze słownika <b> rockyou </b>

1.	Przygotowanie pliku z haszami

![zad2_1](https://user-images.githubusercontent.com/113295774/200123521-3f71e076-ef4f-426b-a8d8-dbc1367fc4bc.png)

2.	Określenie typu haszy i ustalenie formatu w john the ripper na raw-md5 dla przypadku 1-5

![zad2_21](https://user-images.githubusercontent.com/113295774/200123546-9df44ffe-ae92-4eb1-9d57-b50cc53d521f.png)

![zad2_22](https://user-images.githubusercontent.com/113295774/200123552-71516029-1d3c-4615-8a49-dde8f6fc7b84.png)

3.	Format md5 nie był odpowiedni dla przypadków 6 i 7 – szukanie odpowiedniego algorytmu

![zad2_3](https://user-images.githubusercontent.com/113295774/200123568-8702a4c8-0a93-4f73-936f-a6917d09a022.png)

4.	Ustalenie formatu w john the ripper na raw-SHA512 dla przypadku 6

![zad2_4](https://user-images.githubusercontent.com/113295774/200123585-a6914b58-2a0f-41f1-8a21-98277dd50dcb.png)

5.	Ustalenie formatu w john the ripper na raw-SHA256 dla przypadku 7

![zad2_5](https://user-images.githubusercontent.com/113295774/200123607-548c78e5-12f0-4104-a859-241da3fa1350.png)


# Zadanie 3 - Analiza ruchu HTTP

1. Rozpocznij monitorowanie ruchu sieciowego (narzędziem Wireshark).
2. W przeglądarce nawiąż połączenie z http://testphp.vulnweb.com/login.php
3. Wykonaj próbę logowania (dowolne dane).
4. Odszukaj w zapisanym ruchu swoje dane logowania.

## Rozwiązanie
1. Uruchamiamy komputer z zainstalowanym WireShark, w tym wypadku jest to Kali Linux na Hyper-V Microsoft
2. Wybieramy interfejs do nasłuchu, jeśli jest to nasz komputer to główny interfejs sieciowy (tutaj eth0) jeśli chcemy inny komputer to dublujemy na switchu port (port mirroring), dodajemy dodatkową sieciówkę i wybieramy port z tym interfejsem do nasłuchu. W naszym przypadku słuchamy ruchu lokalnego na naszym pc.

![zad3_2](https://user-images.githubusercontent.com/113295774/200120803-4dba04a8-aeb2-490f-a1da-f02dd4571cec.png)

3.	Nasłuchujemy pakietów:

![zad3_3](https://user-images.githubusercontent.com/113295774/200120824-6214d526-826f-465d-b785-14a79a4ff7a0.png)

4.	Wchodzimy na stronę internetową aby sprawdzić działanie logowania ( w naszym wypadku http://testphp.vulnweb.com/login.php)

![zad3_4](https://user-images.githubusercontent.com/113295774/200120844-80297f3f-4ec0-42a7-b018-b982dbafa50c.png)

5.	Wpisujemy dane do logowania test test

![zad3_5](https://user-images.githubusercontent.com/113295774/200120863-3b70e6e5-5563-4e0b-88bd-6d35c995b85e.png)

6.	Zatrzymujemy nasłuch pakietów, dane zostały już przechwycone:

![zad3_6](https://user-images.githubusercontent.com/113295774/200120883-bd20aaeb-ae4e-4565-8e9f-4713d4bd6770.png)

Obok Niebieskiego Żagielka do rozpoczęcia przechwytywania pakietów jest czerwony kwadrat stop.

7.	Filtrujemy ruch aby pokazać tylko pakiety, którymi jesteśmy zainteresowani wykorzystując

![zad3_7](https://user-images.githubusercontent.com/113295774/200120913-da5c6e5f-97ff-4911-9bb8-c4167fea6e19.png)

8.	Filtr do logowania na http ma składnię:

http.request.method == POST

![zad3_8](https://user-images.githubusercontent.com/113295774/200120930-d1af83d8-9272-433a-a299-e7c80bdb706e.png)

9.	Prawym na pakiet, Follow, TCPStream

![zad3_9](https://user-images.githubusercontent.com/113295774/200120936-5a9a9e06-08c3-4cf6-a38b-28425aec8383.png)

10.	Pokazuje się okienko, w którym na dole w Find: wpisujemy uname (znajdzie w ten sposób dane do logowania):

![zad3_10](https://user-images.githubusercontent.com/113295774/200120948-b9d928b9-4e15-4930-b91f-95d79366af7a.png)

Jak widać pierwsze dane do logowania są niepoprawne uname=loginSDA pass=pass 

Kończy się to komunikatem you must login

11.	Następne dane do logowania są już prawidłowe uname=test pass=test

![zad3_11](https://user-images.githubusercontent.com/113295774/200120958-2cf2d12c-a791-4535-9540-1be2fb0435e3.png)

12.	I tym oto sposobem znaleźliśmy dane do logowania.

![zad3_12](https://user-images.githubusercontent.com/113295774/200120970-dae49a11-8c1f-4d55-86e3-c1a1d82e4ae0.png)

# Zadanie 4 - Analiza ruchu SSH

1. Rozpocznij monitorowanie ruchu sieciowego (narzędziem Wireshark).
2. Nawiąż połączenie pomiędzy Kalim a SDA po SSH.
3. Stwórz pliki sekret1.txt i sekret2.txt z tajnymi hasłami.
4. Edytuj konfigurację vsFTPd, żeby umożliwić wgrywanie plików po FTP.
5. Zakończ połączenie po SSH.
6. Spróbuj poszukać w zapisanym ruchu sieciowym zawartość plików sekret1.txt i sekret2.txt

## Rozwiązanie
1.	Zmiana konfiguracji vsftpd do zapisu

![zad4_1](https://user-images.githubusercontent.com/113295774/200121264-580e223e-16f7-4f8e-86d7-1ddd0fb678cf.png)

Wystarczy odhashować linie 

Write_enable=YES

Local_umask=022

2.	Restart serwera vsftpd	

Z prawami roota wykonać komendę

Systemctl restart vsftpd

3.	Uruchamiamy na komputerze kali klienta wireshar, rozpoczynamy nasłuch jak w zadaniu 3 na porcie wychodzącym ( w tym wypadku eth0)

4.	Uruchamiamy klienta ftp

5.	Wpisujemy dane do połączenia i nawiązujemy połączenie

![zad4_5](https://user-images.githubusercontent.com/113295774/200121288-137da6cc-b247-401c-8ac3-5c59585e41ac.png)

6.	Przesyłamy pliki sekret1.txt oraz sekret2.txt

![zad4_6](https://user-images.githubusercontent.com/113295774/200121305-85daff80-b354-4e90-8c64-9220cb89e861.png)

7.	Zatrzymujemy i zapisujemy wynik wireshark

8.	Filtrujemy wynik w poszukiwaniu danych po ftp filtrem ftp-data

![zad4_8](https://user-images.githubusercontent.com/113295774/200121319-4d6fb120-f10c-481f-92b3-e6aa75b90a17.png)

9.	Eksportowanie złapanego pakietu do pliku za pomocą:

Export Packet Bytes Ctrl+Shift+X

Albo Show Packet Bytes i Save as…

![zad4_9](https://user-images.githubusercontent.com/113295774/200121348-e8608386-e477-48c2-aaa2-b8edf1d31111.png)

10.	Zakończone

![zad4_10](https://user-images.githubusercontent.com/113295774/200121365-a91b1cb6-265e-4d56-9eee-d1583390b216.png)

# Zadanie 5 - Analiza ruchu FTP

1. Rozpocznij monitorowanie ruchu sieciowego (narzędziem Wireshark).
2. Nawiąż połączenie pomiędzy Kalim a SDA po FTP.
3. Prześlij z Kaliego do SDA zwykły plik tekstowy (z własną zawartością).
4. Ściągnij z SDA do Kaliego pliki sekret1.txt i sekret2.txt
5. Zakończ połączenie.
6. Odszukaj w zapisanym ruchu sieciowym zawartość przesłanego i ściągniętych plików.

## Rozwiązanie
1.	Uruchamiamy Wireshark na naszym kliencie sftp i nakazujemy mu przechwytywanie pakietów na interfejsie, który dostarcza nam komunikację z serwerem ( w naszym wypadku jest to eth0).

![zad5_1](https://user-images.githubusercontent.com/113295774/200161600-a87d0182-8aef-4700-ab40-338d9829bf3d.png)

2.	Otwieramy terminal i nawiązujemy połączenie z serwerem 

![zad5_2](https://user-images.githubusercontent.com/113295774/200161610-4949d80d-5fb4-4eff-a252-a5bc59d8b874.png)

Składnia to „login” potem łącznik „@” a potem adres serwera

3.	Szukamy interesującego nas pliku poleceniami:

Ls – pokazuje zawartość katalogu

Cd – zmienia katalog

4.	Pobieramy pliki poleceniem get, wysyłamy poleceniem put, są również polecenia mkdir do tworzenia katalogu lub delete do kasowania
5.	
![zad5_4](https://user-images.githubusercontent.com/113295774/200161625-9a8179f5-e3c5-47fe-a45d-de7c42dc15dd.png)

5.	Cały ruch odnajdujemy w Wiresharku wyszukując serwer poleceniem ip

Ip.addr == „zadany adres ip”

![zad5_5](https://user-images.githubusercontent.com/113295774/200161642-dedafb3d-fc04-4c0c-a2e6-8c5ca182617f.png)

6.	Klikamy prawym przyciskiem myszy i robimy TCP Follow i widzimy cały ruch, który niestety jest zaszyfrowany

![zad5_6](https://user-images.githubusercontent.com/113295774/200161655-11b12ffe-e1c8-43f8-8263-f8a27e0a85f7.png)

7.	Niestety nawet znalezienie transakcji kluczy nie pomoże nam w odszyfrowaniu wiadomości:

![zad5_7](https://user-images.githubusercontent.com/113295774/200161661-353ec874-7822-46fe-a912-d1312a7d2de5.png)

8.	Jak wskazane na zdjęciu pakiety są zaszyfrowane, ruchu nie podsłuchamy a więc plików nie wyjmiemy.

![zad5_8](https://user-images.githubusercontent.com/113295774/200161668-68babc64-ac90-4543-8dad-be9662042359.png)


