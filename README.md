# Ekspres do Kawy – Projekt systemu czasu rzeczywistego w języku AADL

## Autorzy

- Bartosz Warchoł, bwarchol@student.agh.edu.pl
- Piotr Waluszek, waluszekp@student.agh.edu.pl

## Opis projektu

Ekspres do kawy to system czasu rzeczywistego zaprojektowany w języku AADL, którego celem jest umożliwienie użytkownikowi przygotowania różnych rodzajów kawy. System zarządza poborem wody, kawy i mleka, procesem spieniania mleka, mieleniem kawy oraz kontrolą temperatury.

## Komponenty systemu

### Pakiet

- **CoffeeMachine** – główny pakiet integrujący wszystkie komponenty systemu ekspresu do kawy.

### Data

- **Beverage** – parametry napoju: ilość kawy, wody, mleka, opcje spienienia, temperatura, moc kawy, gęstość pianki mlecznej.

    - **CoffeeType** - typ kawy (Espresso, Cappuccino, Latte, Czarna)
    - **CoffeeAmount** – ilość kawy.
    - **CoffeeStrength** – moc kawy (lekka, średnia, mocna).
    - **FoamDensity** – gęstość pianki (lekka, gęsta).

### Wątki

- **UserInterfaceControl** – Obsługuje interfejs użytkownika, umożliwiając wyświetlanie parametrów napoju oraz interakcję użytkownika z systemem.
  
- **BrewingControl** – Zarządza całym procesem parzenia kawy, uwzględniając indywidualne parametry napoju, takie jak ilość kawy, wody, mleka, siła kawy i gęstość pianki.

- **WaterPumpControl** – Odpowiada za kontrolowanie pompy wody, zapewniając odpowiednią ilość wody do procesu parzenia zgodnie z ustawieniami użytkownika.

- **CoffeeDispenserControl** – Zarządza dozownikiem kawy.

- **CoffeeGrinderControl** – Odpowiada za mielenie kawy.

- **TemperatureControl** – Kontroluje temperaturę wody.

- **MilkDispenserControl** – Zarządza dozownikiem mleka.

- **MilkFrotherControl** – Odpowiada za kontrolowanie procesu spieniania mleka.

### Procesy

- **MainProcess** – główny proces zarządzający wszystkimi wątkami i logiką ekspresu.
- **BrewingProcess** – proces zarządzający sekwencją parzenia.
- **SensorDataProcess** – proces kontrolujący dane z czujników i dbający o bezpieczeństwo całego procesu

### Urządzenia

- **WaterPump** – pompa wody.
- **MilkPump** - pompa mleka.
- **WaterHeater** – podgrzewacz wody.
- **MilkHeater** – podgrzewacz mleka.
- **CoffeeDispenser** – dozownik kawy.
- **CoffeeGrinder** - młynek do kawy.
- **MilkDispenser** – dozownik mleka.
- **MilkFrother** – spieniacz mleka.
- **TemperatureSensor** – czujnik temperatury.
- **LCDDisplay** – wyświetlacz LCD.

### Magistrale

- **DataBus** – magistrala przesyłająca dane pomiędzy komponentami.

### Procesory

- **MainController** – główny procesor sterujący ekspresu.

### Pamięć

- **SystemMemory** – pamięć operacyjna ekspresu.

### System

- **CoffeeMachineSystem** – kompletny system integrujący wszystkie komponenty.

## Funkcjonalności systemu

- **Obsługa wielu rodzajów napojów** – espresso, latte, cappuccino, oraz możliwość dostosowania siły kawy i gęstości pianki.
- **Personalizacja parametrów** – ilość wody, kawy, mleka, temperatura, opcja spienienia, siła kawy i gęstość pianki.
- **Monitorowanie** – poziom wody, poziom mleka, temperatura.
- **Wyświetlanie komunikatów** – komunikaty statusu, ostrzeżenia, przypomnienia o konserwacji.
