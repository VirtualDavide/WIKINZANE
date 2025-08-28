2025-03-26 16:42

Tags : [[PHP]]

# Programmazione Orientata agli Oggetti in PHP


PHP supporta la programmazione orientata agli oggetti (OOP) e offre una serie di funzionalità che consentono di utilizzare questo paradigma in modo efficace. Ecco una panoramica su come la programmazione orientata agli oggetti è inclusa in PHP, con un focus su classi, oggetti, incapsulamento, ereditarietà, polimorfismo, interfacce, classi astratte e trait.

#### 1. Classi e Oggetti

In PHP, una **classe** è un modello che definisce le proprietà e i metodi di un oggetto. Un **oggetto** è un'istanza di una classe. Le classi possono contenere variabili (note come **proprietà**) e funzioni (note come **metodi**).

**Esempio di classe e oggetto:**
```php
class Auto {
    public $marca;
    public $modello;

    public function accendi() {
        return "L'auto è accesa.";
    }
}

// Creazione di un oggetto
$miaAuto = new Auto();
$miaAuto->marca = "Fiat";
$miaAuto->modello = "Panda";

echo $miaAuto->accendi(); // Output: L'auto è accesa.
```

#### 2. Incapsulamento

L'incapsulamento è un principio fondamentale della OOP che consiste nel nascondere i dettagli interni di un oggetto e fornire un'interfaccia pubblica per interagire con esso. In PHP, puoi utilizzare le visibilità `public`, `protected` e `private` per controllare l'accesso alle proprietà e ai metodi.

**Esempio di incapsulamento:**
```php
class ContoBancario {
    private $saldo;

    public function __construct($saldoIniziale) {
        $this->saldo = $saldoIniziale;
    }

    public function deposita($importo) {
        $this->saldo += $importo;
    }

    public function preleva($importo) {
        if ($importo <= $this->saldo) {
            $this->saldo -= $importo;
        } else {
            return "Fondi insufficienti.";
        }
    }

    public function getSaldo() {
        return $this->saldo;
    }
}

$conto = new ContoBancario(100);
$conto->deposita(50);
echo $conto->getSaldo(); // Output: 150
```

#### 3. Ereditarietà

L'ereditarietà consente di creare una nuova classe (classe figlia) basata su una classe esistente (classe genitore). La classe figlia eredita le proprietà e i metodi della classe genitore, consentendo il riutilizzo del codice.

**Esempio di ereditarietà:**
```php
class Veicolo {
    public function muovi() {
        return "Il veicolo si muove.";
    }
}

class Moto extends Veicolo {
    public function frena() {
        return "La moto frena.";
    }
}

$moto = new Moto();
echo $moto->muovi(); // Output: Il veicolo si muove.
echo $moto->frena(); // Output: La moto frena.
```

#### 4. Polimorfismo

Il polimorfismo consente di utilizzare metodi con lo stesso nome in classi diverse, ma con comportamenti diversi. In PHP, puoi implementare il polimorfismo tramite l'override dei metodi.

**Esempio di polimorfismo:**
```php
class Animale {
    public function verso() {
        return "Verso generico.";
    }
}

class Cane extends Animale {
    public function verso() {
        return "Bau!";
    }
}

class Gatto extends Animale {
    public function verso() {
        return "Miao!";
    }
}

$animali = array(new Cane(), new Gatto());

foreach ($animali as $animale) {
    echo $animale->verso(); // Output: Bau! Miao!
}
```

#### 5. Interfacce e Classi Astratte

PHP supporta anche le interfacce e le classi astratte, che consentono di definire contratti per le classi. Le interfacce definiscono metodi che devono essere implementati dalle classi che le utilizzano, mentre le classi astratte possono contenere sia metodi astratti (senza implementazione) che metodi concreti.

**Esempio di interfaccia:**
```php
interface Veicolo {
    public function muovi();
}

class Bicicletta implements Veicolo {
    public function muovi() {
        return "La bicicletta si muove.";
    }
}

class Auto implements Veicolo {
    public function muovi() {
        return "L'auto si muove.";
    }
}

$veicoli = array(new Bicicletta(), new Auto());

foreach ($veicoli as $veicolo) {
    echo $veicolo->muovi() . "\n"; // Output: La bicicletta si muove. L'auto si muove.
}
```

Le interfacce sono utili per garantire che le classi implementino determinati metodi, fornendo così un contratto che le classi devono rispettare.

**Esempio di classe astratta:**
```php
abstract class Animale {
    abstract public function verso();

    public function descrizione() {
        return "Questo è un animale.";
    }
}

class Cane extends Animale {
    public function verso() {
        return "Bau!";
    }
}

class Gatto extends Animale {
    public function verso() {
        return "Miao!";
    }
}

$cane = new Cane();
echo $cane->verso(); // Output: Bau!
echo $cane->descrizione(); // Output: Questo è un animale.
```

Le classi astratte non possono essere istanziate direttamente e possono contenere sia metodi astratti che metodi concreti.

### 6. Trait

I **trait** sono un meccanismo in PHP che consente di riutilizzare il codice in più classi. A differenza dell'ereditarietà, che consente di estendere solo una classe genitore, i trait permettono di includere metodi e proprietà in diverse classi senza dover utilizzare l'ereditarietà multipla.

I trait sono particolarmente utili per condividere funzionalità comuni tra classi diverse.

**Esempio di trait:**
```php
trait Luci {
    public function accendiLuci() {
        return "Luci accese.";
    }

    public function spegniLuci() {
        return "Luci spente.";
    }
}

class Auto {
    use Luci;

    public function muovi() {
        return "L'auto si muove.";
    }
}

class Moto {
    use Luci;

    public function muovi() {
        return "La moto si muove.";
    }
}

$auto = new Auto();
echo $auto->accendiLuci(); // Output: Luci accese.
echo $auto->muovi(); // Output: L'auto si muove.

$moto = new Moto();
echo $moto->spegniLuci(); // Output: Luci spente.
echo $moto->muovi(); // Output: La moto si muove.
```

In questo esempio, il trait `Luci` è utilizzato sia dalla classe `Auto` che dalla classe `Moto`, consentendo a entrambe le classi di accedere ai metodi `accendiLuci` e `spegniLuci`.

### Conclusione

La programmazione orientata agli oggetti in PHP consente di scrivere codice più modulare, riutilizzabile e manutenibile. Utilizzando classi, oggetti, incapsulamento, ereditarietà, polimorfismo, interfacce, classi astratte e trait, gli sviluppatori possono creare applicazioni complesse in modo più organizzato e strutturato. Queste caratteristiche rendono PHP un linguaggio potente e flessibile per lo sviluppo di applicazioni web.

Se hai ulteriori domande o desideri approfondire qualche argomento specifico, non esitare a chiedere!

## References

- [[I costrutti di programmazione di PHP]]
- [[Strutture Dati php]]