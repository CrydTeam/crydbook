# Klipper Vorzeichen

pin: PA1&#x20;

pin: !PA1 (negiert)&#x20;

pin: ^PA1 (pullup)&#x20;

pin: \~PA1 (pulldown)



## Allgemein

Ein Pullup- oder Pulldown-Widerstand wird dazu verwendet, einen Eingang auf einen definierten Wert zu "ziehen". Normalerweise befindet sich der Eingang im Zustand "schwebend/hochohmig", welcher sich irgendwo zwischen High und Low befindet. Nun sind Schaltungen leider nicht komplett ohne Störsignale, und durch Einstrahlungen von Signalen kann es nun passieren, dass kurzzeitig mal ein Wert über- oder unterschritten wird und der Eingang plötzlich ein High- oder Lowsignal bekommt. Dies führt dann zu unerklärlichen und unregelmäßig auftretenden Fehlern, die einen Neuling zur Verzweiflung treiben können.



## Pullup-Widerstand

Um dies zu vermeiden wird, während nichts am Eingang passiert, dieser auf High gezogen (pullup). Will man also einen Taster haben, der Low schaltet, so will man für den Rest der Zeit High am Eingang liegen haben. Dies kann man erreichen, indem man den Eingang fest mit VCC verbindet. Vom Eingang geht nun eine Leitung nach VCC und eine über den Taster nach GND. Leider würde dies zu einem Kurzschluss führen sobald man den Taster drückt und die Schaltung könnte (und würde höchstwahrscheinlich) Schaden nehmen. Deshalb wird nun zwischen VCC und dem Eingang ein hochohmiger Widerstand eingesetzt, der Pullup-Widerstand. Bei geschlossenem Taster wird nun der Strom über den Pullup-Widerstand nach GND fließen und der Input liegt auf GND (0V).

<figure><img src="https://rn-wissen.de/wiki/images/4/40/Pullup.gif" alt=""><figcaption></figcaption></figure>

## Pulldown-Widerstand

Der Pulldown-Widerstand funktioniert analog zum Pullup-Widerstand, nur dass nun VCC geschaltet werden soll und somit der Eingang auf GND gezogen werden muss. Dies geschieht in gleicher Weise wie beim Pullup, nur dass der Pulldown-Widerstand nun zwischen GND und dem Eingang platziert wird. Schließt man nun wieder den Taster, liegt am Eingang Vcc an --> High.\


<figure><img src="https://rn-wissen.de/wiki/images/7/79/Pulldown.gif" alt=""><figcaption></figcaption></figure>

[Quelle](https://rn-wissen.de/wiki/index.php/Pullup\_Pulldown\_Widerstand)
