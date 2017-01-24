---
title: "plages de types de donn&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "unsigned"
  - "wchar_t"
  - "char"
  - "signed"
  - "short"
  - "long"
  - "double"
  - "float"
  - "int"
  - "long_double"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "float (mot clé) (C++)"
  - "char (mot clé) (C++)"
  - "unsigned long"
  - "__wchar_t (mot clé) (C++)"
  - "unsigned short int"
  - "enum (mot clé)"
  - "unsigned char (mot clé) (C++)"
  - "type de données Integer, plages de types de données"
  - "int (type de données)"
  - "types de données (C++), plages"
  - "unsigned int"
  - "short (type de données)"
  - "short int (type de données)"
  - "types signés (C++), plages de types de données"
  - "long long (mot clé) (C++)"
  - "long double (mot clé) (C++)"
  - "type de données Double, plages de types de données"
  - "signed short int"
  - "unsigned short"
  - "types d'entier dimensionné"
  - "signed int"
  - "signed long int"
  - "signed char (mot clé) (C++)"
  - "wchar_t (mot clé) (C++)"
  - "long (mot clé) (C++)"
  - "plages (C++)"
  - "types non signés (C++), plages de types de données"
  - "chiffres à virgule flottante, plages de types de données"
  - "plages (C++), types de données"
  - "long int (mot clé) (C++)"
  - "unsigned long int"
ms.assetid: 3691ceca-05fb-4b82-b1ae-5c4618cda91a
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# plages de types de donn&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les compilateurs Visual C++ 32 bits et 64 bits identifient les types de la table dans la suite de cet article.  
  
-   `int` (`unsigned``int`)  
  
-   `__int8` (`unsigned``__int8`)  
  
-   `__int16` (`unsigned``__int16`)  
  
-   `__int32` (`unsigned``__int32`)  
  
-   `__int64` (`unsigned``__int64`)  
  
-   `short` (`unsigned``short`)  
  
-   `long` (`unsigned``long`)  
  
-   `long` `long` (`unsigned``long``long`)  
  
 Si son nom commence par deux traits de soulignement (`__`), un type de données est non standard.  
  
 Les plages spécifiées dans le tableau ci-dessous sont inclusives-inclusives.  
  
|Nom de type|Octets|Autres noms|Plage de valeurs|  
|---------------|-----------|-----------------|---------------------|  
|int|4|signed|–2 147 483 648 à 2 147 483 647|  
|unsigned int|4|non signé|de 0 à 4 294 967 295|  
|__int8|1|char|-128 à 127|  
|unsigned __int8|1|unsigned char|0 à 255|  
|__int16|2|short, short int, signed short int|-32 768 à 32 767|  
|unsigned __int16|2|unsigned short, unsigned short int|0 à 65 535|  
|__int32|4|signed, signed int, int|–2 147 483 648 à 2 147 483 647|  
|unsigned __int32|4|unsigned, unsigned int|de 0 à 4 294 967 295|  
|__int64|8|long long, signed long long|-9 223 372 036 854 775 808 à 9 223 372 036 854 775 807|  
|unsigned __int64|8|unsigned long long|de 0 à 18 446 744 073 709 551 615|  
|bool|1|aucun|false ou true|  
|char|1|aucun|–128 à 127 par défaut<br /><br /> 0 à 255 une fois compilé à l’aide de [/J](../build/reference/j-default-char-type-is-unsigned.md)|  
|signed char|1|aucun|-128 à 127|  
|unsigned char|1|aucun|0 à 255|  
|short|2|short int, signed short int|-32 768 à 32 767|  
|unsigned short|2|unsigned short int|0 à 65 535|  
|long|4|long int, signed long int|–2 147 483 648 à 2 147 483 647|  
|unsigned long|4|unsigned long int|de 0 à 4 294 967 295|  
|long long|8|aucun (mais équivaut à __int64)|-9 223 372 036 854 775 808 à 9 223 372 036 854 775 807|  
|unsigned long long|8|aucun (mais équivaut à unsigned __int64)|de 0 à 18 446 744 073 709 551 615|  
|enum|selon le cas|aucun|Consultez [Notes](#bkmkRemarks) plus loin dans cet article.|  
|float|4|aucun|3.4E +/- 38 (7 chiffres)|  
|double|8|aucun|1.7E +/- 308 (15 chiffres)|  
|long double|identique à double|aucun|Identique à double|  
|wchar_t|2|__wchar_t|0 à 65 535|  
  
 Selon la façon dont elle est utilisée, une variable de `__wchar_t` désigne un type caractères larges ou un type caractères multioctets. Utilisez le préfixe `L` avant une constante caractère ou chaîne pour désigner la constante de type caractères larges.  
  
 `signed` et `unsigned` sont des modificateurs que vous pouvez utiliser avec tout type d'entier sauf `bool`. Notez que `char`, `signed char` et `unsigned char` sont trois types distincts qui servent aux mécanismes tels que la surcharge et les modèles.  
  
 Les types `int` et `unsigned``int` ont une taille de quatre octets. Toutefois, le code portable ne doit pas dépendre de la taille d'`int`, car la norme du langage permet que cela soit propre à l'implémentation.  
  
 C/C++ dans Visual Studio prend également en charge les types entier dimensionnés. Pour plus d’informations, consultez [__int8, \__int16, \__int32, \__int64](../cpp/int8-int16-int32-int64.md) et [Limites d’entier](../cpp/integer-limits.md).  
  
 Pour plus d’informations sur les restrictions de tailles de chaque type, consultez [Types fondamentaux](../cpp/fundamental-types-cpp.md).  
  
 La plage de types énumérés varie selon le contexte du langage et les indicateurs spécifiés du compilateur. Pour plus d'informations, consultez [Déclarations d'énumération C](../c-language/c-enumeration-declarations.md) et [Énumérations](../cpp/enumerations-cpp.md).  
  
## Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)   
 [Types fondamentaux](../cpp/fundamental-types-cpp.md)