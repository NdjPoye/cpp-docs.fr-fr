---
title: "Repr&#233;sentation &#224; virgule flottante IEEE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "double (type de données), représentation à virgule flottante"
  - "float (mot clé)"
  - "chiffres à virgule flottante, représentation IEEE"
  - "représentation à virgule flottante IEEE"
  - "long double"
  - "réel*10 (valeur)"
  - "réel*4 (valeur)"
  - "réel*8 (valeur)"
ms.assetid: 537833e8-fe05-49fc-8169-55fd0314b195
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Repr&#233;sentation &#224; virgule flottante IEEE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Visual C\+\+ est compatible avec les standards numériques IEEE.  Il existe trois variétés de nombres réels.  Réel\*4 et réel\*8 sont utilisés dans Visual C\+\+.  Réel\*4 est déclaré à l'aide du mot **float**.  Réel\*8 est déclaré à l'aide du mot **double**.  En programmation Windows 32 bits, le type de données `long double` correspond à **double**.  Il existe, cependant, une prise en charge du langage assembleur pour les calculs utilisant le type de données réel\*10.  
  
 Les valeurs sont stockées comme suit :  
  
|Valeur|Forme de stockage|  
|------------|-----------------------|  
|réel\*4|bit de signe, exposant 8 bits, mantisse 23 bits|  
|réel\*8|bit de signe, exposant 11 bits, mantisse 52 bits|  
|réel\*10|bit de signe, exposant 15 bits, mantisse 64 bits|  
  
 Dans les formats réel\*4 et réel\*8, une valeur 1 non significative est supposée être présente dans la mantisse, mais n'est pas stockée en mémoire, de sorte que les mantisses correspondent en fait à 24 ou 53 bits, même si seuls 23 ou 52 bits sont stockés.  Le format réel\*10 stocke réellement ce bit.  
  
 Les exposants sont tronqués de la moitié de leur valeur possible.  Cela signifie que vous soustrayez cet écart de l'exposant stocké pour obtenir l'exposant réel.  Si l'exposant stocké est inférieur à la valeur de l'écart, il s'agit en fait d'un exposant négatif.  
  
 Les exposants sont tronqués comme suit :  
  
|Exposant|Tronqué de|  
|--------------|----------------|  
|8 bits \(réel\*4\)|127|  
|11 bits \(réel\*8\)|1023|  
|15 bits \(réel\*10\)|16383|  
  
 Ces exposants ne sont pas des puissances de dix, mais de deux.  Autrement dit, les exposants stockés sur 8 bits peuvent être inférieurs ou égaux à 127.  La valeur 2\*\*127 équivaut approximativement 10\*\*38, qui est la limite réelle de réel\*4.  
  
 La mantisse est stockée en tant que fraction binaire au format 1.XXX... .  Cette fraction a une valeur supérieure ou égale à 1 et inférieure à 2.  Notez que les nombres réels sont toujours stockés sous la forme normalisée, ce qui signifie que la mantisse est décalée vers la gauche de telle sorte que son bit de poids fort est toujours 1.  Étant donné que ce bit est toujours 1, il est implicite \(non stocké\) dans les formats réel\*8 et réel\*4.  La virgule binaire \(non décimale\) se trouve normalement juste à droite de la valeur 1 non significative.  
  
 Le format des différentes tailles est, donc, le suivant :  
  
|Format|OCTET 1|OCTET 2|OCTET 3|OCTET 4|...|OCTET n|  
|------------|-------------|-------------|-------------|-------------|---------|-------------|  
|réel\*4|`SXXX XXXX`|`XMMM MMMM`|`MMMM MMMM`|`MMMM MMMM`|||  
|réel\*8|`SXXX XXXX`|`XXXX MMMM`|`MMMM MMMM`|`MMMM MMMM`|...|`MMMM MMMM`|  
|réel\*10|`SXXX XXXX`|`XXXX XXXX`|`1MMM MMMM`|`MMMM MMMM`|...|`MMMM MMMM`|  
  
 `S` représente le bit de signe, les `X` correspondent aux bits de l'exposant et les `M` aux bits de la mantisse.  Notez que le bit de gauche est supposé dans les formats réel\*4 et réel\*8, mais est présent en tant que valeur "1" dans OCTET 3 du format réel\*10.  
  
 Pour décaler la virgule binaire correctement, vous devez d'abord supprimer l'écart de l'exposant, puis déplacer la virgule binaire vers la droite ou la gauche selon le nombre approprié de bits.  
  
