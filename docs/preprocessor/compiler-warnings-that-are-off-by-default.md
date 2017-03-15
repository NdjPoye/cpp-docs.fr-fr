---
title: "Avertissements du compilateur d&#233;sactiv&#233;s par d&#233;faut | Microsoft Docs"
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
  - "compilateur cl.exe, définir des options"
  - "avertissements, compilateur"
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
caps.latest.revision: 39
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 37
---
# Avertissements du compilateur d&#233;sactiv&#233;s par d&#233;faut
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le compilateur contient des avertissements qui sont désactivés par défaut, car la plupart des utilisateurs ne souhaitent pas les voir.  Toutefois, vous pouvez les activer à l'aide de l'une des options suivantes.  
  
 `#pragma warning(default :`  `warning_number` `)`  
 L'avertissement spécifié \(`warning_number`\) est activé à son niveau par défaut.  La documentation de l'avertissement contient le niveau par défaut de l'avertissement.  
  
 `#pragma warning(` `warning_level`  `:`  `warning_number` `)`  
 L'avertissement spécifié \(`warning_number`\) est activé au niveau spécifié \(`warning_level`\).  
  
 [\/Wall](../build/reference/compiler-option-warning-level.md)  
 **\/Wall** active tous les avertissements qui sont désactivés par défaut.  
  
 Les avertissements suivants sont désactivés par défaut.  
  
