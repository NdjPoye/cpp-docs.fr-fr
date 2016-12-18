---
title: "_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l | Microsoft Docs"
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
  - "_mbcjistojms"
  - "_mbcjmstojis"
  - "_mbcjistojms_l"
  - "_mbcjmstojis_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbcjistojms"
  - "_mbcjistojms"
  - "_mbcjistojms_l"
  - "_mbcjmstojis_l"
  - "_mbcjmstojis"
  - "mbcjmstojis_l"
  - "mbcjistojms_l"
  - "mbcjmstojis"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbcjistojms (fonction)"
  - "_mbcjistojms_l (fonction)"
  - "_mbcjmstojis (fonction)"
  - "_mbcjmstojis_l (fonction)"
  - "mbcjistojms (fonction)"
  - "mbcjistojms_l (fonction)"
  - "mbcjmstojis (fonction)"
  - "mbcjmstojis_l (fonction)"
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit entre les normes de l'industrie japonaises \(JIS\) et les caractères Microsoft pour le Japon \(JMS\).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
unsigned int _mbcjistojms(  
   unsigned int c   
);  
unsigned int _mbcjistojms_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbcjmstojis(  
   unsigned int c   
);  
unsigned int _mbcjmstojis_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à convertir.  
  
 `local`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Sur les paramètres régionaux japonais, ces fonctions retournent un caractère converti ou retournent 0 si aucune conversion n'est possible.  Dans les paramètres régionaux non japonais, ces fonctions retournent le caractère passé.  
  
## Notes  
 la fonction `_mbcjistojms` convertit un caractère aux normes de l'industrie japonaises \(JIS\) en un caractère Kanji Microsoft \(décalage JIS\).  Le caractère est converti uniquement si les octets de tête et de queue sont dans une plage 0x21 – 0x7E.  Si l'octet de tête ou de queue est en dehors de cette plage, `errno` a la valeur `EILSEQ`.  Pour plus d'informations sur ça et d'autres codes d'erreur, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .  
  
 La fonction `_mbcjmstojis`convertit un caractère du décalage JIS en un caractère JIS.  Le caractère est converti uniquement si l'octet de tête est dans la plage 0x81 – 0x9F ou 0xE0 – 0xFC et l'octet de queue se trouve dans la plage 0x40 – 0x7E ou 0x80 – 0xFC.  Notez que certaines points de code de cette plage n'ont pas un caractère assigné et donc ne peuvent pas être convertis.  
  
 La valeur `c` doit être une valeur de 16 bits dont les bits 8 supérieurs représentent l'octet de tête du caractère à convertir et dont les 8 bits inférieurs représentent l'octet de queue.  
  
 La valeur de la sortie est affectée par la valeur du paramètre de la catégorie `LC_CTYPE` des paramètres régionaux ; consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md), pour plus d'informations.  Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 Dans les versions antérieures, `_mbcjistojms` et `_mbcjmstojis` ont été appelés`jistojms` et `jmstojis`, respectivement.  `_mbcjistojms`,`_mbcjistojms_l`,`_mbcjmstojis` et `_mbcjmstojis_l` doivent être utilisés à la place.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mbcjistojms`|\<mbstring.h\>|  
|`_mbcjistojms_l`|\<mbstring.h\>|  
|`_mbcjmstojis`|\<mbstring.h\>|  
|`_mbcjmstojis_l`|\<mbstring.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [\_ismbb, routines](../../c-runtime-library/ismbb-routines.md)