## Exemples  
 Les exemples suivants sont en format réel\*4 :  
  
-   Dans l'exemple suivant, le bit de signe est zéro et l'exposant stocké est 128, ou 100 0000 0 en notation binaire, soit 127 plus 1.  La mantisse stockée est \(1.\) 000 0000 ... 0000 0000 ; elle possède une valeur 1 de gauche implicite et une virgule binaire, de sorte que la mantisse réelle équivaut à un.  
  
    ```  
                        SXXX XXXX XMMM MMMM ... MMMM MMMM  
    2   =  1  * 2**1  = 0100 0000 0000 0000 ... 0000 0000 = 4000 0000  
    ```  
  
-   Comme \+2 sauf que le bit de signe est défini.  Ceci est vrai pour tous les nombres à virgule flottante au standard IEEE.  
  
    ```  
    -2  = -1  * 2**1  = 1100 0000 0000 0000 ... 0000 0000 = C000 0000  
    ```  
  
-   Même mantisse, l'exposant est incrémenté d'une unité \(la valeur tronquée est 129, soit 100 0000 1 en notation binaire.\)  
  
    ```  
    4  =  1  * 2**2  = 0100 0000 1000 0000 ... 0000 0000 = 4080 0000  
    ```  
  
-   Même exposant, la mantisse est supérieure de moitié ; il s'agit de \(1.\) 100 0000 ...0000 0000, ce qui correspond à 1 1\/2 \(les valeurs des nombres fractionnaires sont 1\/2, 1\/4, 1\/8, etc.\), étant donné que c'est une fraction binaire.  
  
    ```  
    6  = 1.5 * 2**2  = 0100 0000 1100 0000 ... 0000 0000 = 40C0 0000  
    ```  
  
-   Même exposant que d'autres puissances de deux, la mantisse est inférieure d'une unité à deux \(127\), soit 011 1111 1 en représentation binaire.  
  
    ```  
    1  = 1   * 2**0  = 0011 1111 1000 0000 ... 0000 0000 = 3F80 0000  
    ```  
  
-   L'exposant biaisé équivaut à 126, soit 011 1111 0 en représentation binaire, et la mantisse correspond à \(1.\) 100 0000 ... 0000 0000, ce qui donne 1 1\/2.  
  
    ```  
    .75 = 1.5 * 2**-1 = 0011 1111 0100 0000 ... 0000 0000 = 3F40 0000  
    ```  
  
-   Exactement identique à deux sauf que le bit qui représente 1\/4 est défini dans la mantisse.  
  
    ```  
    2.5 = 1.25 * 2**1 = 0100 0000 0010 0000 ... 0000 0000 = 4020 0000  
    ```  
  
-   1\/10 est une fraction itérative en binaire.  La mantisse est juste en deçà de 1.6, et l'exposant tronqué indique que la valeur 1.6 doit être divisée par 16 \(il s'agit de 011 1101 1 en binaire, soit 123 en représentation décimale\).  L'exposant réel est 123 – 127 \= –4, ce qui signifie que le facteur de multiplication est 2\*\*–4 \= 1\/16.  Notez que la mantisse stockée est arrondie dans le dernier bit \(tentative de représentation du nombre non représentable avec une précision optimale\). \(La raison pour laquelle 1\/10 et 1\/100 ne peuvent pas être représentés exactement en notation binaire est similaire à la raison qui fait que 1\/3 n'est pas représentable exactement en notation décimale.\)  
  
    ```  
    0.1 = 1.6 * 2**-4 = 0011 1101 1100 1100 ... 1100 1101 = 3DCC CCCD  
    ```  
  
-   `0  = 1.0 * 2**-128 = all zeros--a special case.`  
  
## Voir aussi  
 [Pourquoi les nombres à virgule flottante peuvent manquer de précision](../../build/reference/why-floating-point-numbers-may-lose-precision.md)