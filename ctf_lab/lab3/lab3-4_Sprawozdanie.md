# / PRACE W TOKU /
> CTF Laboratorium nr 3/4
> 
>    Mikołaj Czajka       
> 
> 2022

***
### `Zadanie 1. Próbkowanie`
Za pomocą programu  Sonic Visualiser wczytano plik  *Oscillator_2_4_8_16kHz_PitchUp_and_PitchDown_Fs44100Hz.wav* 
i ustawiono zalecane parametry. 
Plik dźwiękowy zawierał sume sygnałów sinusoidalnych o częstotliwościach początkowych 2kHz, 4kHz, 8kHz i 16kHz
o zmiennej liniowo wysokości dla wszystkich tonów w czasie.

Po odchłuchaniu pliku wraz z analizą zobrazowanego wida można zauważyć, że:
- Częstotliwość próbkowania sygnału wynosiła 44100Hz  (0.5 * 44100 = 22050), 
  pasmo sygnału przekraczało więc w pewnych momentach połowę szybkości próbkowania - powoduje to
  nachodzenie na siebie widma sygnału w poaśmienie podstawowym oraz lustrzanego odbicia widma.
  Zachodzi zjawisko aliasingu
  

Nastepnie wczytano pliki: <br />
*Original_piano.wav* <br />
*Original_piano_sampled_at8kHz_sample1.wav* <br />
*Original_piano_sampled_at8kHz_sample2.wav* <br />

Po odłuchaniu plików można zauważyć:
- W pliku sample1 wyraźnie słychać zniekształcenia spowodowane aliasingiem, sygnałm jest próbkowany 
  ze zbyt małą częstotliwością. Na spektometrze można zauważyć przesunięcę sygnału względem sygnału oryginalnego
- Sample2 jest również próbkowany w niskiej częstotliwości jednak po zastosowaniu filtra antyaliasingowego 
  jest on tylko nieznacznie gorszej jakości od oryginału, 
  wykres spektrem w większości pokrywa się z *Original_piano.wav*.
  



***
### `Zadanie 2. Kwantyzacja`
Za pomocą programu  Sonic Visualiser wczytano plik  *quantization_sinus_mono_loweringBitDepth.wav* 
i ustawiono zalecane parametry.  <br />
*Plik dźwiękowy rozpoczyna się od sygnału skwantowanego do 16 bitów i co pewien czas rozdzielczość bitowa
jest zmniejszana o 1 bit, aż do docelowej. Następnie rozdzielczość jest ponownie zwiększana aż do 24 bitów.*

Obserwacje: <br />
Początek sygnału - kwantowanie 16 bitowe
![](./files/z2-pic1.png "Początek sygnału")
 <br />

Część sygnału gdy kwantyzacja spadła do wartości 3 bitów -. **t = 21s**
Poziom błędu kwantyzacji jest wtedy największy:

- w dziedzinie czasu widać, że sinus jest najgorzej odzorowany, wykres jest poszarpany.
W 3 bitach można maksymalnie zapisać osiem poziomów 0-7 (000-111), na przebiegu czasowym
  widać wyraźnie kolejne stopnie od zera do maksimum.
  
- W dziedzinie częstotliwości oprócz jednego piku dla sinusa pojawią coraz więcej szumu o różnych częstowliwoścach,
dla najniższego poziomu kwantyzacji szum jest największy. 
  
- Przy osłuchu pliku można zauważyć pojawiający się szum, na początku słyszymy tylko jednostajny 
dźwięk sygnału sinusoidalnego, po pewnym czasie dodatkowe dźwięki wysokiej częstotliwości, które szybko 
  narastają wraz ze mniejszaniem się ilości bitów. Dla najniższego poziomu hałas ten jest najgłośniejszy. 

![](./files/z2-pic2.png "Początek sygnału")
 <br />

Następnie wczytano plik: *Piano_16b_to_2b_to_16b_quantizer1.wav*   <br />
*Plik jest skonstruowany tak, że oryginalne nagranie partii fortepianu jest skwantowane do 16 bitów, 
następnie rozdzielczość kwantyzatora jest zmniejszana do 2 bitów i ponownie zwiększana do 16 bitów.*


- x

- x

- x





***
### `Zadanie 3. Dithering i kształtowanie szumu rekwantyzacji`


***
### `Zadanie 4. Jitter i błędy synchronizacji zegarów`

