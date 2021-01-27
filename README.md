# PNoD_rozpoznawanie_obrazów
# Introduction
Problemem, którym zajmujemy się w liście 4 jest rozpoznawanie ubrań z pewnego zbioru zawierającego zdj, na których znajdują się różne rodzaje ubrań. 
Rodaje te możemy wyszczególnić w klasie: class_clothes = ['T-shirt/top', 'Trouser', 'Pullover', 'Dress', 'Coat', 'Sandal', 'Shirt', 'Sneaker', 'Bag', 'Ankle boot'].
Naszym zadaniem jest swtorzenie modelu uczącego się z jak największą dokładnością. Aby wykonać to zadanie rozdzieliłam je na pod zadania do zrealizowania.
Zadania:
1. Przetworzenie danych
2. Zbudowanie modelu 
3. Trenowanie modelu
4. Karmienie Modelu
5. Ocena dokładności
6. Prognozowanie 
7. Weryfikacja na danych walidacyjnych
8. Wykorzystanie na danych testowych 
# Methods
Metody które wykorzystałam do realizacji powyższych zadań wykorzystują biblioteke: scikit-learn. Jako metode Klasyfkacji modelu wykorzytsała funckję KNeighborsClassifier która jako argumenty przyjmuje ilość sąsiadów: 1, 5 lub 9 oraz rodzaj algorytmu wyszukiwania najblizszych sąsiadów - Ball Tree - wykorzystująca drzewo binarne.
Do trenowania modelu wykorzystuje funkcje fit (model.fit(x,y)), która trenuje mój model.
Do prognozowania wykorzystuję funkcję predict(X). A do testowania funkcję od predict_proba(X_test) - prognozuje ona wyniki dla grupy testowej.
	
# Results
Jeżeli chodzi o rezultaty metody kNN to są one zbliżone do tych przedstawionych w bazie danych: http://fashion-mnist.s3-website.eu-central-1.amazonaws.com/. Aby je porównać jako argumenty wybrałam ocene dokładności oraz czas wykonywania się algorytmu. Ostatni z nich nie jest dokońca argumentem niezależnym ponieważ pracowałam na środowisku Colab, co miało duży wpływ na czas i możliwości wykonywania się algorytmu. Dla porównania wyniki przedstawione na pierwszym obrazie są z bazy danych, mozemy zauważyć, że dokładnością dla modelu z jednym sąsiadem wynosi 0.847, dla 9 sąsiadów 0,856 i dla 6 sąsiadów - 0,86. Jak widzimy dokładność rośnie do n =5 natomist później już dokładność spada dla większej ilości sąsiadów. Czas dla k=1 - 0:40:45, czas dla k=2 - 0:41:19 oraz czas dla k=9 - 	0:41:53.

natomiast 3 poniższe przedstawiają wyniki otrzymane przez algorytm, który napisałam z wykorzystaniem biblioteki scikit-learn:
dla k = 1 acc = 0.849 
(Dla pierwszego przypadku nie liczyłam czsu poniewaź rozbiłam ten przykład w komórkach i musiałabym doliczyć czas, który zajeło by przejście - odpalenie jednej komórki po końcu drugiej.)
dla k = 5
TRAINING ACCURACY for n=5: 0.89405
time:58.80702748333335 [min] - 0:58:81
dla k = 9
TRAINING ACCURACY for n = 9: 0.873575
time:70.40844191666666 [min] - 1:10:41

# Usage 
Napisany przeze mnie program można uruchomić dwiema metodami.
Metoda 1 - prostsza, sugerowana
Odpalić program za pomocą narzędzi oferowanych od Google - Colaboratory (Colab) - umożliwia ono pisanie i uruchamianie kodu w pythonie bezpośrenio w przeglądarce. 
Aby uruchomić program w Colabie należy wejść w zakladkę środowisko wykonawcze i wybać opcje uruchom wszystko. Po uruchomieniu każda komórka po kolei będzie uruchamiana i pod sobą wyświetlać wykonane działania. Nie ma potrzeby pobierania bibliotek ani plików, które pobiorą się automatycznie za pomocą biblioteki requests z pliku z githuba.
Metoda 2 - trudniejsza
Należy pobrać zaimplementowany kod z zadania :  oraz plik requirements.txt - zawierający potrzebne bilioteki.
Aby zainstalować potrzebne biblioteki należy wypisać komendę do terminala: pip install -r requirements.txt.
Po instalacji można uruchomić program.
