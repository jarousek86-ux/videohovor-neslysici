# Videohovor pro neslyšící

Prototyp webové aplikace pro videohovor dvou osob s textovým chatem. Cílem je podpořit vizuální komunikaci, odezírání a znakový jazyk.

**Stav: rozpracovaný prototyp.** Funkčnost hovoru na různých zařízeních a sítích je potřeba dále ověřit.

## Co obsahuje současná implementace

- Vytvoření místnosti a sdílení jejího kódu.
- Připojení druhé osoby pomocí kódu.
- Video druhé osoby a vlastní náhled.
- Textový chat, indikátor psaní a vizuální upozornění na zprávu.
- Ovládání mikrofonu, kamery a ukončení hovoru.
- Rozložení pro počítač i mobil.

## Technologie

HTML, CSS a JavaScript v souboru `index.html`. Pro spojení aplikace používá PeerJS 1.5.2 načítaný z cdnjs a WebRTC v prohlížeči. Nemá sestavovací krok ani npm závislosti.

## Spuštění na počítači

Potřebuješ Git a Python 3, případně jiný místní HTTP server.

```bash
git clone https://github.com/jarousek86-ux/videohovor-neslysici.git
cd videohovor-neslysici
python3 -m http.server 8000 --bind 127.0.0.1
```

Otevři [http://localhost:8000](http://localhost:8000). Server ukončíš klávesami Ctrl+C.

Pro nasazení mimo vlastní počítač použij HTTPS kvůli přístupu ke kameře a mikrofonu. Aplikace potřebuje připojení k internetu pro načtení PeerJS a navázání spojení.

## Jak vyzkoušet hovor

1. Obě osoby otevřou aplikaci.
2. První osoba zadá jméno, vytvoří místnost a předá její kód druhé osobě.
3. Druhá osoba zadá jméno a kód místnosti a zvolí **Připojit se**.
4. Obě osoby povolí kameru a mikrofon, pokud chtějí pokračovat.
5. Během hovoru mohou používat textový chat a ovládací tlačítka.

## Současná omezení

- Implementace žádá o kameru i mikrofon; samostatný režim pouze pro textový chat zatím není připraven.
- Chybí ověření identity účastníků a samostatné potvrzení příchozího hovoru. Kód místnosti sdílej jen se zamýšleným účastníkem.
- Používá se výchozí konfigurace PeerJS bez vlastního nastavení signalizačního a TURN serveru; spojení není zaručeno ve všech sítích.
- Neobsahuje automatický přepis řeči, překlad znakového jazyka ani funkci nahrávání.
- Projekt zatím nemá automatické testy ani doloženou matici podporovaných prohlížečů.

## Další rozvoj

- Ověřit spojení mezi dvěma zařízeními a různými sítěmi.
- Zlepšit zpracování odmítnutých oprávnění a přerušení spojení.
- Doplnit potvrzení příchozího hovoru a možnost komunikace bez mikrofonu.
- Ověřit mobilní chat, přístupnost ovládání a úplné ukončení přenosu.

## Autor

[Jaroslav Klein](https://github.com/jarousek86-ux)
