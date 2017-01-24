---
title: "Syntaxe de sp&#233;cification de format&#160;: fonctions printf et wprintf | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wprintf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "directives de balise printf (fonction)"
  - "champs de spécification de formation pour la fonction printf"
  - "champs de précision"
  - "directives de balise d'impression"
  - "printf (fonction), champs de spécification de format"
  - "printf (fonction), précision"
  - "champs de type"
  - "champs de type, printf (fonction)"
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Syntaxe de sp&#233;cification de format&#160;: fonctions printf et wprintf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit la syntaxe des arguments de chaîne de format de `printf`, `wprintf` et des fonctions associées.  Des versions plus sécurisées de ces fonctions sont disponibles ; pour plus d'informations, consultez [Fonctionnalités de sécurité dans le CRT](../c-runtime-library/security-features-in-the-crt.md).  Pour plus d'informations sur chaque fonction, consultez la documentation de ces fonctions spécifiques.  Pour obtenir la liste de ces fonctions, consultez [E\/S de flux](../c-runtime-library/stream-i-o.md).  
  
 Une spécification de format, qui se compose de champs facultatifs et obligatoires, se présente sous la forme suivante :  
  
 `%`\[[flags](../c-runtime-library/flag-directives.md)\] \[[width](../c-runtime-library/printf-width-specification.md)\] \[**.**[precision](../c-runtime-library/precision-specification.md)\] \[{`h` &#124; `l` &#124; `ll` &#124; `w` &#124; `I` &#124; `I32` &#124; `I64`}\] [type](../c-runtime-library/printf-type-field-characters.md)  
  
 Chaque champ de la spécification de format est un caractère ou un nombre qui représente un spécificateur d'option ou de conversion de format particulier.  Le caractère obligatoire `type` précise le type de conversion à appliquer à un argument.  Les champs facultatifs `flags`, `width` et `precision` contrôlent d'autres aspects de format.  Une spécification de format de base contient uniquement le symbole de pourcentage et un caractère `type`, par exemple, `%s`, qui spécifie une conversion de chaînes.  Dans les versions sécurisées des fonctions, si un signe de pourcentage est suivi d'un caractère qui n'a aucune signification en tant que champ de format, le gestionnaire de paramètres non valides est appelé.  Pour plus d'informations, consultez [Validation de paramètre](../c-runtime-library/parameter-validation.md).  Dans les versions non sécurisées, le caractère est copié dans la sortie sans être modifié.  Pour imprimer un caractère de pourcentage, utilisez `%%`.  
  
 Les champs de la spécification de format contrôlent les aspects ci\-après de la conversion et de la mise en forme d'argument :  
  
 `type`  
 Caractère de spécificateur de conversion requis qui détermine si le paramètre `argument` associé est interprété comme un caractère, une chaîne, un entier ou un nombre à virgule flottante.  Pour plus d'informations, consultez [Caractères du champ de type printf](../c-runtime-library/printf-type-field-characters.md).  
  
 `flags`  
 Caractères facultatifs qui contrôlent la justification de sortie et la sortie des signes, espaces, zéros non significatifs, virgules décimales et préfixes octaux et hexadécimaux.  Pour plus d'informations, consultez [Directives de balise](../c-runtime-library/flag-directives.md).  Plusieurs indicateurs peuvent apparaître dans une spécification de format, et les indicateurs peuvent apparaître dans n'importe quel ordre.  
  
 `width`  
 Nombre décimal facultatif qui spécifie le nombre minimal de caractères envoyés.  Pour plus d'informations, consultez [Spécification de largeur printf](../c-runtime-library/printf-width-specification.md).  
  
 `precision`  
 Nombre décimal facultatif qui spécifie le nombre maximal de caractères imprimés pour les chaînes, le nombre de chiffres significatifs ou le nombre de chiffres après le caractère de virgule décimale pour les valeurs à virgule flottante ou le nombre minimal de chiffres imprimés pour les valeurs entières.  Pour plus d'informations, consultez « Comment les valeurs de précision affectent le type » dans [Spécifications de précision](../c-runtime-library/precision-specification.md).  
  
 `h` &#124; `l` &#124; `ll` &#124; `w` &#124; `I` &#124; `I32` &#124; `I64`  
 Préfixes facultatifs de `type` qui spécifient la taille de l'argument correspondant.  Pour plus d'informations, consultez « Préfixes de taille » dans [Spécification de taille](../c-runtime-library/size-specification.md).  
  
> [!IMPORTANT]
>  Assurez\-vous que les chaînes de spécification de format ne sont pas définies par l'utilisateur.  Par exemple, imaginez un programme qui invite l'utilisateur à entrer un nom et enregistre l'entrée dans une variable de chaîne nommée `name`.  Pour imprimer `name`, n'effectuez pas l'opération suivante :  
>   
>  `printf( name ); /* Danger!  If name contains "%s", program will crash */`  
>   
>  Procédez plutôt comme suit :  
>   
>  `printf( "%s", name );`  
  
## Voir aussi  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [Paramètres positionnels printf\_p](../c-runtime-library/printf-p-positional-parameters.md)   
 [Directives de balise](../c-runtime-library/flag-directives.md)   
 [Spécification de largeur printf](../c-runtime-library/printf-width-specification.md)   
 [Spécifications de précision](../c-runtime-library/precision-specification.md)   
 [Spécification de taille](../c-runtime-library/size-specification.md)   
 [Caractères du champ de type printf](../c-runtime-library/printf-type-field-characters.md)