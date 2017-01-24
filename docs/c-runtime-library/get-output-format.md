---
title: "_get_output_format | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_output_format"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "get_output_format"
  - "_get_output_format"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_get_output_format (fonction)"
  - "get_output_format (fonction)"
  - "mise en forme de la sortie"
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _get_output_format
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient la valeur actuelle de l’indicateur de format de sortie.  
  
> [!IMPORTANT]
>  Cette fonction est obsolète. Depuis Visual Studio 2015, elle n’est pas disponible dans la bibliothèque CRT.  
  
## Syntaxe  
  
```  
unsigned int _get_output_format();  
```  
  
## Valeur de retour  
 La valeur actuelle de l’indicateur de format de sortie.  
  
## Notes  
 L’indicateur de format de sortie contrôle les fonctionnalités de l’E\/S mise en forme. Pour l’instant, l’indicateur a deux valeurs possibles : 0 et `_TWO_DIGIT_EXPONENT`. Si `_TWO_DIGIT_EXPONENT` est défini, les nombres à virgule flottante sont générés avec seulement deux chiffres dans l’exposant, sauf si un troisième chiffre est requis par la taille de l’exposant. Si l’indicateur est défini sur zéro, la virgule flottante générée affiche trois chiffres dans l’exposant, en utilisant si nécessaire des zéros pour compléter la valeur sur trois chiffres.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_get_output_format`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [Caractères du champ de type printf](../c-runtime-library/printf-type-field-characters.md)   
 [\_set\_output\_format](../c-runtime-library/set-output-format.md)