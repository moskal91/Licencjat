# Gra Multiplayer RPG - The Last Trinity
Autorzy: Adrian Podlawski, Mateusz Kleina rok 2017

## Słowa kluczowe
Unity, Game, Multiplayer, Cooperation, Adventure, RPG, C#, Unity, Photon, PUN

## Streszczenie 
Zaimplementowaliśmy wieloosobową grę w wersji Beta, która bazuje na silniku graficznym Unity. Tryb multiplayer zbudowaliśmy na podstawie frameworka Photon Unity 3D Networking, który został pobrany ze sklepu Asset Store, a następnie zmodyfikowany i zaprogramowany zgodnie z wymaganiami gry.
   
Scenę po której poruszają się postaci utworzyliśmy dzięki silnikowi gry Unity. Krajobrazy oraz budynki zostały pobrane z Assets Store, a następnie zmodyfikowane.
    
Wszystkie skrypty odpowiadające za sterowanie postaci, łączenie z serwerem, czy walkę z przeciwnikiem, zostały utworzone przez nas w języku programowania C Sharp.
    
Postaci oraz ich animacje zostały utworzone przy pomocy storny Mixamo.com, a następnie odpowiednio zaimplementowane przy pomocny skryptów.
    
W trakcie rozwijania aplikacji, pliki były przechowywane we wspólnym repozytorium na stronie Github.com. Zbudowana wersja gry znajduje się na repozytorium Git.Projekt był testowany manualnie poprzez sterowanie postaciami oraz przy użyciu logów przesyłanych do silnika Unity.Za środowisko testowe posłużył nam osobny serwer, który nie miał wpływu na wydaną wersję projektu, znajdującą się na repozytorium.


## Spis treści 
1. Wstęp i opis
    - Porównanie dostępnych rozwiązań,
        - World of Warcraft,
        - Diablo 3
      
1. Projektowanie oraz przygotowanie środowiska
    - Projekt Terenu,
    - Projekt Postaci sterowanych przez gracza,
    - Projekt systemu mulitplayer
    - Instalacja niezbędnych narzędzi
   
1. Implementacja
    - Budowa terenu
    - Tworzenie Postaci
    - Ruch kamery
    - Fizyka
    - Animacje
    - Poruszanie bohaterów
    - Poruszanie postaci wrogów
    - Umiejętności bohaterów
    - Multiplayer

1. Bibliografia
    - Książki,
    - Artykuły dostępne w Internecie,
    - Poradniki dostępne na YouTube

## Wstęp
Podczas minionych semestrów na uczelni poznaliśmy wiele nowych technologii, Framework-ów oraz języków programowania. Mieliśmy do czynienia z wieloma ich odmianami, poznaliśmy ich różne zastosowania. Niektóre z nich służyły nam do pisania prostych programów tekstowych, które korzystały tylko i wyłącznie z wiersza poleceń. Z drugiej strony były też obszerne aplikacje, połączone z bazą danych oraz utworzone według wzorców projektowych przy użyciu  języków programowania takich jak Ruby, czy Java. 

Chcąc rozwijać swoją wiedzę oraz poszerzać swoje umiejętności, jako programiści postanowiliśmy napisać nasz projekt w języku programowania, z którym nie mieliśmy styczności na uczelni. Uważaliśmy, że będzie to dla nas dobra okazja do sprawdzenia tego, czego do tej pory się nauczyliśmy, gdyż nauka programowania, to nie tylko nauka składni danego języka. W wielu przypadkach to głównie nauka logicznego myślenia, wiązania ze sobą faktów, szukania oraz korygowania własnych błędów i wyciągania z nich wniosków. 

Szukaliśmy języka programowania, który jest wszechstronny i może być wykorzystany w różnych projektach min. przy budowaniu dużych stron internetowych, gier, serwisów. Po namyśle zdecydowaliśmy się na język C Sharp. Jest on zorientowany obiektowo, dzięki temu mogliśmy wykorzystać nasze doświadczenie min. z języka Java.  Ma on bardzo szerokie zastosowanie, może być wykorzystany do tworzenia aplikacji desktopowych, Windows Service, dzięki niemu możemy również tworzyć rozbudowane strony internetowe przy użyciu technologii ASP.NET opartej na .NET Framework. Wybierając jednak nowy język programowania, chcieliśmy również skorzystać z technologii, która umożliwi nam przetestowanie naszych umiejętności zupełnie na innej płaszczyźnie.

Aktualnie na świecie miliony osób grają w gry przeróżnego typu, a my należymy do tej bardzo licznej społeczności. Do tej pory jednak nie mieliśmy przed sobą zadania, by stworzyć jedną z nich od podstaw. Chcieliśmy podjąć się tego wyzwania i za silnik graficzny obraliśmy Unity, który współgra z językiem C Sharp, a do tego obsługuje aż 22 platformy sprzętowe i co raz częściej wykorzystywany jest również w przeglądarkach internetowych oraz wirtualnej rzeczywistości.Wiedzieliśmy, że będzie do dla nas wyzwanie, ale zarazem wielki krok w początkach naszej kariery, jako młodych programistów.

Unity daje możliwość tworzenia gry bez wdrażania się w szczegóły techniczne dotyczące renderowania obrazu i obsługi różnych kart graficznych, obliczania skomplikowanych równań fizycznych czy korzystania z protokołów sieciowych. Tworzenie gier nie wymaga już niskopoziomowego kodu, stało się przyjaźniejsze i bardziej dostępne dla programistów chcących skupić się na samej mechanice gry.

Skłoniło nas to do stworzenia nieco odmiennego projektu, w którym rozgrywka polega na wspólnym pokonywaniu przeszkód i odkrywaniu dalszego ciągu tej samej historii, a gracze zamknięci zostają we wspólnej ramie czasowej. Dotąd gry tego typu występowały głównie w postaci gier jednoosobowych, takich jak Far Cry, Tomb Raider, czy Grand Theft Auto.

W odróżnieniu od innych gier wieloosobowych takich jak np. Diablo 3, gdzie całą fabułę możemy ukończyć sami, w The Last Trinity położyliśmy główny nacisk na współpracę. Do ukończenia rozgrywki niezbędne są wszystkie postaci, które sterowane są przez różnych graczy.

Aktualnie gry Multiplayer opierają się głównie na mechanice zbierania co raz lepszego ekwipunku, jak np. w World of Warcraft. Często doprowadza to również do wielu konfliktów pomiędzy graczami. W naszej stawiamy na wspólną zabawę, nie będzie w niej ciągłego zbierania ekwipunku, a jedynie pokonywanie rozmaitych i bardziej skomplikowanych przeszkód razem ze swoją drużyną.

Początkowym założeniem naszej pracy było utworzenie gry wieloosobowej, której świat jednocześnie będzie mogła eksplorować trójka graczy. Każdy z nich sterowałby inną, unikatową postacią. 
Gra miała posiadać przykładowe misje oraz stanowić fundament do dalszego jej rozwoju na tle fabularnym. Wszystkie powyższe założenia udało nam się zrealizować. 



## Bibliografia
- [Photon Documentation](https://doc-api.photonengine.com/en/pun/current/)
- [Unity Documentation](https://docs.unity3d.com/Manual/index.html)
- [C# Documentation](https://msdn.microsoft.com/en-us/library/67ef8sbd.aspx)
- [Stack Overflow](https://stackoverflow.com/)
