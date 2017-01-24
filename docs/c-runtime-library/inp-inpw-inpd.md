---
title: "_inp, _inpw, _inpd | Microsoft Docs"
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
  - "_inp"
  - "_inpw"
  - "_inpd"
apilocation: 
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "inpd"
  - "_inp"
  - "_inpw"
  - "_inpd"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_inp (fonction)"
  - "_inpd (fonction)"
  - "_inpw (fonction)"
  - "E/S (CRT), port"
  - "inp (fonction)"
  - "inpd (fonction)"
  - "inpw (fonction)"
  - "ports, routines E/S"
ms.assetid: 5d9c2e38-fc85-4294-86d5-7282cc02d1b3
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _inp, _inpw, _inpd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en entrée sur un port un octet \(`_inp`\), un mot \(`_inpw`\), ou un mot double \(`_inpd`\).  
  
> [!IMPORTANT]
>  Ces fonctions sont obsolètes. Depuis Visual Studio 2015, elles ne sont pas disponibles dans la bibliothèque CRT.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _inp(   
   unsigned short port   
);  
unsigned short _inpw(   
   unsigned short port   
);  
unsigned long _inpd(   
   unsigned short port   
);  
```  
  
#### Paramètres  
 `port`  
 Numéro du port d’E\/S.  
  
## Valeur de retour  
 Les fonctions retournent l’octet, le mot ou le mot double lu à partir du `port`. Aucun retour d'erreur.  
  
## Notes  
 Les fonctions `_inp`, `_inpw` et `_inpd` lisent respectivement un octet, un mot et un mot double sur le port d’entrée spécifié. La valeur d’entrée peut être tout entier court non signé dans la plage 0 \- 65 535.  
  
 Comme ces fonctions lisent directement sur un port d’E\/S, elles ne doivent pas être utilisées dans du code utilisateur dans Windows NT, Windows 2000, Windows XP et Windows Server 2003.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_inp`|\<conio.h\>|  
|`_inpw`|\<conio.h\>|  
|`_inpd`|\<conio.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Console et port E\/S](../c-runtime-library/console-and-port-i-o.md)   
 [\_outp, \_outpw, \_outpd](../c-runtime-library/outp-outpw-outpd.md)