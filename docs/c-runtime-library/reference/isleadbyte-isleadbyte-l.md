---
title: "isleadbyte, _isleadbyte_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isleadbyte_l"
  - "isleadbyte"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_istleadbyte"
  - "_isleadbyte_l"
  - "isleadbyte"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "octets de tête"
  - "_isleadbyte_l (fonction)"
  - "_istleadbyte (fonction)"
  - "istleadbyte (fonction)"
  - "isleadbyte (fonction)"
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# isleadbyte, _isleadbyte_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un caractère est l’octet de tête d’un caractère multioctet.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s’exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### Paramètres  
 `c`  
 Entier à tester.  
  
## Valeur de retour  
 `isleadbyte` retourne une valeur différente de zéro si l’argument satisfait la condition de test, ou 0 si ce n’est pas le cas. Dans les paramètres régionaux « C » et dans les paramètres régionaux SBCS \(jeu de caractères codés sur un octet\), `isleadbyte` retourne toujours 0.  
  
## Notes  
 La macro `isleadbyte` retourne une valeur différente de zéro si son argument est le premier octet d’un caractère multioctet.`isleadbyte` produit un résultat significatif pour n’importe quel argument entier de \-1 \(`EOF`\) à `UCHAR_MAX` \(0xFF\), inclusivement.  
  
 Le type d’argument attendu de `isleadbyte` est `int`. Si un caractère signé est passé, le compilateur est susceptible de le convertir en un entier par extension de signe, aboutissant à des résultats imprévisibles.  
  
 La version de cette fonction avec le suffixe `_l` est identique, excepté qu’il utilise les paramètres régionaux passés au lieu des paramètres régionaux actuels pour son comportement dépendant des paramètres régionaux.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_istleadbyte`|Retourne toujours la valeur false|**\_** `isleadbyte`|Retourne toujours la valeur false|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`isleadbyte`|\<ctype.h\>|  
|`_isleadbyte_l`|\<ctype.h\>|  
  
 Pour plus d’informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable, mais consultez [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).  
  
## Voir aussi  
 [Classification d'octets](../../c-runtime-library/byte-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [\_ismbb, routines](../../c-runtime-library/ismbb-routines.md)