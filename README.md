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

Rodzaj hashu: SHA2-512 = -m 1700

![zad1_3_1](https://user-images.githubusercontent.com/113295774/200120447-0b6a6aa3-08c8-48c9-a8be-5c80321f7690.png)

Hasło: T0^^3k
