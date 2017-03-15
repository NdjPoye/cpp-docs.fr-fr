---
title: "&lt;locale&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<locale>"
  - "std.<locale>"
  - "locale/std::<locale>"
  - "std::<locale>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "locale (en-tête)"
ms.assetid: ca56f9d2-7128-44da-8df1-f4c78c17fbf2
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# &lt;locale&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les classes de modèle et les fonctions que les programmes C\+\+ peuvent utiliser pour encapsuler et manipuler différentes conventions culturelles concernant la représentation et la mise en forme des données numériques, monétaires et de calendrier, y compris la prise en charge de l'internationalisation de la classification des caractères et du classement des chaînes.  
  
## Syntaxe  
  
```  
  
#include <locale>  
  
```  
  
### Fonctions  
  
|||  
|-|-|  
|[has\_facet](../Topic/has_facet.md)|Teste si une facette particulière est stockée dans des paramètres régionaux spécifiés.|  
|[isalnum](../Topic/isalnum.md)|Teste si un élément figurant dans des paramètres régionaux est un caractère alphabétique ou numérique.|  
|[isalpha](../Topic/isalpha.md)|Teste si un élément figurant dans des paramètres régionaux est un caractère alphabétique.|  
|[iscntrl](../Topic/iscntrl.md)|Teste si un élément figurant dans des paramètres régionaux est un caractère de contrôle.|  
|[isdigit](../Topic/isdigit.md)|Teste si un élément figurant dans des paramètres régionaux est un caractère numérique.|  
|[isgraph](../Topic/isgraph.md)|Teste si un élément figurant dans des paramètres régionaux est un caractère alphanumérique ou de ponctuation.|  
|[islower](../Topic/islower.md)|Teste si un élément figurant dans des paramètres régionaux est en minuscules.|  
|[isprint](../Topic/isprint.md)|Teste si un élément figurant dans des paramètres régionaux est un caractère imprimable.|  
|[ispunct](../Topic/ispunct.md)|Teste si un élément figurant dans des paramètres régionaux est un caractère de ponctuation.|  
|[isspace](../Topic/isspace.md)|Teste si un élément figurant dans des paramètres régionaux est un espace blanc.|  
|[isupper](../Topic/isupper.md)|Teste si un élément figurant dans des paramètres régionaux est en majuscules.|  
|[isxdigit](../Topic/isxdigit.md)|Teste si un élément figurant dans des paramètres régionaux est un caractère utilisé pour représenter un nombre hexadécimal.|  
|[tolower](../Topic/tolower.md)|Convertit un caractère en minuscule.|  
|[toupper](../Topic/toupper.md)|Convertit un caractère en majuscule.|  
|[use\_facet](../Topic/use_facet.md)|Retourne une référence à une facette d'un type spécifié stocké dans des paramètres régionaux.|  
  
### Classes  
  