|||  
|-|-|  
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) \(niveau 4\)|l'énumérateur 'identificateur' dans un switch de l'enum 'énumération' n'est pas géré explicitement par une étiquette case|  
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) \(niveau 3\)|l'énumérateur 'identificateur' dans un switch de l'enum 'énumération' n'est pas géré|  
|C4191 \(niveau 3\)|'opérateur\/opération' : conversion potentiellement dangereuse de 'type d'expression' à 'type requis'|  
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) \(niveau 4\)|'identificateur' : conversion de 'type1' en 'type2', perte possible de données|  
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) \(niveau 4\)|'opérateur' : conversion de 'type1' en 'type2', perte possible de données|  
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) \(niveau 4\)|'fonction' : aucun prototype de fonction fourni : conversion de '\(\)' en '\(void\)'|  
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) \(niveau 4\)|'fonction' : une fonction membre ne se substitue à aucune fonction membre virtuelle de classe de base|  
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) \(niveau 1\)|'fonction\_virtuelle' : aucune substitution disponible pour la fonction membre virtuelle à partir de la base 'classe' ; la fonction est masquée|  
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) \(niveau 3\)|'classe' : la classe possède des fonctions virtuelles, mais le destructeur n'est pas virtuel|  
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) \(niveau 4\)|'fonction' : aucune substitution disponible pour la fonction membre virtuelle à partir de 'type' de base ; la fonction est masquée|  
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) \(niveau 3\)|'opérateur' : constantes non signées\/négatives incompatibles|  
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) \(niveau 4\)|extension non standard utilisée : 'var' : variable de contrôle de boucle déclarée dans la boucle for utilisée à l'extérieur de la portée de la boucle|  
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) \(niveau 4\)|'opérateur' : l'expression est toujours false|  
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) \(niveau 2\)|'conversion' : troncation de 'type1' à 'type2'|  
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) \(niveau 1\)|'variable' : troncation de pointeur de 'type' à 'type'|  
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) \(niveau 1\)|'opération' : la conversion de 'type1' en 'type2' d'une taille supérieure|  
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) \(niveau 4\)|'type' : utilisation de ce type non défini dans les métadonnées CLR, ce qui peut provoquer une exception runtime|  
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) \(niveau 1\)|modification de comportement : 'fonction' appelé, mais un opérateur de membre a été appelé dans les versions précédentes|  
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) \(niveau 1\)|changement de comportement : 'membre1' appelé à la place de 'membre2'|  
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : utilisé dans la liste des initialiseurs membre de base|  
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) \(niveau 4\)|'action' : conversion de 'type\_1' en 'type\_2', incompatibilité signed\/unsigned|  
|C4370 \(niveau 3\)|la disposition de classe a été modifiée à partir d'une version précédente du compilateur en raison d'une meilleure compression|  
|C4371 \(niveau 3\)|la disposition de classe peut avoir été modifiée à partir d'une version précédente du compilateur en raison d'une meilleure compression du membre 'member'|  
|C4388 \(niveau 4\)|incompatibilité signed\/unsigned|  
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) \(niveau 2\)|'fonction' : la signature de fonction contient le type 'type' ; le passage d'objets C\+\+ n'est pas sécurisé entre le code pure et le code mixte ou natif.|  
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) \(niveau 4\)|spécificateur de type manquant \- int est pris en compte par défaut.  Remarque : C ne prend plus en charge int par défaut|  
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) \(niveau 4\)|'classe1' : la disposition des objets sous \/vd2 sera modifiée en raison de la base virtuelle 'classe2'|  
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) \(niveau 4\)|le dynamic\_cast de la base virtuelle 'classe1' en 'classe2' risque d'échouer dans certains contextes|  
|C4444 \(niveau 3\)|'\_\_unaligned' de niveau supérieur n'est pas implémenté dans ce contexte|  
|C4471 \(niveau 4\)|une déclaration anticipée d'une énumération non délimitée doit avoir un type sous\-jacent \(int pris par défaut\)|  
|C4472 \(niveau 1\)|'identifier' est un enum natif : ajoutez un spécificateur d'accès \(private\/public\) pour déclarer un enum géré|  
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) \(niveau 4\)|'fonction' : la fonction inline non référencée a été supprimée|  
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) \(niveau 4\)|'nom de type' : le nom de type dépasse la limite métadonnées de 'limite' caractères|  
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) \(niveau 1\)|l'expression avant la virgule correspond à une fonction qui n'a pas de liste d'arguments|  
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) \(niveau 1\)|l'appel de fonction avant la virgule n'a pas de liste d'arguments|  
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) \(niveau 1\)|'opérateur' : l'opérateur avant la virgule n'a pas d'effet ; opérateur avec effet secondaire attendu|  
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) \(niveau 1\)|l'expression avant la virgule n'a pas d'effet ; expression avec effet secondaire attendu|  
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) \(niveau 1\)|'opérateur' : l'opérateur avant la virgule n'a pas d'effet ; souhaitez\-vous utiliser 'opérateur' ?|  
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) \(niveau 1\)|l'expression n'a pas d'effet ; attendue expression avec effets secondaires|  
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) \(niveau 3\)|'\_\_assume' contient l'effet 'effet'|  
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) \(niveau 4\)|informations : la sémantique catch\(...\) a changé depuis Visual C\+\+ 7.1 ; les exceptions structurées \(SEH\) ne sont plus interceptées|  
|C4574 \(niveau 4\)|'identifier' est défini comme étant '0' : voulez\-vous utiliser 'identifier \#if' ?|  
|C4608 \(niveau 3\)|'symbol1' a déjà été initialisé par un autre membre union dans la liste des initialiseurs, 'symbol2'|  
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) \(niveau 3\)|\#pragma warning : numéro d'avertissement inexistant 'numéro'|  
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) \(niveau 4\)|'classe dérivée' : le constructeur par défaut n'a pas pu être généré parce que le constructeur par défaut de la classe de base est inaccessible|  
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) \(niveau 4\)|'classe dérivée' : le constructeur de copie n'a pas pu être généré parce qu'un constructeur de copie de la classe de base est inaccessible|  
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) \(niveau 4\)|'classe dérivée' : l'opérateur d'assignation n'a pas pu être généré parce qu'un opérateur d'assignation de la classe de base est inaccessible|  
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) \(niveau 1\)|digrammes non pris en charge avec \-Ze.  Séquence de caractères 'digramme' non interprétée comme jeton de remplacement pour 'car'|  
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) \(niveau 3\)|'instance' : la construction d'un objet static local n'est pas thread\-safe|  
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) \(niveau 4\)|'symbole' non défini comme préprocesseur ou macro, remplacement par '0' pour 'directives'|  
|C4682 \(niveau 4\)|'symbol' : aucun attribut de paramètre directionnel spécifié, \[in\] pris par défaut|  
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) \(niveau 3\)|'type défini par l'utilisateur' : changement de comportement possible, changement de la convention d'appel de retour UDT|  
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) \(niveau 1\)|'fonction' : la signature de membre non privée contient un type natif privé d'assembly 'type\_natif'|  
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) \(niveau 4\)|'fonction' : fonction non inline|  
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) \(niveau 3\)|stockage de résultat flottant 32 bits en mémoire, perte possible de performances|  
|C4767 \(niveau 4\)|le nom de section 'symbol' comporte plus de 8 caractères et sera tronqué par l'éditeur de liens|  
|C4786 \(niveau 3\)|'symbol' : nom d'objet tronqué à 'nombre' caractères dans les informations de débogage|  
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) \(niveau 4\)|'octets' octets de remplissage ajoutés après construction 'nom\_membre'|  
|[C4826](../error-messages/compiler-warnings/compiler-warning-level-2-c4826.md) \(niveau 2\)|la conversion de 'type1' en 'type2' est de type signe étendu.  Cela peut provoquer un comportement inattendu au moment de l'exécution|  
|[C4837](../error-messages/compiler-warnings/compiler-warning-level-4-c4837.md) \(niveau 4\)|trigraphe détecté : '??%c' remplacé par '%c'|  
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) \(niveau 1\)|cast de littéral de chaîne étendu en 'LPSTR'|  
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) \(niveau 1\)|cast de littéral de chaîne en 'LPWSTR'|  
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) \(niveau 1\)|'déclarateur' : un GUID ne peut être associé qu'à une classe, une interface ou un espace de noms|  
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) \(niveau 1\)|initialisation de copie non conforme ; plusieurs conversions définies par l'utilisateur ont été appliquées implicitement|  
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) \(niveau 4\)|bibliothèque de types présumée construite pour des pointeurs 'nombre' bits|  
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) \(niveau 1\)|reinterpret\_cast utilisé entre des classes connexes : 'classe1' et 'classe2'|  
|C4962|'fonction' : les optimisations guidées par profil sont désactivées, car elles génèrent des incohérences au niveau des données de profil|  
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) \(niveau 4\)|'symbol' : la spécification d'exception ne correspond pas à la déclaration précédente|  
|C4987 \(niveau 4\)|extension non standard utilisée : 'throw \(...\)'|  
|C4988 \(niveau 4\)|'symbol' : variable déclarée en dehors de la portée classe\/fonction|  
  
## Voir aussi  
 [warning](../preprocessor/warning.md)