---
title: "_set_printf_count_output | Microsoft Docs"
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
  - "_set_printf_count_output"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_printf_count_output"
  - "_set_printf_count_output"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "%n (format)"
  - "_set_printf_count_output (fonction)"
  - "set_printf_count_output (fonction)"
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_printf_count_output
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Activer ou désactiver la prise en charge du format `%n` dans les familles de fonctions [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## Syntaxe  
  
```  
int _set_printf_count_output(  
   int enable  
);  
```  
  
#### Paramètres  
 `enable`  
 Une valeur différente de zéro pour permettre la prise en charge de `%n`, 0 pour désactiver la prise en charge de `%n`.  
  
## Valeur de propriété\/valeur de retour  
 L'état de la prise en charge de `%n` avant d'appeler cette fonction : différent de zéro si la prise en charge de `%n` a été activée, 0 s'il est désactivé.  
  
## Notes  
 Pour des raisons de sécurité, la prise en charge du spécificateur de format `%n` est désactivée par défaut dans `printf` et toutes ses variantes.  Si `%n` se rencontre dans une spécification du format `printf`, le comportement par défaut consiste à appeler le gestionnaire de paramètre non valide comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Appeler `_set_printf_count_output` avec l'argument différent de zéro entraîne les familles de fonction`printf`à interpréter `%n` comme décrit dans [Caractères du champ de type printf](../../c-runtime-library/printf-type-field-characters.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_set_printf_count_output`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_set_printf_count_output.c  
#include <stdio.h>  
  
int main()  
{  
   int e;  
   int i;  
   e = _set_printf_count_output( 1 );  
   printf( "%%n support was %sabled.\n",  
        e ? "en" : "dis" );  
   printf( "%%n support is now %sabled.\n",  
        _get_printf_count_output() ? "en" : "dis" );  
   printf( "12345%n6789\n", &i ); // %n format should set i to 5  
   printf( "i = %d\n", i );  
}  
```  
  
## Sortie  
  
```  
%n support was disabled.  
%n support is now enabled.  
123456789  
i = 5  
```  
  
## Équivalent .NET Framework  
 Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [\_get\_printf\_count\_output](../../c-runtime-library/reference/get-printf-count-output.md)