|||  
|-|-|  
|[codecvt](../standard-library/codecvt-class.md)|Classe de modèle qui fournit une facette utilisée pour convertir des données entre les encodages de caractères interne et externe.|  
|[codecvt\_base](../standard-library/codecvt-base-class.md)|Classe de base de la classe codecvt utilisée pour définir un type d'énumération appelé **result**, utilisé comme type de retour pour les fonctions membres de facette pour indiquer le résultat d'une conversion.|  
|[codecvt\_byname](../standard-library/codecvt-byname-class.md)|Classe de modèle dérivée qui décrit un objet susceptible de servir de facette d'assemblage de paramètres régionaux donnés, permettant ainsi la récupération d'informations spécifiques à une zone culturelle concernant les conversions.|  
|[collate](../standard-library/collate-class.md)|Classe de modèle d'assemblage fournissant une facette qui gère les conventions de tri de chaîne.|  
|[collate\_byname](../standard-library/collate-byname-class.md)|Classe de modèle dérivée qui décrit un objet susceptible de servir de facette d'assemblage de paramètres régionaux donnés, permettant ainsi la récupération d'informations spécifiques à une zone culturelle concernant les conventions de tri de chaîne.|  
|[ctype](../standard-library/ctype-class.md)|Classe de modèle fournissant une facette utilisée pour la classification des caractères et la conversion entre majuscules et minuscules et entre le jeu de caractères natif et celui utilisé par les paramètres régionaux.|  
|[ctype\<char\>](../standard-library/ctype-char-class.md)|Classe constituant une spécialisation explicite de la classe de modèle **ctype\<CharType**\> en type `char`, décrivant un objet qui peut servir de facette de paramètres régionaux pour caractériser diverses propriétés d'un caractère de type `char`.|  
|[ctype\_base](../standard-library/ctype-base-class.md)|Classe de base de la classe ctype utilisée pour définir des types énumération utilisés pour classifier ou tester les caractères, individuellement ou dans des plages entières.|  
|[ctype\_byname](../standard-library/ctype-byname-class.md)|Classe de modèle dérivée qui décrit un objet pouvant servir de facette ctype de paramètres régionaux donnés, permettant ainsi la classification des caractères et la conversion des caractères entre des jeux de caractères natifs, de casse ou de paramètres régionaux spécifiés.|  
|[paramètres régionaux](../standard-library/locale-class.md)|Classe qui décrit un objet de paramètres régionaux encapsulant des informations spécifiques à la culture sous la forme d'un ensemble de facettes qui définissent collectivement un environnement localisé spécifique.|  
|[messages](../standard-library/messages-class.md)|Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour récupérer des messages localisés à partir d'un catalogue de messages internationalisés pour des paramètres régionaux donnés.|  
|[messages\_base](../standard-library/messages-base-class.md)|Classe de base qui décrit un type `int` pour le catalogue de messages.|  
|[messages\_byname](../standard-library/messages-byname-class.md)|Classe de modèle dérivée qui décrit un objet pouvant servir de facette de message de paramètres régionaux donnés, permettant ainsi la récupération de messages localisés.|  
|[money\_base](../standard-library/money-base-class.md)|Classe de base de la classe ctype utilisée pour définir des types énumération utilisés pour classifier ou tester les caractères, individuellement ou dans des plages entières.|  
|[money\_get](../standard-library/money-get-class.md)|Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de séquences de type **CharType** en valeurs monétaires.|  
|[money\_put](../standard-library/money-put-class.md)|Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de valeurs monétaires en séquences de type **CharType**.|  
|[moneypunct](../standard-library/moneypunct-class.md)|Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour décrire les séquences de type **CharType** utilisées pour représenter un champ d'entrée monétaire ou un champ de sortie monétaire.|  
|[moneypunct\_byname](../standard-library/moneypunct-byname-class.md)|Classe de modèle dérivée qui décrit un objet pouvant servir de facette moneypunct de paramètres régionaux donnés, permettant ainsi la mise en forme de champs d'entrée ou de sortie monétaires.|  
|[num\_get](../standard-library/num-get-class.md)|Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de séquences de type **CharType** en valeurs numériques.|  
|[num\_put](../standard-library/num-put-class.md)|Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de valeurs numériques en séquences de type **CharType**.|  
|[numpunct](../standard-library/numpunct-class.md)|Classe de modèle qui décrit un objet pouvant servir de facette locale pour décrire les séquences de type **CharType** utilisées pour représenter des informations sur la mise en forme et la ponctuation d'expressions numériques et booléennes.|  
|[numpunct\_byname](../standard-library/numpunct-byname-class.md)|Classe de modèle dérivée qui décrit un objet pouvant servir de facette moneypunct de paramètres régionaux donnés, permettant la mise en forme et la ponctuation d'expressions numériques et booléennes.|  
|[time\_base](../standard-library/time-base-class.md)|Classe qui sert de classe de base pour les facettes de la classe de modèle time\_get, définissant simplement le type énuméré dateorder et plusieurs constantes de ce type.|  
|[time\_get](../standard-library/time-get-class.md)|Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de séquences de type **CharType** en valeurs temporelles.|  
|[time\_get\_byname](../standard-library/time-get-byname-class.md)|Classe de modèle dérivée qui décrit un objet pouvant servir de facette de paramètres régionaux du typetime\_get\<**CharType**, **InputIterator**\>.|  
|[time\_put](../standard-library/time-put-class.md)|Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de valeurs temporelles en séquences de type **CharType**.|  
|[time\_put\_byname](../standard-library/time-put-byname-class.md)|Classe de modèle dérivée qui décrit un objet pouvant servir de facette de paramètres régionaux du type `time_put`\<**CharType**, **OutputIterator**\>.|  
|[wbuffer\_convert, classe](../standard-library/wbuffer-convert-class.md)|Décrit une mémoire tampon de flux qui contrôle la transmission des éléments vers et à partir d'une mémoire tampon de flux d'octets.|  
|[wstring\_convert, classe](../standard-library/wstring-convert-class.md)|Classe de modèle qui effectue des conversions entre une chaîne étendue et une chaîne d'octets.|  
  
## Voir aussi  
 [Pages de codes](../c-runtime-library/code-pages.md)   
 [Chaînes relatives aux noms, aux langues, au pays et à la région](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)