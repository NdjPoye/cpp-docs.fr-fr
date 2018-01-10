---
title: "Avertissements du compilateur désactivés par défaut | Documents Microsoft"
ms.date: 11/04/2016
ms.technology: cpp-tools
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 48afd89f4b795a4f582d8b9506c527a602a1d2b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warnings-that-are-off-by-default"></a>Avertissements du compilateur désactivés par défaut

Le compilateur contient des avertissements qui sont désactivés par défaut, car la plupart des utilisateurs ne souhaitent pas les voir. Toutefois, vous pouvez les activer à l'aide de l'une des options suivantes.

`#pragma warning(default : warning_number )`  
L'avertissement spécifié (`warning_number`) est activé à son niveau par défaut. La documentation de l'avertissement contient le niveau par défaut de l'avertissement.

`#pragma warning( warning_level : warning_number )`  
L'avertissement spécifié (`warning_number`) est activé au niveau spécifié (`warning_level`).

[/Wall](../build/reference/compiler-option-warning-level.md)  
**/ Mur** Active tous les avertissements qui sont désactivés par défaut.

Les avertissements suivants sont désactivés par défaut.

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (niveau 4)|l'énumérateur 'identificateur' dans un switch de l'enum 'énumération' n'est pas géré explicitement par une étiquette case|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (niveau 4)|l'énumérateur 'identificateur' dans un switch de l'enum 'énumération' n'est pas géré|
|C4191 (niveau 3)|'opérateur/opération' : conversion potentiellement dangereuse de 'type d'expression' à 'type requis'|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (niveau 4)|'identificateur' : conversion de 'type1' en 'type2', perte possible de données|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (niveau 4)|'opérateur' : conversion de 'type1' en 'type2', perte possible de données|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (niveau 4)|'fonction' : aucun prototype de fonction fourni : conversion de '()' en '(void)'|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (niveau 4)|'fonction' : une fonction membre ne se substitue à aucune fonction membre virtuelle de classe de base|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (niveau 1)|'fonction_virtuelle' : aucune substitution disponible pour la fonction membre virtuelle à partir de la base 'classe' ; la fonction est masquée|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (niveau 3)|'classe' : la classe possède des fonctions virtuelles, mais le destructeur n'est pas virtuel|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (niveau 4)|'fonction' : aucune substitution disponible pour la fonction membre virtuelle à partir de 'type' de base ; la fonction est masquée|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (niveau 3)|'opérateur' : constantes non signées/négatives incompatibles|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (niveau 4)|extension non standard utilisée : ’var’ : variable de contrôle de boucle déclarée dans la boucle for utilisée à l’extérieur de la portée de la boucle|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (niveau 4)|'opérateur' : l'expression est toujours false|
|[L’erreur C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (niveau 4)|'type' : utilisation de ce type non défini dans les métadonnées CLR, ce qui peut provoquer une exception runtime|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (niveau 1)|modification de comportement : 'fonction' appelé, mais un opérateur de membre a été appelé dans les versions précédentes|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (niveau 1)|changement de comportement : 'membre1' appelé à la place de 'membre2'|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : utilisé dans la liste des initialiseurs membre de base|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (niveau 4)|'action' : conversion de 'type_1' en 'type_2', incompatibilité signed/unsigned|
|C4370 (niveau 3)|la disposition de classe a été modifiée à partir d'une version précédente du compilateur en raison d'une meilleure compression|
|C4371 (niveau 3)|la disposition de classe peut avoir été modifiée à partir d'une version précédente du compilateur en raison d'une meilleure compression du membre 'member'|
|C4388 (niveau 4)|incompatibilité signed/unsigned|
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (niveau 2)|'fonction' : la signature de fonction contient le type 'type' ; le passage d'objets C++ n'est pas sécurisé entre le code pure et le code mixte ou natif.|
|C4426 (niveau 1)|indicateurs d’optimisation modifiés après l’en-tête, peut être dû à #pragma optimize()|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (niveau 4)|'classe1' : la disposition des objets sous /vd2 sera modifiée en raison de la base virtuelle 'classe2'|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (niveau 4)|le dynamic_cast de la base virtuelle 'classe1' en 'classe2' risque d'échouer dans certains contextes|
|C4444 (niveau 3)|'__unaligned' de niveau supérieur n'est pas implémenté dans ce contexte|
|C4464 (niveau 4)|chemin include relatif contient '..'|
|C4472 (niveau 1)|'identifier' est un enum natif : ajoutez un spécificateur d'accès (private/public) pour déclarer un enum géré|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (niveau 4)|'fonction' : la fonction inline non référencée a été supprimée|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (niveau 4)|'nom de type' : le nom de type dépasse la limite métadonnées de 'limite' caractères|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (niveau 1)|l’expression avant la virgule correspond à une fonction qui n’a pas de liste d’arguments|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (niveau 1)|l’appel de fonction avant la virgule n’a pas de liste d’arguments|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (niveau 1)|'opérateur' : l'opérateur avant la virgule n'a pas d'effet ; opérateur avec effet secondaire attendu|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (niveau 1)|l'expression avant la virgule n'a pas d'effet ; expression avec effet secondaire attendu|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (niveau 1)|'opérateur' : l'opérateur avant la virgule n'a pas d'effet ; souhaitez-vous utiliser 'opérateur' ?|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (niveau 1)|l'expression n'a pas d'effet ; attendue expression avec effets secondaires|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (niveau 3)|'__assume' contient l'effet 'effet'|
|[L’erreur C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (niveau 4)|Information : la sémantique changée depuis Visual C++ 7.1 ; les exceptions structurées (SEH) ne sont plus interceptées|
|C4574 (niveau 4)|'identifier' est défini comme étant '0' : voulez-vous utiliser 'identifier #if' ?|
|C4582 (niveau 4)|'*type*' : constructeur n’est pas appelé de manière implicite|
|C4583 (niveau 4)|'*type*' : destructeur n’est pas appelé de manière implicite|
|C4587 (niveau 1)|'*anonymous_structure*' : changement de comportement : constructeur est appelé n’est plus implicitement.|
|C4588 (niveau 1)|'*anonymous_structure*' : changement de comportement : destructeur est appelé n’est plus implicitement.|
|C4598 (niveaux 1 et 3)|' #include «*en-tête*» ' : numéro de l’en-tête *nombre* dans l’en-tête précompilé ne correspond pas à la compilation en cours à cette position|
|C4599 (niveau 3)|'*option* *chemin d’accès*' : nombre d’arguments de ligne de commande *nombre* ne correspond pas d’en-tête précompilé|
|C4605 (niveau 1)|' /D*macro*' spécifié sur la ligne de commande actuelle, mais n’a pas été spécifié lorsque l’en-tête précompilé a été généré|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (niveau 3)|#pragma warning : numéro d'avertissement inexistant 'numéro'|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (niveau 4)|'classe dérivée' : le constructeur par défaut n'a pas pu être généré parce que le constructeur par défaut de la classe de base est inaccessible|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (niveau 4)|'classe dérivée' : le constructeur de copie n'a pas pu être généré parce qu'un constructeur de copie de la classe de base est inaccessible|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (niveau 4)|'classe dérivée' : l'opérateur d'assignation n'a pas pu être généré parce qu'un opérateur d'assignation de la classe de base est inaccessible|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (niveau 1)|digrammes non pris en charge avec -Ze. Séquence de caractères 'digramme' non interprétée comme jeton de remplacement pour 'car'|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (niveau 3)|'instance' : la construction d'un objet static local n'est pas thread-safe|
|C4647 (niveau 3)|changement de comportement : __is_pod (*type*) a une valeur différente dans les versions précédentes|
|C4654 (niveau 4)|Le code placé avant d’inclure d’en-tête précompilé ligne sera ignorée. Ajoutez le code à l’en-tête précompilé.|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (niveau 4)|'*symbole*'n’est pas défini comme préprocesseur ou macro, remplacement par '0' pour'*directives*'|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (niveau 4)|'*symbole*' : aucun attribut de paramètre directionnel spécifié, [in] pris par défaut|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (niveau 3)|'*type défini par l’utilisateur*' : changement de comportement possible, changement de retour UDT convention d’appel|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (niveau 1)|'*fonction*' : signature de membre non privée contient un type natif privé d’assembly 'type_natif'|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (niveau 4)|'*fonction*' : fonction non inline|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (niveau 3)|stockage de résultat flottant 32 bits en mémoire, perte possible de performances|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|accès volatile de '*expression*' dépend :\<iso &#124; ms > configuration ; envisagez d’utiliser des fonctions intrinsèques __iso_volatile_load/store|
|C4749 (niveau 4)|conditionnellement pris en charge : offsetof appliqué au type de disposition-non standard '*type*'|
|C4767 (niveau 4)|nom de la section «*symbole*' est supérieure à 8 caractères et sera tronqué par l’éditeur de liens|
|C4768 (niveau 3)|attributs __declspec avant la spécification de liaison sont ignorés.|
|C4774 (niveau 4)|'*chaîne*' : chaîne attendue dans l’argument de format *nombre* n’est pas une chaîne littérale|
|C4786 (niveau 3)|'*symbole*' : nom de l’objet a été tronqué à 'nombre' caractères dans les informations de débogage|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (niveau 4)|'octets' octets de remplissage ajoutés après construction 'nom_membre'|
|C4826 (niveau 2)|La conversion de '*type1*'à'*type2*' est de type signe étendu. Cela peut entraîner un comportement inattendu.|
|C4837 (niveau 4)|trigraphe détecté : ' ?? *caractère*« remplacé par »*caractère*'|
|C4841 (niveau 4)|extension non standard utilisée : indicateur composée membre utilisé dans offsetof|
|C4842 (niveau 4)|le résultat de « offsetof' appliqué à un type à l’aide de l’héritage multiple n’est pas garanti pour être cohérent entre les versions du compilateur|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (niveau 4)|'_fichier_(*line_number*)' compilateur ne peut pas appliquer l’ordre d’évaluation de gauche à droite dans la liste d’initialisation entre accolades|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (niveau 1)|cast de littéral de chaîne étendu en 'LPSTR'|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (niveau 1)|cast de littéral de chaîne en 'LPWSTR'|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (niveau 1)|'déclarateur' : un GUID ne peut être associé qu'à une classe, une interface ou un espace de noms|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (niveau 1)|initialisation de copie non conforme ; plusieurs conversions définies par l'utilisateur ont été appliquées implicitement|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (niveau 4)|bibliothèque de types présumée construite pour des pointeurs 'nombre' bits|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (niveau 1)|reinterpret_cast utilisé entre des classes connexes : 'classe1' et 'classe2'|
|C4962|'fonction' : les optimisations guidées par profil sont désactivées, car elles génèrent des incohérences au niveau des données de profil|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (niveau 4)|'*symbole*' : spécification d’exception ne correspond pas à la déclaration précédente|
|C4987 (niveau 4)|extension non standard utilisée : 'throw (...)'|
|C4988 (niveau 4)|'*symbole*' : variable déclarée en dehors de la portée classe/fonction|
|C5022|'*type*' : plusieurs constructeurs de déplacement spécifiés|
|C5023|'*type*' : plusieurs opérateurs d’assignation de déplacement spécifiés|
|C5024 (niveau 4)|'*type*' : constructeur de déplacement a été implicitement défini comme étant supprimé|
|C5025 (niveau 4)|'*type*' : déplacer l’opérateur d’assignation a été implicitement défini comme étant supprimé|
|C5026 (niveaux 1 et 4)|'*type*' : constructeur de déplacement a été implicitement défini comme étant supprimé|
|C5027 (niveaux 1 et 4)|'*type*' : déplacer l’opérateur d’assignation a été implicitement défini comme étant supprimé|
|C5029 (niveau 4)|extension non standard utilisée : les attributs d’alignement en C++ s’appliquent aux variables, les membres de données et les types de balises uniquement|
|C5031 (niveau 4)|#pragma warning (pop) : incompatibilité probable, l’affichage d’état d’avertissement émis dans un autre fichier|
|C5032 (niveau 4)|détecté #pragma warning (push) sans Warning (pop) correspondant #pragma|
|C5035|l’utilisation de fonctionnalité '*fonctionnalité*' provoque la fonction *fonction* doit être compilé comme code de l’invité|
|C5036 (niveau 1)|conversion de pointeur de fonction varargs lors de la compilation avec /hybrid:x86arm64 '*type1*'à'*type2*'|

Ces avertissements sont désactivées, sauf si le [/ permissive-](../build/reference/permissive-standards-conformance.md) option du compilateur est définie :

|||
|-|-|
|[C4471 (niveau 4)](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md)|une déclaration anticipée d'une énumération non délimitée doit avoir un type sous-jacent (int pris par défaut)|
|[C4608 (niveau 3)](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md)|' union\_membre ' a déjà été initialisé par un autre membre union dans la liste d’initialiseurs, 'union_member'|


Ces avertissements ont été désactivée par défaut dans les versions du compilateur avant Visual Studio 2015 :

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (niveau 2)|'conversion' : troncation de 'type1' à 'type2'|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (niveau 1)|'variable' : troncation de pointeur de 'type' à 'type'|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (niveau 1)|'opération' : la conversion de 'type1' en 'type2' d'une taille supérieure|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (niveau 1)|'opérateur' : zéro étendant 'type1' en 'type2' d’une taille supérieure|

Ces avertissements ont été désactivée par défaut dans les versions du compilateur antérieures à Visual Studio 2012 :

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (niveau 4)|spécificateur de type manquant - int est pris en compte par défaut. Remarque : C ne prend plus en charge int par défaut|

## <a name="see-also"></a>Voir aussi

[warning](../preprocessor/warning.md)
