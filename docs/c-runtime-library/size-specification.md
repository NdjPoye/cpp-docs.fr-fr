---
title: "Sp&#233;cification de taille | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "size"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "printf (fonction), champs de spécification de format"
ms.assetid: 525dc5d8-e70a-4797-a6a0-ec504a27355c
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Sp&#233;cification de taille
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans une spécification de format, le quatrième champ est un modificateur de longueur d'argument pour le spécificateur de conversion.  Les préfixes de champ `size` du champ `type` \(`h`, `l`, `w`, `I`, `I32`, `I64` et `ll`\) spécifient la « taille » de l'argument correspondant \(long ou court, 32 bits ou 64 bits, caractère sur un octet ou large\), selon le spécificateur de conversion qu'ils modifient.  Ces préfixes de taille sont utilisés avec les caractères `type` dans les familles `printf` et `wprintf` de fonctions pour spécifier l'interprétation des longueurs d'argument, comme illustré dans le tableau suivant.  Le champ `size` est facultatif pour certains types d'arguments.  Si aucun préfixe de taille n'est spécifié, le formateur consomme les arguments de type entier, par exemple, `char`, `short`, `int`, `long` signé ou non signé, et les types d'énumération — en tant que types `int` 32 bits, tandis que les arguments à virgule flottante sont consommés en tant que types `double` 64 bits.  Cela correspond aux règles de promotion d'argument par défaut pour les listes d'arguments de variable.  Pour plus d'informations sur la promotion d'argument, consultez [Ellipses et arguments par défaut](../misc/ellipses-and-default-arguments.md).  Sur les systèmes 32 bits et 64 bits, la spécification de format d'un argument d'entier 64 bits doit inclure un préfixe de taille `ll` ou `I64`.  Sinon, le comportement du formateur n'est pas défini.  
  
 Certains types sont de tailles différentes en code 32 bits et 64 bits.  Par exemple, la longueur de `size_t` est 32 bits dans le code compilé pour x86, contre 64 bits dans le code compilé pour x64.  Pour créer un code de mise en forme indépendant de la plateforme pour les types de largeur variable, vous pouvez utiliser un modificateur de longueur d'argument de largeur variable.  Vous pouvez également utiliser un modificateur de longueur d'argument 64 bits et promouvoir explicitement le type d'argument de largeur variable à 64 bits.  Le modificateur de longueur d'argument `I` spécifique à Microsoft gère les arguments entiers de largeur variable.  
  
> [!NOTE]
>  Les préfixes de modificateur de longueur `I`, `I32` et `I64` sont des extensions Microsoft et ne sont pas compatibles avec ANSI.  Le préfixe `h` quand il est utilisé avec des données de type `char`, le préfixe `w` quand il est utilisé avec des données de type `wchar_t` et le préfixe `l` quand il est utilisé avec des données de type `double` sont des extensions Microsoft.  Les préfixes de longueur `hh`, `j`, `z` et `t` ne sont pas pris en charge.  
  
### Préfixes de taille pour les spécificateurs de type de format printf et wprintf  
  
|Pour spécifier|Utilisez le préfixe|Avec le spécificateur de type|  
|--------------------|-------------------------|-----------------------------------|  
|`long int`|`l` \(L minuscule\)|`d`, `i`, `o`, `x` ou `X`|  
|`long unsigned int`|`l`|`o`, `u`, `x` ou `X`|  
|`long long`|`ll`|`d`, `i`, `o`, `x` ou `X`|  
|`short int`|`h`|`d`, `i`, `o`, `x` ou `X`|  
|`short unsigned int`|`h`|`o`, `u`, `x` ou `X`|  
|`__int32`|`I32`|`d`, `i`, `o`, `x` ou `X`|  
|`unsigned __int32`|`I32`|`o`, `u`, `x` ou `X`|  
|`__int64`|`I64`|`d`, `i`, `o`, `x` ou `X`|  
|`unsigned __int64`|`I64`|`o`, `u`, `x` ou `X`|  
|`ptrdiff_t` \(autrement dit, `__int32` sur les plateformes 32 bits, `__int64` sur les plateformes 64 bits\)|`I`|`d`, `i`, `o`, `x` ou `X`|  
|`size_t` \(autrement dit, `unsigned __int32` sur les plateformes 32 bits, `unsigned __int64` sur les plateformes 64 bits\)|`I`|`o`, `u`, `x` ou `X`|  
|`long double` \(Dans [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)], bien que `long double` soit un type distinct, il possède la même représentation interne que `double`.\)|`l` ou `L`|`a`, `A`, `e`, `E`, `f`, `g` ou `G`|  
|Caractères codés sur un seul octet avec les fonctions `printf` et `wprintf`.  \(Un spécificateur de type `hc` ou `hC` est synonyme de `c` dans les fonctions `printf` et de `C` dans les fonctions `wprintf`.\)|`h`|`c` ou `C`|  
|Caractères larges avec les fonctions `printf` et `wprintf`.  \(Un spécificateur de type `lc`, `lC`, `wc` ou `wC` est synonyme de `C` dans les fonctions `printf` et de `c` dans les fonctions `wprintf`.\)|`l` ou `w`|`c` ou `C`|  
|Chaîne de caractères codés sur un octet avec les fonctions `printf` et `wprintf`.  \(Un spécificateur de type `hs` ou `hS` est synonyme de `s` dans les fonctions `printf` et de `S` dans les fonctions `wprintf`.\)|`h`|`s`, `S` ou `Z`|  
|Chaîne de caractères larges avec les fonctions `printf` et `wprintf`.  \(Un spécificateur de type `ls`, `lS`, `ws` ou `wS` est synonyme de `S` dans les fonctions `printf` et de `s` dans les fonctions `wprintf`.\)|`l` ou `w`|`s`, `S` ou `Z`|  
  
## Voir aussi  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Syntaxe de spécification de format : fonctions printf et wprintf](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [Directives de balise](../c-runtime-library/flag-directives.md)   
 [Spécification de largeur printf](../c-runtime-library/printf-width-specification.md)   
 [Spécifications de précision](../c-runtime-library/precision-specification.md)   
 [Caractères du champ de type printf](../c-runtime-library/printf-type-field-characters.md)