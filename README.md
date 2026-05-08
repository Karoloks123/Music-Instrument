# Instrument muzyczny
Projekt instrumentu muzycznego oparty o syntezę DDS (Direct Digital Synthesis) z wykorzystaniem mikrokontrolera FRDM-KL05Z oraz przetwornika DAC.

# Opis projektu
Instrument umożliwia generowanie dźwięków o zadanych częstotliwościach poprzez sterowanie akumulatorem fazy oraz odtwarzanie próbek zapisanych w tablicach przebiegów.

**Funkcjonalności:**
+ 13 klawiszy odpowiadających nutom:
+ C, C#, D, D#, E, F, F#, G, G#, A, A#, B, C1
+ zmiana oktawy (+ / -)
+ zmiana kształtu przebiegu:
  - sinus
  - trójkąt
  - piła
+ regulacja głośności przy użyciu pola dotykowego
+ wyświetlanie aktualnych informacji na LCD

**Wykorzystany sprzęt:**
- płytka FRDM-KL05Z
- LCD1602A
- klawiatura matrycowa 4x4
- głośnik WaveShare
- pole dotykowe TSI
- DAC mikrokontrolera

# Zasada działania
Sygnał audio generowany jest metodą DDS:
1. Timer PIT wywołuje przerwanie.
2. W przerwaniu inkrementowany jest akumulator fazy.
3. Na podstawie jego wartości wybierana jest próbka z tablicy przebiegu.
4. Próbka wysyłana jest do przetwornika DAC.
5. DAC generuje sygnał audio na wyjściu głośnika.

# Ograniczenia projektu
Ze względów na ogarniczenia sprzętowe wykorzystywanej płytki rozwojowej program ma kilka głównych problemów:
- ograniczona liczba próbek DDS
- ograniczona częstotliwość próbkowania
- ograniczona liczba dostępnych oktaw

# Instrukcja użytkowania
Po podłączeniu zasilania użytkownik ma do dyspozycji 16 klawiszy funkcyjnych. Klawisze S1 – S13 są klawiszami odpowiedzialnymi za konkretne dźwięki (idące w kolejności zgodnej z normami, tj. C, C#, D, D#, E, F, F#, G, G#, A, A#, B, C1) – grana nuta zostanie wyświetlona na wyświetlaczu. Klawisz S14 pozwala na zwiększenie oktawy nut o jeden, a klawisz S15 o jej zmniejszenie (do dyspozycji są tylko 3 oktawy). Ostatni przycisk S16 pozwala na sekwencyjny wybór jaki kształt ma mieć fala, której dźwięk będzie grany. Do wyboru jest po kolei: sinus, trójkąt, piła. W celu zmiany głośności należy wykorzystać znajdujący się na płytce czujnik dotykowy. Pozwala on na dostosowanie odpowiednio poziomu głośności dźwięków, bez potrzeby wykorzystywania potencjometru głośnika. Aktualny wybór/poziom głośności jest prezentowany na wyświetlaczu.
